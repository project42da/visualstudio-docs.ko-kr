---
title: 컨테이너에 대한 고급 예제
description: ''
ms.custom: ''
ms.date: 04/18/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: e03835db-a616-41e6-b339-92b41d0cfc70
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c941928495dc39dc6b6ecbe9600f39dad969fec2
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="advanced-example-for-containers"></a>컨테이너에 대한 고급 예제

[컨테이너에 빌드 도구 설치](build-tools-container.md)에서 샘플 Dockerfile은 항상 최신 microsoft/windowsservercore 이미지와 최신 Visual Studio Build Tools 2017 설치 관리자를 기반으로 하는 [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) 이미지를 사용합니다. 이 이미지를 다른 사용자가 풀할 수 있는 [Docker 레지스트리](https://azure.microsoft.com/services/container-registry)에 게시할 경우 많은 시나리오에 괜찮을 수 있습니다. 그러나 실제로 사용하는 기본 이미지, 다운로드하는 바이너리, 그리고 설치하는 도구 버전에 대해 더 구체적인 것이 일반적입니다.

다음 예제의 Dockerfile은 microsoft/dotnet-framework 이미지의 특정 버전 태그를 사용합니다. 기본 이미지에 특정 태그를 사용하는 것이 일반적이며 이미지를 빌드 또는 다시 빌드할 때 항상 동일한 근거가 있다는 점을 기억하는 것이 쉽습니다.

> [!NOTE]
> 컨테이너에서 설치 관리자 실행 시 알려진 문제가 있는 microsoft/windowsservercore:10.0.14393.1593 또는 이를 기반으로 하는 이미지에는 Visual Studio를 설치할 수 없습니다. 자세한 내용은 [알려진 문제](build-tools-container-issues.md)를 참조하세요.

아래 예제에서는 최신 릴리스의 Build Tools 2017을 다운로드합니다. 이전 버전의 Build Tools를 사용하려는 경우 컨테이너에 나중에 설치할 수 있습니다. 먼저 레이아웃을 [만들고](create-an-offline-installation-of-visual-studio.md) [유지](update-a-network-installation-of-visual-studio.md)해야 합니다.

## <a name="install-script"></a>스크립트 설치

설치 오류가 발생할 때 로그를 수집하려면 작업 디렉터리에서 다음 콘텐츠로 "Install.cmd"라는 일괄 처리 스크립트를 만듭니다.

```shell
@if not defined _echo echo off
setlocal enabledelayedexpansion

call %*
if "%ERRORLEVEL%"=="3010" (
    exit /b 0
) else (
    if not "%ERRORLEVEL%"=="0" (
        set ERR=%ERRORLEVEL%
        call C:\TEMP\collect.exe -zip:C:\vslogs.zip

        exit /b !ERR!
    )
)
```

## <a name="dockerfile"></a>Dockerfile

작업 디렉터리에서 다음 콘텐츠로 "Dockerfile"을 만듭니다.

```dockerfile
# escape=`

# Use a specific tagged image. Tags can be changed, though that is unlikely for most images.
# You could also use the immutable tag @sha256:1a66e2b5f3a5b8b98ac703a8bfd4902ae60d307ed9842978df40dbc04ac86b1b
ARG FROM_IMAGE=microsoft/dotnet-framework:4.7.1-20180410-windowsservercore-1709
FROM ${FROM_IMAGE}

# Copy our Install script.
COPY Install.cmd C:\TEMP\

# Download collect.exe in case of an install failure.
ADD https://aka.ms/vscollect.exe C:\TEMP\collect.exe

# Use the latest release channel. For more control, specify the location of an internal layout.
ARG CHANNEL_URL=https://aka.ms/vs/15/release/channel
ADD ${CHANNEL_URL} C:\TEMP\VisualStudio.chman

# Download and install Build Tools excluding workloads and components with known issues.
ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe
RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
    --installPath C:\BuildTools `
    --channelUri C:\TEMP\VisualStudio.chman `
    --installChannelUri C:\TEMP\VisualStudio.chman `
    --all `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
    --remove Microsoft.VisualStudio.Component.Windows81SDK

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
```

다음 명령을 실행하여 현재 작업 디렉터리에 이미지를 빌드합니다.

```shell
docker build -t buildtools2017:15.6.27428.2037 -t buildtools2017:latest -m 2GB .
```

필요에 따라 `--build-arg` 명령줄 스위치를 사용하여 `FROM_IMAGE` 또는 `CHANNEL_URL` 인수 중 하나 또는 모두를 전달하여 고정된 이미지를 유지하도록 다른 기본 이미지 또는 내부 레이아웃의 위치를 지정합니다.

## <a name="diagnosing-install-failures"></a>설치 오류 진단

이 예제에서는 특정 도구를 다운로드하고 해시가 일치하는지 검증합니다. 또한 설치 실패가 발생할 경우 호스트 시스템으로 로그를 복사하여 실패를 분석할 수 있도록 최신 Visual Studio 및 .NET 로컬 컬렉션을 다운로드합니다.

```shell
> docker build -t buildtools2017:15.6.27428.2037 -t buildtools2017:latest -m 2GB .
Sending build context to Docker daemon
...
Step 8/10 : RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache ...
 ---> Running in 4b62b4ce3a3c
The command 'cmd /S /C C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe ...' returned a non-zero code: 1603

> docker cp 4b62b4ce3a3c:C:\vslogs.zip "%TEMP%\vslogs.zip"
```

마지막 줄의 실행이 끝나면 컴퓨터에서 "%TEMP%\vslogs.zip"을 열거나 [개발자 커뮤니티](https://developercommunity.visualstudio.com) 웹 사이트에서 문제를 제출합니다.

## <a name="get-support"></a>지원 받기

때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.

* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고, 답변을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다. (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목

* [Build Tools를 컨테이너에 설치](build-tools-container.md)
* [알려진 컨테이너 관련 문제](build-tools-container-issues.md)
* [Visual Studio Build Tools 2017 워크로드 및 구성 요소 ID](workload-component-id-vs-build-tools.md)
