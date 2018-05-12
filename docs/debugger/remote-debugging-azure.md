---
title: 원격 디버깅 IIS와 Azure에서 ASP.NET Core | Microsoft Docs
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a6c04b53-d1b9-4552-a8fd-3ed6f4902ce6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
- dotnetcore
- azure
ms.openlocfilehash: c95a91ecd057bfec7af5e9b932d4326cdcab9270
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="remote-debug-aspnet-core-on-iis-in-azure-in-visual-studio-2017"></a>Visual Studio 2017에는 Azure에서 IIS에서 ASP.NET Core 원격 디버그

이 설정 및 Visual Studio 2017 ASP.NET Core 응용 프로그램을 구성 하 고 Azure를 사용 하 여 IIS에 배포 하 고 Visual Studio에서 원격 디버거를 연결 하는 방법을 설명 합니다.

Azure에서 원격 디버그 하는 권장된 방법은 각 시나리오에 따라 달라 집니다.

* Azure 앱 서비스에서 ASP.NET Core를 디버깅 하려면 참조 [스냅숏 디버거를 사용 하 여 Azure 디버그 앱](../debugger/debug-live-azure-applications.md)합니다. 이것이 권장된 방법입니다.
* 보다 일반적인 디버깅 기능을 사용 하 여 Azure 앱 서비스에서 ASP.NET Core를 디버깅 하려면이 항목의 단계를 수행 합니다. (섹션을 참조 [Azure 앱 서비스에서 원격 디버깅](#remote_debug_azure_app_service)).

    이 시나리오에서는 Visual Studio에서 Azure에 응용 프로그램을 배포 해야 하지만를 수동으로 설치 하거나 다음 그림에 나와 있는 것 처럼 IIS 또는 (이러한 구성 요소는 점선으로 표시 됩니다.) 원격 디버거를 구성할 필요는 없습니다.

    ![원격 디버거 구성 요소](../debugger/media/remote-debugger-azure-app-service.png "Remote_debugger_components")

* Azure VM에서 IIS를 디버깅 하려면이 항목의 단계를 수행 합니다. (섹션을 참조 [Azure VM에서 원격 디버깅](#remote_debug_azure_vm)). Iis 사용자 지정된 구성을 사용할 수 있습니다 하지만 설치 및 배포 단계는 더 복잡 합니다.

    Azure VM에 대 한 Visual Studio에서 Azure에 응용 프로그램을 배포 해야 하 고 또한 해야 IIS 역할 및 원격 디버거를 수동으로 설치 하려면 다음 그림에 나와 있는 것 처럼 합니다.

    ![원격 디버거 구성 요소](../debugger/media/remote-debugger-azure-vm.png "Remote_debugger_components")

* Azure 서비스 패브릭에서 ASP.NET Core를 디버깅 하려면 참조 [원격 서비스 패브릭 응용 프로그램을 디버깅](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application)합니다.

> [!WARNING]
> 이 자습서의 단계를 완료 했을 때 만드는 Azure 리소스를 삭제 해야 합니다. 불필요 한 비용이 발생 하지 않아도 해당 방법입니다.


### <a name="requirements"></a>요구 사항

프록시를 통해 연결 된 두 컴퓨터 간에 디버깅이 지원 되지 않습니다. 국가 간 대기 시간이 긴 또는 전화 접속, 인터넷 등 낮은 대역폭 연결을 통해 또는 인터넷을 통해 디버깅 권장 되지 않습니다 및 실패 하거나 느리고 수입니다. 요구 사항 목록은 전체 참조 [요구 사항](../debugger/remote-debugging.md#requirements_msvsmon)합니다.

## <a name="create-the-aspnet-core-application-on-the-visual-studio-2017-computer"></a>Visual Studio 2017 컴퓨터에서 ASP.NET Core 응용 프로그램 만들기 

1. 새 ASP.NET Core 응용 프로그램을 만듭니다. (선택 **파일 > 새로 만들기 > 프로젝트**을 선택한 후 **Visual C# > 웹 > ASP.NET Core 웹 응용 프로그램**).

    에 **ASP.NET Core** 템플릿 섹션 **웹 응용 프로그램**합니다.

2. 있는지 확인 **ASP.NET 코어 2.0** 선택 되어 있는 **Docker 지원을 사용 하도록 설정** 은 **하지** 선택한 하 고 **인증** 로 설정 되어 **인증 안 함**합니다.

3. 프로젝트 이름을 **MyASPApp** 클릭 **확인** 에 새 솔루션을 만듭니다.

4. About.cshtml.cs 파일을 열고에 중단점을 설정는 `OnGet` 메서드 (에 중단점을 설정 하 고 이전 템플릿은 HomeController.cs를 대신 엽니다는 `About()` 메서드).

## <a name="remote_debug_azure_app_service"></a> Azure 앱 서비스에서 ASP.NET Core 원격 디버그

Visual Studio에서 게시 하 고 IIS의 완전 하 게 된 인스턴스를 응용 프로그램을 디버깅할 신속 하 게 있습니다. 그러나 IIS 구성 사전 설정 되어 있으며 사용자 지정할 수 없습니다. 자세한 내용은 참조 [Visual Studio를 사용 하 여 Azure에 ASP.NET Core 웹 앱을 배포](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)합니다. (IIS 사용자 지정 하는 기능, 필요한 경우 디버깅에서 시도 [Azure VM](#BKMK_azure_vm).) 

#### <a name="to-deploy-the-app-and-remote-debug-using-server-explorer"></a>배포 응용 프로그램 및 서버 탐색기를 사용 하 여 원격 디버깅 하려면

1. Visual Studio에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시**합니다.

2. 선택 **Microsoft Azure 앱 서비스** 에서 **게시** 대화 상자에서 **새로 만들기**를 게시 하려면 프롬프트를 따릅니다.

    자세한 내용은 참조 [Visual Studio를 사용 하 여 Azure에 ASP.NET Core 웹 앱을 배포](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)합니다.

3. 열기 **서버 탐색기** (**보기** > **서버 탐색기**) 응용 프로그램 서비스 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **디버거연결**.

4. 실행 중인 ASP.NET 응용 프로그램에서 링크를 클릭 하 여 **에 대 한** 페이지.

    Visual Studio에서 중단점이 적중됩니다.

    정말 간단하죠. 이 항목의 단계 나머지는 Azure VM에 원격 디버깅에 적용 됩니다.

## <a name="remote_debug_azure_vm"></a> Azure VM에서 ASP.NET Core 원격 디버그

Windows 서버에 대 한 Azure VM 만들 지정 하 고 설치 및 IIS 및 기타 필수 소프트웨어 구성 요소를 구성 합니다. 이 Azure 응용 프로그램 서비스를 배포 하는 보다 많은 시간이 소요 되며이 자습서의 나머지 단계를 수행 해야 합니다.

먼저에 설명 된 모든 단계에 따라 [설치 및 실행된 IIS](/azure/virtual-machines/windows/quick-create-portal)합니다.

네트워크 보안 그룹에 포트 80을 여는 경우 원격 디버거에 대 한 포트 4022를 열 수도 있습니다. 이런 방식으로 나중에 열 필요가 없습니다.

### <a name="update-browser-security-settings-on-windows-server"></a>Windows Server에서 브라우저 보안 설정을 업데이트합니다

브라우저 보안 설정에 따라이 자습서에 설명 된 소프트웨어를 더 빠르게 다운로드할 수 있도록 브라우저에 다음 신뢰할 수 있는 사이트를 추가 하는 데 시간이 저장 될 수 있습니다. 이러한 사이트에 대 한 액세스를 필요할 수 있습니다.

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- visualstudio.com
- iis.net

Internet Explorer를 사용 하는 경우으로 이동 하 여 신뢰할 수 있는 사이트를 추가할 수 있습니다 **인터넷 옵션 > 보안 > 신뢰할 수 있는 사이트 > 사이트**합니다. 이러한 단계는 다른 브라우저도 서로 다릅니다. (My.visualstudio.com에서 이전 버전의 원격 디버거를 다운로드 해야 할 경우 신뢰할 수 있는 사이트 추가로 몇 가지는 로그인 해야 합니다.)

소프트웨어를 다운로드 하는 경우에 다양 한 웹 사이트 스크립트 및 리소스를 로드할 수 있는 권한을 부여 하는 요청 발생할 수 있습니다. 대부분의 경우에서 이러한 추가 리소스는 소프트웨어를 설치 하지 않아도 됩니다.

### <a name="install-aspnet-core-on-windows-server"></a>Windows Server에 ASP.NET Core를 설치 합니다.

1. 설치는 [.NET 핵심 Windows Server 호스팅](https://aka.ms/dotnetcore-2-windowshosting) 호스팅 시스템에서 번들입니다. 번들은.NET Core 런타임,.NET 핵심 라이브러리 및 ASP.NET Core 모듈을 설치 합니다. 더 자세한 지침에 대 한 참조 [를 IIS에 게시](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)합니다.

    > [!NOTE]
    > 시스템으로 지정 되지 않은 인터넷에 연결 하는 경우 구하여 설치는 *[Microsoft Visual c + + 2015 재배포 가능](https://www.microsoft.com/download/details.aspx?id=53840)* .NET 핵심 Windows Server 호스팅 번들을 설치 하기 전에.

3. 시스템을 다시 시작 (실행 또는 **net stop가 /y** 뒤 **net 시작 w3svc** 시스템 경로에 대 한 변경을 선택 하기 위해 명령 프롬프트에서).

## <a name="optional-install-web-deploy-36-for-hosting-servers-on-windows-server"></a>(선택 사항) 설치 웹 배포 Windows 서버에서 서버를 호스팅하기 위한 3.6

일부 시나리오에서는 빠르게 수 게시 설정 가져오기 Visual Studio의 배포 옵션을 수동으로 구성 하는 대신 합니다. 게시 설정 Visual Studio에서 게시 프로필을 구성 하는 대신, 참조를 가져오려면 선호 하는 경우 [게시 설정 하 고 IIS에 배포 하는 가져오기](../deployment/tutorial-import-publish-settings-iis.md)합니다. 그렇지 않은 경우이 항목의 상태를 유지 하 고 계속 읽어보세요. 가져오기에 대 한 문서를 완료 하는 경우 게시 설정 및 응용 프로그램을 성공적으로 배포 그런 다음이 항목으로 돌아와서을에서 섹션에서 시작 [원격 도구 다운로드](#BKMK_msvsmon)합니다.

### <a name="BKMK_install_webdeploy"></a> (선택 사항) 설치 웹 배포 Windows Server에서 3.6

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

### <a name="BKMK_deploy_asp_net"></a> Windows Server 컴퓨터에 ASP.NET 웹 사이트를 구성 합니다.

가져오는 경우 게시 설정,이 섹션을 건너뛸 수 있습니다.

1. **IIS(인터넷 정보 서비스) 관리자** 를 열고 **사이트**로 이동합니다.

2. **기본 웹 사이트** 노드를 마우스 오른쪽 단추로 클릭하고 **응용 프로그램 추가**를 선택합니다.

3. 설정의 **별칭** 필드를 **MyASPApp** 및 응용 프로그램 풀 필드를 **관리 코드 없음**합니다. 설정의 **실제 경로** 를 **C:\Publish** (나중에 배포할 ASP.NET 프로젝트).

4. IIS 관리자에서 선택한 사이트를 선택할 **사용 권한 편집**, 해당 IUSR, IIS_IUSRS, 또는 사용자 응용 프로그램 풀에는 읽기 및 실행 권한 가진 인증된 된 사용자에 대해 구성 되었는지 확인 합니다.

    액세스 권한이 있는이 사용자 중 하나가 표시 되지 않으면, IUSR 읽기 및 실행 권한이 있는 사용자로 추가 하는 단계를 통해 이동 합니다.

### <a name="bkmk_webdeploy"></a> (선택 사항) Visual Studio에서 Web Deploy를 사용 하 여 앱을 배포 및 게시

웹 플랫폼 설치 관리자를 사용 하 여 웹 배포를 설치한 경우 Visual Studio에서 직접 앱을 배포할 수 있습니다.

1. 상승 된 권한으로 Visual Studio를 시작 하 고 프로젝트를 엽니다.

    이 웹 배포를 사용 하 여 앱을 배포 하려면 필요할 수 있습니다.

2. **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

3. 에 대 한 **게시 대상 선택**선택, **Microsoft Azure 가상 컴퓨터** 클릭 **게시**합니다.

    ![RemoteDBG_Publish_IISl](../debugger/media/remotedbg_azure_vm_profile.png "RemoteDBG_Publish_IIS")

4. 대화 상자에서 이전에 만든 Azure VM을 선택 합니다.

4. Azure VM 및 IIS 설치에 대 한 수정 사항을 구성 매개 변수를 입력 합니다.

    ![RemoteDBG_Publish_WebDeployl](../debugger/media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    다음 단계는 호스트 이름에서 유효성을 검사 하려고 하면 해결 되지 않으면는 **서버** 텍스트 상자에서 IP 주소를 지정 하십시오. 에 포트 80을 사용 하면는 **서버** 텍스트 상자의 하 고 포트 80이 고 방화벽에서 열려 있는지 확인 합니다.

6. 클릭 **다음**, 선택는 **디버그** 구성을 선택 하 고 **대상에서 추가 파일 제거** 아래는 **파일 게시** 옵션.

5. 클릭 **Prev**를 선택한 후 **유효성 검사**합니다. 연결 설정의 유효성을 검사 하는 경우에 게시 하도록 시도할 수 있습니다.

6. 클릭 **게시** 에서는 앱을 게시 합니다.

    출력 탭 게시 성공 하 고 브라우저 앱을 열고는 경우를 설명 합니다.

    웹 배포에 대해 언급 오류가 발생할 경우 웹 배포 설치 단계를 다시 확인 하 고 있는지는 [올바른 포트가 열려 있는지](#bkmk_openports) 서버에 있습니다.

    성공적으로 배포 응용 프로그램 제대로 실행 되지 않는 경우는 IIS와 Visual Studio 프로젝트를 모두 사용 하는 동일한 버전의 ASP.NET 다시 확인 합니다. 즉 하지 문제가, IIS 구성 또는 웹 사이트 구성에 문제가 있을 수 있습니다. Windows 서버에서 웹 사이트에서 IIS 더 구체적인 오류 메시지에 대 한 연 후 이전 단계를 다시 확인 합니다.

### <a name="optional-publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>(선택 사항) Visual Studio에서 로컬 폴더에 게시 하 여 앱을 배포 및 게시

웹 배포는 사용 하지 않는 경우에 게시 하 고 파일 시스템 또는 기타 도구를 사용 하 여 앱을 배포 해야 합니다. 파일 시스템을 사용 하 여 패키지를 만드는 작업부터 시작 하 고 패키지를 수동으로 배포 하거나 XCopy, RoboCopy, PowerShell 등 다른 도구를 사용 합니다. 이 섹션에서는 웹 배포를 사용 하지 않는 경우 패키지를 수동으로 복사 하려는 한다고 가정 합니다.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

### <a name="BKMK_msvsmon"></a> 다운로드 하 여 Windows Server에서 원격 도구 설치

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a> Windows Server에서 원격 디버거 설정

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> 추가 사용자에 대 한 사용 권한을 추가 하는 인증 모드를 변경 하거나 원격 디버거에 대 한 포트 번호에 필요한 경우 참조 [원격 디버거 구성](../debugger/remote-debugging.md#configure_msvsmon)합니다.

### <a name="BKMK_attach"></a> Visual Studio 컴퓨터에서 ASP.NET 응용 프로그램에 연결

1. Visual Studio 컴퓨터에서 열고는 **MyASPApp** 솔루션입니다.
2. Visual Studio에서 클릭 **디버그 > 프로세스에 연결** (Ctrl + Alt + P).

    > [!TIP]
    > Visual Studio 2017에 다시 연결할 수는 동일한 프로세스를 이전에 사용 하 여 연결할 **디버그 > 프로세스에 다시 연결 중...** (Shift+Alt+P). 

3. 한정자 필드를 설정  **\<원격 컴퓨터 이름 >: 4022**합니다.
4. **새로 고침**가 있어야 합니다.
    일부 프로세스가 **사용 가능한 프로세스** 창에 표시됩니다.

    모든 프로세스가 표시 되지 않으면, (포트는 필수) 원격 컴퓨터 이름 대신 IP 주소를 사용해 보십시오. 사용할 수 있습니다 `ipconfig` IPv4 주소를 얻기 위해 명령줄에 있습니다.

    사용 하려는 경우는 **찾을** 단추를 해야 할 수 있습니다 [UDP 포트 3702 열고](#bkmk_openports) 서버의 합니다.

5. **모든 사용자의 프로세스 표시**를 선택합니다.
6. 빠르게 찾기 위해 프로세스 이름의 첫 글자를 입력 **dotnet.exe** (용 ASP.NET Core).
    >참고: ASP.NET Core 응용 프로그램에 대 한 이전 프로세스 이름이 dnx.exe 이었습니다.

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess_aspnetcore.png "RemoteDBG_AttachToProcess")

7. **연결**을 클릭합니다.

8. 원격 컴퓨터의 웹 사이트를 엽니다. 브라우저에서로 이동 **http://\<원격 컴퓨터 이름 >** 합니다.
    
    ASP.NET 웹 페이지가 표시됩니다.
9. 실행 중인 ASP.NET 응용 프로그램에서 링크를 클릭 하 여 **에 대 한** 페이지.

    Visual Studio에서 중단점이 적중됩니다.

### <a name="bkmk_openports"></a> 문제 해결: Windows Server에 필요한 포트를 열려면

대부분의 설치 프로그램에서 ASP.NET와 원격 디버거 설치를 통해 필요한 포트가 열립니다. 그러나 배포 문제를 해결 하는 경우 방화벽 뒤에 있는 응용 프로그램은 호스트에서 올바른 포트가 열려 있는지 확인 해야 합니다.

Azure VM에서 포트를 열어야 통해는 [네트워크 보안 그룹](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80)합니다. 

필요한 포트:

- 80-IIS에 대 한 필요합니다.
- 4022-Visual Studio 2017 원격 디버깅을 위해 필요 합니다. (참조 [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md) 자세한 정보에 대 한).
- UDP 3702-(선택 사항) 검색 포트 수 있습니다는 **찾을** 단추 Visual Studio에서 원격 디버거를 연결 합니다.

또한 이러한 포트는 ASP.NET 설치도 이미 열려 해야 합니다.
- 8172-(웹 배포를 Visual Studio에서 앱을 배포 하는 데 필요한 선택 사항)

