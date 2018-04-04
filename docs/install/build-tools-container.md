---
title: Build Tools를 컨테이너에 설치 | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: d5c038e2-e70d-411e-950c-8a54917b578a
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 50a63b954c87e6b5308e499be2422948fa865964
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2018
---
# <a name="install-build-tools-into-a-container"></a>Build Tools를 컨테이너에 설치

Visual Studio Build Tools를 Windows 컨테이너에 설치하여 CI/CD(지속적인 통합/지속적인 업데이트) 워크플로를 지원할 수 있습니다. 이 문서에서는 컨테이너에 설치할 수 있는 [워크로드 및 구성 요소](workload-component-id-vs-build-tools.md)뿐만 아니라 변경할 필요가 있는 Docker 구성을 안내합니다.

[컨테이너](https://www.docker.com/what-container)는 CI/CD 서버 환경뿐만 아니라 개발 환경에서도 사용할 수 있는 일관된 빌드 시스템을 패키지하는 유용한 방법입니다. 예를 들어 Visual Studio 또는 다른 도구를 사용하여 코드를 계속 작성하는 동안 사용자 지정 환경에서 빌드할 컨테이너에 소스 코드를 탑재할 수 있습니다. CI/CD 워크플로에서 동일한 컨테이너 이미지를 사용하면 코드를 일관되게 작성할 수 있습니다. 또한 런타임 일관성을 위해서도 컨테이너를 사용할 수 있습니다. 이 경우 오케스트레이션 시스템에서 여러 컨테이너를 사용하는 마이크로 서비스에는 일반적이지만 이 문서의 범위를 벗어납니다.

Visual Studio Build Tools에 소스 코드를 빌드하는 데 필요한 것이 없는 경우 다른 Visual Studio 제품에 대해 동일한 단계를 사용할 수 있습니다. 그러나 Windows 컨테이너는 대화형 사용자 인터페이스를 지원하지 않으므로 모든 명령을 자동화해야 합니다.

## <a name="overview"></a>개요

[Docker](https://www.docker.com/what-docker)를 사용하여 소스 코드를 작성하는 컨테이너를 만들 수 있는 이미지를 만듭니다. Dockerfile 예제는 최신 Visual Studio Build Tools 2017 및 소스 코드 작성에 자주 사용되는 유용한 다른 프로그램 일부를 설치합니다. 사용자 고유의 Dockerfile을 추가로 수정하여 테스트 실행, 빌드 출력 게시 등을 수행할 수 있는 다른 도구와 스크립트를 포함할 수 있습니다.

Windows용 Docker를 이미 설치한 경우 3단계로 건너뛸 수 있습니다.

## <a name="step-1-enable-hyper-v"></a>1단계: Hyper-V 사용 설정

Hyper-V는 기본적으로 사용되지 않습니다. 현재 Windows 10에서 Hyper-V 격리만 지원되므로 Windows용 Docker를 사용하도록 설정해야 합니다.

* [Windows 10에서 Hyper-V를 사용하도록 설정](https://docs.microsoft.com/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v)
* [Windows Server 2016에서 Hyper-V를 사용하도록 설정](https://docs.microsoft.com/windows-server/virtualization/hyper-v/get-started/install-the-hyper-v-role-on-windows-server)

> [!NOTE]
> 컴퓨터에서 가상화를 사용하도록 설정해야 합니다. 일반적으로는 기본적으로 사용하도록 설정됩니다. 그러나 Hyper-V 설치가 실패하는 경우 가상화를 사용하도록 설정하는 방법은 시스템 설명서를 참조하세요.

## <a name="step-2-install-docker-for-windows"></a>2단계. Windows용 Docker 설치

Windows 10을 사용하는 경우 [Windows용 Docker Community Edition](https://www.docker.com/docker-windows)을 다운로드하여 설치할 수 있습니다. PowerShell을 사용하여 DSC(Desired State Configuration) 또는 간단한 단일 설치용 [패키지 공급자](https://docs.microsoft.com/virtualization/windowscontainers/deploy-containers/deploy-containers-on-server)를 통해 [Windows Server 2016용 Docker Enterprise Edition을 설치](https://docs.docker.com/engine/installation/windows/docker-ee)할 수 있습니다.

## <a name="step-3-switch-to-windows-containers"></a>3단계. Windows 컨테이너로 전환

Windows에서 Build Tools 2017만 설치할 수 있으므로 [Windows 컨테이너로 전환](https://docs.docker.com/docker-for-windows/#getting-started-with-windows-containers)해야 합니다. Windows 컨테이너는 Windows 10에서 [Hyper-V 격리](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container)만 지원하고, Windows Server 2016에서는 Hyper-V 및 프로세스 격리를 모두 지원합니다.

## <a name="step-4-expand-maximum-container-disk-size"></a>4단계. 최대 컨테이너 디스크 크기 확장

Visual Studio Build Tools(및 상위 수준의 Visual Studio)에서 설치하는 모든 도구에 많은 디스크 공간이 필요합니다. Dockerfile 예제에서 패키지 캐시를 사용하지 않더라도 필요한 공간을 수용하려면 컨테이너 이미지의 디스크 크기를 늘려야 합니다. 현재 Windows에서는 Docker 구성만 변경하여 디스크 크기를 늘릴 수 있습니다.

**Windows 10**:

1. 시스템 트레이에 있는 [Windows용 Docker 아이콘을 마우스 오른쪽 단추로 클릭](https://docs.docker.com/docker-for-windows/#docker-settings)하고 **설정...**을 클릭합니다.
2. [디먼 섹션을 클릭](https://docs.docker.com/docker-for-windows/#docker-daemon)합니다.
3. [**기본** 단추를 **고급**으로 전환](https://docs.docker.com/docker-for-windows/#edit-the-daemon-configuration-file)합니다.
4. 다음 JSON 배열 속성을 추가하여 디스크 공간을 120GB(Build Tools의 확장도 수용할 만큼 충분한 크기 이상)로 늘립니다.

   ```json
   {
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

   이 속성은 이미 있는 모든 항목에 추가됩니다. 예를 들어 기본 디먼 구성 파일에 이러한 변경 내용을 적용하면 다음과 같이 표시됩니다.

   ```json
   {
     "registry-mirrors": [],
     "insecure-registries": [],
     "debug": true,
     "experimental": true,
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

5. **적용**을 클릭합니다.

**Windows Server 2016**:

1. "Docker" 서비스를 중지합니다.

   ```shell
   sc.exe stop docker
   ```

2. 관리자 권한 명령 프롬프트에서 "%ProgramData%\Docker\config\daemon.json"(또는 `dockerd --config-file`에 지정한 모든 내용)을 편집합니다.
3. 다음 JSON 배열 속성을 추가하여 디스크 공간을 120GB(Build Tools의 확장도 수용할 만큼 충분한 크기 이상)로 늘립니다.

   ```json
   {
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

   이 속성은 이미 있는 모든 항목에 추가됩니다.
4. 파일을 저장한 후 닫습니다.
5. "Docker" 서비스를 시작합니다.

   ```shell
   sc.exe start docker
   ```

## <a name="step-5-create-and-build-the-dockerfile"></a>5단계. Dockerfile 만들기 및 빌드

다음 예제 Dockerfile을 디스크의 새 파일에 저장해야 합니다. 파일 이름이 단순히 "Dockerfile"이면 기본적으로 인식됩니다.

> [!NOTE]
> 이 Dockerfile 예제는 컨테이너에 설치할 수 없는 이전 버전의 Windows SDK만 제외합니다. 이전 릴리스에서는 빌드 명령이 실패하게 됩니다.

1. 명령 프롬프트를 엽니다.
2. 새 디렉터리를 만듭니다(권장).

   ```shell
   mkdir C:\BuildTools
   ```

3. 디렉터리를 이 새 디렉터리로 변경합니다.

   ```shell
   cd C:\BuildTools
   ```

3. 다음 내용을 C:\BuildTools\Dockerfile에 저장합니다.

   ```dockerfile
   # Use the latest Windows Server Core image.
   FROM microsoft/windowsservercore

   # Download useful tools to C:\Bin.
   ADD https://dist.nuget.org/win-x86-commandline/v4.1.0/nuget.exe C:\\Bin\\nuget.exe

   # Download the Build Tools bootstrapper outside of the PATH.
   ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:\\TEMP\\vs_buildtools.exe

   # Add C:\Bin to PATH and install Build Tools excluding workloads and components with known issues.
   RUN setx /m PATH "%PATH%;C:\Bin" \
    && C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache --installPath C:\BuildTools --all \
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 \
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 \
       --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 \
       --remove Microsoft.VisualStudio.Component.Windows81SDK \
    || IF "%ERRORLEVEL%"=="3010" EXIT 0

   # Start developer command prompt with any other commands specified.
   ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

   # Default to PowerShell if no other command specified.
   CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
   ```

4. 해당 디렉터리 내에서 다음 명령을 실행합니다.

   ```shell
   docker build -t buildtools2017:latest -m 2GB .
   ```

   이 명령은 현재 디렉터리에서 2GB의 메모리를 사용하여 Dockerfile을 빌드합니다. 일부 작업을 설치하는 경우 기본 1GB가 충분하지 않습니다. 그러나 빌드 요구 사항에 따라 1GB의 메모리만으로도 빌드할 수 있습니다.

   최종 이미지에는 "buildtools2017:latest"라는 태그가 지정됩니다. 태그가 지정되지 않더라도 "latest" 태그가 기본값이므로 컨테이너에서 해당 이미지를 "buildtools2017"로 쉽게 실행할 수 있습니다. 더 많은 [고급 시나리오](advanced-build-tools-container.md)에서 특정 버전의 Visual Studio Build Tools 2017을 사용하려는 경우, 컨테이너에서 특정 버전을 일관되게 사용할 수 있도록 특정 Visual Studio 빌드 번호뿐만 아니라 "latest"도 포함된 태그를 컨테이너에 지정할 수도 있습니다.

## <a name="step-6-using-the-built-image"></a>6단계. 빌드된 이미지 사용

이제 이미지를 만들었으므로 컨테이너 내에서 해당 이미지를 실행하여 대화형 빌드와 자동화된 빌드를 모두 수행할 수 있습니다. 이 예제에서는 개발자 명령 프롬프트를 사용하므로 PATH 및 기타 환경 변수가 이미 구성되어 있습니다.

1. 명령 프롬프트를 엽니다.
2. 컨테이너를 실행하여 모든 개발자 환경 변수가 설정된 PowerShell 환경을 시작합니다.

   ```shell
   docker run -it buildtools2017
   ```

이 이미지를 CI/CD 워크플로에 사용하려면 자신의 [Azure Container Registry](https://azure.microsoft.com/services/container-registry) 또는 다른 내부 [Docker 레지스트리](https://docs.docker.com/registry/deploying)에 게시하여 서버에서 끌어오기만 하면 됩니다.

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.
* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.  (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목

* [고급 컨테이너 예제](advanced-build-tools-container.md)
* [알려진 컨테이너 관련 문제](build-tools-container-issues.md)
* [Visual Studio Build Tools 2017 워크로드 및 구성 요소 ID](workload-component-id-vs-build-tools.md)
