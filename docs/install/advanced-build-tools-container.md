---
title: "컨테이너의 고급 예 | Microsoft Docs"
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e03835db-a616-41e6-b339-92b41d0cfc70
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: 8ab92d3936306ac47a59df33b4a1131341b28d44
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2017
---
# <a name="advanced-example-for-containers"></a>컨테이너의 고급 예

[컨테이너에 빌드 도구 설치](build-tools-container.md)에서 샘플 Dockerfile은 항상 최신 microsoft/windowsservercore 이미지와 최신 Visual Studio Build Tools 2017 설치 관리자를 사용합니다. 이 이미지를 다른 사용자가 풀할 수 있는 [Docker 레지스트리](https://azure.microsoft.com/services/container-registry)에 게시할 경우 많은 시나리오에 괜찮을 수 있습니다. 그러나 실제로 사용하는 기본 이미지, 다운로드하는 바이너리, 그리고 설치하는 도구 버전에 대해 더 구체적인 것이 일반적입니다.

다음 예제의 Dockerfile은 microsoft/windowsservercore 코어의 특정 버전 태그를 사용합니다. 기본 이미지에 특정 태그를 사용하는 것이 일반적이며 이미지를 빌드 또는 다시 빌드할 때 항상 동일한 근거가 있다는 점을 기억하는 것이 쉽습니다.

> [!NOTE]
> 컨테이너에서 설치 관리자 실행 시 알려진 문제가 있는 microsoft/windowsservercore:10.0.14393.1593에는 Visual Studio를 설치할 수 없습니다. 자세한 내용은 [알려진 문제](build-tools-container-issues.md)를 참조하세요.

이 예제에서는 또한 부트스트래퍼와 동시에 빌드되는 특정 버전을 설치하는 Build Tools 2017 부트스트래퍼도 사용합니다. 이 제품은 릴리스 채널을 통해 업데이트할 수 있지만 일반적으로 다시 빌드할 컨테이너에는 실용적인 시나리오가 아닙니다. 특정 채널에 대한 URL을 가져오려는 경우 https://aka.ms/vs/15/release/channel에서 채널을 다운로드하고 JSON 파일을 열며 부트스트래퍼 URL을 확인할 수 있습니다. 자세한 내용은 [Visual Studio의 네트워크 설치 만들기](create-a-network-installation-of-visual-studio.md)를 참조하세요.

```dockerfile
# Use a specific tagged image. Tags can be changed, though that is unlikely for most images.
# You could also use the immutable tag @sha256:d841bd78721c74f9b88e2700f5f3c2d66b54cb855b8acb4ab2c627a76a46301d
FROM microsoft/windowsservercore:10.0.14393.1770

# Use PowerShell commands to download, validate hashes, etc.
SHELL ["powershell.exe", "-ExecutionPolicy", "Bypass", "-Command", "$ErrorActionPreference='Stop'; $ProgressPreference='SilentlyContinue'; $VerbosePreference = 'Continue';"]

# Download Build Tools 15.4.27004.2005 and other useful tools.
ENV VS_BUILDTOOLS_URI=https://aka.ms/vs/15/release/6e8971476/vs_buildtools.exe \
    VS_BUILDTOOLS_SHA256=D482171C7F2872B6B9D29B116257C6102DBE6ABA481FAE4983659E7BF67C0F88 \
    NUGET_URI=https://dist.nuget.org/win-x86-commandline/v4.1.0/nuget.exe \
    NUGET_SHA256=4C1DE9B026E0C4AB087302FF75240885742C0FAA62BD2554F913BBE1F6CB63A0

# Download tools to C:\Bin and install Build Tools excluding workloads and components with known issues.
RUN New-Item -Path C:\Bin, C:\TEMP -Type Directory | Out-Null; \
    [System.Environment]::SetEnvironmentVariable('PATH', "\"${env:PATH};C:\Bin\"", 'Machine'); \
    function Fetch ([string] $Uri, [string] $Path, [string] $Hash) { \
      Invoke-RestMethod -Uri $Uri -OutFile $Path; \
      if ($Hash -and ((Get-FileHash -Path $Path -Algorithm SHA256).Hash -ne $Hash)) { \
        throw "\"Download hash for '$Path' incorrect\""; \
      } \
    }; \
    Fetch -Uri $env:NUGET_URI -Path C:\Bin\nuget.exe -Hash $env:NUGET_SHA256; \
    Fetch -Uri $env:VS_BUILDTOOLS_URI -Path C:\TEMP\vs_buildtools.exe -Hash $env:VS_BUILDTOOLS_SHA256; \
    Fetch -Uri 'https://aka.ms/vscollect.exe' -Path C:\TEMP\collect.exe; \
    $p = Start-Process -Wait -PassThru -FilePath C:\TEMP\vs_buildtools.exe -ArgumentList '--quiet --wait --norestart --nocache --installPath C:\BuildTools --all --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 --remove Microsoft.VisualStudio.Component.Windows81SDK'; \
    if (($ret = $p.ExitCode) -and ($ret -ne 3010)) { C:\TEMP\collect.exe; throw ('Install failed with exit code 0x{0:x}' -f $ret) }

# Restore default shell for Windows containers.
SHELL ["cmd.exe", "/s", "/c"]

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
```

이 예제에서는 특정 도구를 다운로드하고 해시가 일치하는지 검증합니다. 또한 설치 실패가 발생할 경우 호스트 시스템으로 로그를 복사하여 실패를 분석할 수 있도록 최신 Visual Studio 및 .NET 로컬 컬렉션을 다운로드합니다.

```shell
> docker build -t buildtools:15.4.27004.2005 -t buildtools:latest -m 2GB .
Sending build context to Docker daemon
...
Step 4/7 : RUN New-Item -Path C:\Bin, C:\TEMP -Type Directory | Out-Null; ...
 ---> Running in 4b62b4ce3a3c
Install failed with exit code 0x643
At line:1 char:1
+ throw ('Install failed with exit code 0x{0:x}' -f 1603)
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (Install failed with exit code 0x643:String) [], RuntimeException
    + FullyQualifiedErrorId : Install failed with exit code 0x643

> docker cp 4b62b4ce3a3c:C:\Users\ContainerAdministrator\AppData\Local\TEMP\vslogs.zip "%TEMP%\vslogs.zip"
```

마지막 줄의 실행이 끝나면 컴퓨터에서 "%TEMP%\vslogs.zip"을 열거나 [개발자 커뮤니티](https://developercommunity.visualstudio.com) 웹 사이트에서 문제를 제출합니다.

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.
* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.  (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목
* [빌드 도구를 컨테이너에 설치](build-tools-container.md)
* [컨테이너에 대한 알려진 문제](build-tools-container-issues.md)
