---
title: 원격 디버깅 원격 IIS 컴퓨터에 ASP.NET Core | Microsoft Docs
ms.custom: remotedebugging
ms.date: 05/21/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 573a3fc5-6901-41f1-bc87-557aa45d8858
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 607f4bb2bcce3d8895a4a07df8d70c866e7a6aab
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746932"
---
# <a name="remote-debug-aspnet-core-on-a-remote-iis-computer-in-visual-studio-2017"></a>Visual Studio 2017에 원격 IIS 컴퓨터에 원격 디버깅 ASP.NET Core
IIS에 배포 된 ASP.NET 응용 프로그램을 디버깅 하려면 설치 및 응용 프로그램을 배포한 컴퓨터에서 원격 도구를 실행 하 고 Visual Studio에서 실행 중인 앱에 연결 합니다.

![원격 디버거 구성 요소](../debugger/media/remote-debugger-aspnet.png "Remote_debugger_components")

이 가이드에는 설정, Visual Studio 2017 ASP.NET Core 구성 및 IIS에 배포 하 고 Visual Studio에서 원격 디버거를 연결 하는 방법을 설명 합니다. 원격 디버깅 ASP.NET 4.5.2, 참조 [IIS 컴퓨터에 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)합니다. 배포 하 고 Azure를 사용 하 여 IIS에서 디버깅할 수도 있습니다. Azure 앱 서비스에 대 한 쉽게 배포 하 고 디버그할 수의 IIS와 원격 디버거 중 하나를 사용 하 여 미리 구성 된 인스턴스에서 [스냅숏 디버거](../debugger/debug-live-azure-applications.md) 또는 [서버 탐색기에서 디버거를 연결](../debugger/remote-debugging-azure.md)합니다.

이러한 절차 이러한 서버 구성에서 테스트 되었으며:
* Windows Server 2012 R2 및 IIS 8
* Windows Server 2016 및 IIS 10

## <a name="requirements"></a>요구 사항

프록시를 통해 연결 된 두 컴퓨터 간에 디버깅이 지원 되지 않습니다. 국가 간 대기 시간이 긴 또는 전화 접속, 인터넷 등 낮은 대역폭 연결을 통해 또는 인터넷을 통해 디버깅 권장 되지 않습니다 및 실패 하거나 느리고 수입니다. 요구 사항 목록은 전체 참조 [요구 사항](../debugger/remote-debugging.md#requirements_msvsmon)합니다.

## <a name="app-already-running-in-iis"></a>IIS에서 이미 실행 중인 앱?

이 문서는 Windows 서버에 IIS의 기본 구성 설정 하 고 Visual Studio에서 앱을 배포 하는 단계를 포함 합니다. 이러한 단계는 서버 응용 프로그램을 올바르게 실행할 수 있도록 하 고 원격 디버그에 준비가 설치 된 구성 요소에 필요한에 있는지 확인 하기 위해 포함 합니다.

* 응용 프로그램은 IIS에서 실행 되 고 원격 디버거를 다운로드 하 고 디버깅을 시작로 이동 하 려 할 경우 [다운로드 하 여 Windows Server에서 원격 도구 설치](#BKMK_msvsmon)합니다.

* 앱 설정 되어 있는지, 배포 되었는지 확인 하는 데 도움이 필요 하 고이 항목의 모든 단계에 따라 디버그할 수 있도록 IIS에서 올바르게 실행 합니다.

## <a name="create-the-aspnet-core-application-on-the-visual-studio-2017-computer"></a>Visual Studio 2017 컴퓨터에서 ASP.NET Core 응용 프로그램 만들기 

1. 새 ASP.NET Core 응용 프로그램을 만듭니다. (**파일 > 새로 만들기 > 프로젝트**을 선택한 후 **Visual C# > 웹 > ASP.NET Core 웹 응용 프로그램**).

    에 **ASP.NET Core** 템플릿 섹션 **웹 응용 프로그램**합니다.

2. 있는지 확인 **ASP.NET 코어 2.0** 선택 되어 있는 **Docker 지원을 사용 하도록 설정** 은 **하지** 선택한 하 고 **인증** 로 설정 되어 **인증 안 함**합니다.

3. 프로젝트 이름을 **MyASPApp** 클릭 **확인** 에 새 솔루션을 만듭니다.

4. About.cshtml.cs 파일을 열고에 중단점을 설정는 `OnGet` 메서드 (에 중단점을 설정 하 고 이전 템플릿은 HomeController.cs를 대신 엽니다는 `About()` 메서드).

## <a name="bkmk_configureIIS"></a> 설치 하 고 Windows 서버에서 IIS를 구성 합니다.

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Windows Server에서 브라우저 보안 설정을 업데이트합니다

(기본적으로 사용 됩니다) Internet Explorer에서 보안 강화 구성을 사용 하면 일부 도메인을 웹 서버 구성 요소 중 일부를 다운로드할 수 있도록를 신뢰할 수 있는 사이트로 추가 해야 할 수 있습니다. 로 이동 하 여 신뢰할 수 있는 사이트 추가 **인터넷 옵션 > 보안 > 신뢰할 수 있는 사이트 > 사이트**합니다. 다음 도메인을 추가 합니다.

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- iis.net

소프트웨어를 다운로드 하는 경우에 다양 한 웹 사이트 스크립트 및 리소스를 로드할 수 있는 권한을 부여 하는 요청 발생할 수 있습니다. 필요 하지 않지만 프로세스를 간소화 하기 위해 클릭 이러한 리소스 중 일부 **추가** 대화 상자가 나타나면 합니다.

## <a name="install-aspnet-core-on-windows-server"></a>Windows Server에 ASP.NET Core를 설치 합니다.

1. 설치는 [.NET 핵심 Windows Server 호스팅](https://aka.ms/dotnetcore-2-windowshosting) 호스팅 시스템에서 번들입니다. .NET Core 런타임,.NET 핵심 라이브러리 및 ASP.NET Core 모듈 번들을 설치합니다. 더 자세한 지침에 대 한 참조 [를 IIS에 게시](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)합니다.

    > [!NOTE]
    > 시스템으로 지정 되지 않은 인터넷에 연결 하는 경우 구하여 설치는 *[Microsoft Visual c + + 2015 재배포 가능](https://www.microsoft.com/download/details.aspx?id=53840)* .NET 핵심 Windows Server 호스팅 번들을 설치 하기 전에.

3. 시스템을 다시 시작 (실행 또는 **net stop가 /y** 뒤 **net 시작 w3svc** 시스템 경로에 대 한 변경을 선택 하기 위해 명령 프롬프트에서).

## <a name="choose-a-deployment-option"></a>배포 옵션을 선택 합니다.

IIS에 앱을 배포 하는 데 도움이 필요, 이러한 옵션을 고려 합니다.

* IIS에서 게시 설정 파일을 만들고 Visual Studio의 설정을 가져올 배포 합니다. 일부 시나리오에서 앱을 배포 하는 빠른 방법을 이것이입니다. 게시 설정 파일을 만들 때 사용 권한은 자동으로 설정 됩니다 IIS에서.

* 로컬 폴더에 게시 하 고 IIS에서 준비 된 응용 프로그램 폴더를 기본 방법으로 출력을 복사 하 여 배포 합니다.

## <a name="optional-deploy-using-a-publish-settings-file"></a>(선택 사항) 게시 설정 파일을 사용 하 여 배포

이 옵션을 사용 하려면 게시 설정 파일을 만들고 Visual Studio로 가져옵니다.

> [!NOTE]
> 이 배포 방법은 웹 배포를 사용합니다. 웹 배포를 수동으로 구성 Visual Studio에서 설정을 가져오지 않고 하려는 경우에 호스팅 서버에 대 한 웹 배포 3.6 대신 웹 배포 3.6를 설치할 수 있습니다. 그러나 수동으로 웹 배포을 구성 해야 합니다는 응용 프로그램 폴더가 서버에 올바른 값 및 사용 권한으로 구성 되어 있는지 확인 하십시오 (참조 [구성할 ASP.NET 웹 사이트](#BKMK_deploy_asp_net)).

### <a name="install-and-configure-web-deploy-for-hosting-servers-on-windows-server"></a>설치 및 Windows Server에서 호스팅 서버에 대 한 웹 배포를 구성 합니다.

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

### <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Windows Server에는 IIS에서 게시 설정 파일 만들기

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/create-publish-settings-iis.md)]

### <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio에서 게시 설정 가져오기 및 배포

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/import-publish-settings-vs.md)]

응용 프로그램을 성공적으로 배포 후 자동으로 시작 해야 합니다. Visual Studio에서 앱 시작 되지 않으면, IIS에서 앱을 시작 합니다. ASP.NET Core 응용 프로그램 풀 필드에 있는지 확인 해야는 **DefaultAppPool** 로 설정 된 **관리 코드 없음**합니다.

1. 에 **설정** 대화 상자, 클릭 하 여 디버깅 사용 **다음**, 선택는 **디버그** 구성을 선택한 후 **에서 추가 파일 제거 대상** 아래는 **파일 게시** 옵션입니다.

    > [!NOTE]
    > 디버깅을 비활성화 하는 릴리스 구성을 선택 하면는 *web.config* 게시할 때 파일입니다.

1. 클릭 **저장** 한 다음 응용 프로그램을 다시 게시 합니다.

## <a name="optional-deploy-by-publishing-to-a-local-folder"></a>(선택 사항) 로컬 폴더에 게시 하 여 배포

RoboCopy Powershell을 사용 하 여 IIS에 응용 프로그램을 복사 하려면 또는 파일을 복사 하려는 경우 앱을 배포 하려면이 옵션을 사용할 수 있습니다.

### <a name="BKMK_deploy_asp_net"></a> Windows Server 컴퓨터에 ASP.NET 웹 사이트를 구성 합니다.

1. Windows 탐색기를 열고 새 폴더를 만들 **C:\Publish**, ASP.NET 프로젝트를 나중에 배포 됩니다 있습니다.

2. 열려 있지 않으면 엽니다는 **인터넷 정보 서비스 (IIS) 관리자**합니다. (서버 관리자의 왼쪽된 창에서 선택 **IIS**합니다. 서버를 마우스 오른쪽 단추로 클릭 하 고 선택 **인터넷 정보 서비스 (IIS) 관리자**.)

3. 아래 **연결** 왼쪽된 창에서로 이동 **사이트**합니다.

4. 선택 된 **기본 웹 사이트**, 선택 **기본 설정**, 설정는 **실제 경로** 를 **C:\Publish**합니다.

4. **기본 웹 사이트** 노드를 마우스 오른쪽 단추로 클릭하고 **응용 프로그램 추가**를 선택합니다.

5. 설정의 **별칭** 필드를 **MyASPApp**, 응용 프로그램 풀 기본값을 그대로 (**DefaultAppPool**)을 설정 하 고는 **실제 경로** 를 **C:\Publish**합니다.

6. 아래 **연결**선택, **응용 프로그램 풀**합니다. 열기 **DefaultAppPool** 응용 프로그램 풀 필드를 설정 하 고 **관리 코드 없음**합니다.

7. IIS 관리자에서 새 사이트를 마우스 오른쪽 단추로 클릭, 선택 **사용 권한 편집**, 해당 IUSR, IIS_IUSRS, 또는 웹 응용 프로그램에 대 한 액세스는 읽기 및 실행 권한 가진 인증된 된 사용자에 대해 구성 된 사용자 있는지 확인 합니다.

    액세스 권한이 있는이 사용자 중 하나가 표시 되지 않으면, IUSR 읽기 및 실행 권한이 있는 사용자로 추가 하는 단계를 통해 이동 합니다.

### <a name="publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>Visual Studio에서 로컬 폴더에 게시 하 여 앱을 배포 및 게시

게시 하 고 파일 시스템 또는 기타 도구를 사용 하 여 앱을 배포할 수도 있습니다.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

## <a name="BKMK_msvsmon"></a> 다운로드 하 여 Windows Server에서 원격 도구 설치

이 자습서에서는 Visual Studio 2017 사용 했습니다.

원격 디버거 다운로드 페이지를 여는 데 문제가 있는 경우 참조 [파일 다운로드를 차단 해제](../debugger/remote-debugging.md#unblock_msvsmon) 에 대 한 도움말입니다.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> 일부 시나리오에서는 파일 공유에서 원격 디버거를 실행 하는 가장 효율적인 수 있습니다. 자세한 내용은 참조 [파일 공유에서 원격 디버거를 실행](../debugger/remote-debugging.md#fileshare_msvsmon)합니다.
  
## <a name="BKMK_setup"></a> Windows Server에서 원격 디버거 설정

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> 추가 사용자에 대 한 사용 권한을 추가 하는 인증 모드를 변경 하거나 원격 디버거에 대 한 포트 번호에 필요한 경우 참조 [원격 디버거 구성](../debugger/remote-debugging.md#configure_msvsmon)합니다.

원격 디버거를 서비스로 실행에 대 한 정보를 참조 하십시오. [원격 디버거를 서비스로 실행](../debugger/remote-debugging.md#bkmk_configureService)합니다.

## <a name="BKMK_attach"></a> Visual Studio 컴퓨터에서 ASP.NET 응용 프로그램에 연결

1. Visual Studio 컴퓨터에서 디버깅을 시도 하 고 있는 솔루션을 엽니다 (**MyASPApp** 이 문서에서 모든 단계를 따르는 경우).
2. Visual Studio에서 클릭 **디버그 > 프로세스에 연결** (Ctrl + Alt + P).

    > [!TIP]
    > Visual Studio 2017에 다시 연결할 수 있습니다 이전에 사용 하 여 연결할 동일한 프로세스에 **디버그 > 프로세스에 다시 연결 중...** (Shift + Alt + P)입니다. 

3. 한정자 필드를 설정  **\<원격 컴퓨터 이름 >: 4022**합니다.
4. 클릭 **새로 고침**합니다.
    일부 프로세스가 **사용 가능한 프로세스** 창에 표시됩니다.

    모든 프로세스가 표시 되지 않으면, (포트는 필수) 원격 컴퓨터 이름 대신 IP 주소를 사용해 보십시오. 사용할 수 있습니다 `ipconfig` IPv4 주소를 얻기 위해 명령줄에 있습니다.

    사용 하려는 경우는 **찾을** 단추를 해야 할 수 있습니다 [UDP 포트 3702 열고](#bkmk_openports) 서버의 합니다.

5. **모든 사용자의 프로세스 표시**를 선택합니다.
6. 빠르게 찾기 위해 프로세스 이름의 첫 글자를 입력 **dotnet.exe** (용 ASP.NET Core).

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess_aspnetcore.png "RemoteDBG_AttachToProcess")

7. **연결**을 클릭합니다.

8. 원격 컴퓨터의 웹 사이트를 엽니다. 브라우저에서로 이동 **http://\<원격 컴퓨터 이름 >** 합니다.
    
    ASP.NET 웹 페이지가 표시됩니다.

9. 실행 중인 ASP.NET 응용 프로그램에서 링크를 클릭 하 여 **에 대 한** 페이지.

    Visual Studio에서 중단점이 적중됩니다.

## <a name="bkmk_openports"></a> 문제 해결: Windows Server에 필요한 포트를 열려면

대부분의 설치 프로그램에서 ASP.NET와 원격 디버거 설치를 통해 필요한 포트가 열립니다. 그러나 포트가 열려 있는지 확인 해야 합니다.

> [!NOTE]
> Azure VM에서 포트를 열어야 통해는 [네트워크 보안 그룹](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80)합니다. 

필요한 포트:

- 80-IIS에 대 한 필요합니다.
- 4022-Visual Studio 2017 원격 디버깅을 위해 필요 합니다. (참조 [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md) 자세한 정보에 대 한 합니다.
- 8172-(선택 사항) Visual Studio에서 앱을 배포 하기 위해 Web Deploy에 필요 합니다.
- UDP 3702-(선택 사항) 검색 포트 수 있습니다는 **찾을** 단추 Visual Studio에서 원격 디버거를 연결 합니다.

1. Windows Server에서 포트를 열려면는 **시작** 메뉴, 검색할 **고급 보안이 포함 된 Windows 방화벽**합니다.

2. 그런 다음 선택 **인바운드 규칙 > 새 규칙 > 포트**, 클릭 하 고 **다음**합니다. (UDP 3702 선택 **아웃 바운드 규칙** 대신 합니다.)

3. 아래 **특정 로컬 포트**, 포트 번호를 입력, 클릭 **다음**합니다.

4. 클릭 **연결 허용**, 클릭 **다음**합니다.

5. 포트에 대 한 고 클릭 하나 이상의 네트워크 종류도 선택 **다음**합니다.

    선택한 유형은 원격 컴퓨터가 연결된 네트워크를 포함해야 합니다.
6. 이름을 추가 합니다 (예를 들어 **IIS**, **웹 배포**, 또는 **msvsmon**) 인바운드 규칙과 클릭에 대 한 **마침**합니다.

    인바운드 규칙 또는 아웃 바운드 규칙 목록에 새 규칙이 표시 됩니다.

    Windows 방화벽 구성에 대 한 자세한 내용은 참조 [원격 디버깅용 Windows 방화벽을 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)합니다.

3. 필요한 포트에 대 한 추가 규칙을 만듭니다.
