---
title: "원격 디버깅 원격 IIS 컴퓨터에 ASP.NET | Microsoft Docs"
ms.custom: remotedebugging
ms.date: 07/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cb339b5-3caf-4755-aad1-4a5da54b2a23
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: aspnet
ms.openlocfilehash: 35b8cd394881ba5bf075044d30aee17ab6a321c4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="remote-debug-aspnet-on-a-remote-iis-computer"></a>원격 IIS 컴퓨터에 ASP.NET 원격 디버그
IIS에 배포 된 ASP.NET 응용 프로그램을 디버깅 하려면 설치 및 응용 프로그램을 배포한 컴퓨터에서 원격 도구를 실행 하 고 Visual Studio에서 실행 중인 앱에 연결 합니다.

![원격 디버거 구성 요소](../debugger/media/remote-debugger-aspnet.png "Remote_debugger_components")

이 설정 및 Visual Studio 2017 ASP.NET MVC 4.5.2 응용 프로그램을 구성 하 고, IIS에 배포 하 고 Visual Studio에서 원격 디버거를 연결 하는 방법을 설명 합니다. 원격 디버깅 ASP.NET Core, 참조 [IIS 컴퓨터에 있는 원격 디버깅 ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)합니다. 배포 하 고 Azure를 사용 하 여 IIS에서 디버깅할 수도 있습니다. 자세한 내용은 참조 [Azure에서 원격 디버깅](../debugger/remote-debugging-azure.md)합니다.

이러한 절차 이러한 서버 구성에서 테스트 되었으며:
* Windows Server 2012 R2 및 IIS 8 (Windows Server 2008 R2에 대 한 서버 단계는 다른)

## <a name="requirements"></a>요구 사항

원격 디버거는 Windows Server 2008 서비스 팩 2부터 Windows Server에서 지원 됩니다. 요구 사항 목록은 전체 참조 [요구 사항](../debugger/remote-debugging.md#requirements_msvsmon)합니다.

> [!NOTE]
> 프록시를 통해 연결 된 두 컴퓨터 간에 디버깅이 지원 되지 않습니다. 국가 간 대기 시간이 긴 또는 전화 접속, 인터넷 등 낮은 대역폭 연결을 통해 또는 인터넷을 통해 디버깅 권장 되지 않습니다 및 실패 하거나 느리고 수입니다.

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>ASP.NET 4.5.2를 만들려면 Visual Studio 컴퓨터에 응용 프로그램
  
1. 새 MVC ASP.NET 응용 프로그램을 만듭니다. (**파일 > 새로 만들기 > 프로젝트**을 선택한 후 * * Visual C# > 웹 > ASP.NET 웹 응용 프로그램입니다. **ASP.NET 4.5.2** 템플릿 섹션에서 **MVC**를 선택합니다. 있는지 확인 **Docker 지원 활성화** 선택 하지 않으면 해당 **인증** 로 설정 되어 **인증 안 함**합니다. 프로젝트 이름을 **MyASPApp**.)

2. HomeController.cs 파일을 열고 `About()` 메서드에 중단점을 설정합니다.

## <a name="bkmk_configureIIS"></a>설치 하 고 Windows 서버에서 IIS를 구성 합니다.

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Windows Server에서 브라우저 보안 설정을 업데이트합니다

보안 설정에 따라은이 자습서에 설명 된 소프트웨어를 쉽게 다운로드할 수 있도록 브라우저에 다음 신뢰할 수 있는 사이트를 추가 하는 데 시간이 저장 될 수 있습니다. 이러한 사이트에 대 한 액세스를 필요할 수 있습니다.

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- visualstudio.com

Internet Explorer를 사용 하는 경우으로 이동 하 여 신뢰할 수 있는 사이트를 추가할 수 있습니다 **인터넷 옵션 > 보안 > 신뢰할 수 있는 사이트 > 사이트**합니다. 이러한 단계는 다른 브라우저도 서로 다릅니다. (My.visualstudio.com에서 이전 버전의 원격 디버거를 다운로드 해야 할 경우 신뢰할 수 있는 사이트 추가로 몇 가지는 로그인 해야 합니다.)

소프트웨어를 다운로드 하는 경우에 다양 한 웹 사이트 스크립트 및 리소스를 로드할 수 있는 권한을 부여 하는 요청 발생할 수 있습니다. 대부분의 경우에서 이러한 추가 리소스는 소프트웨어를 설치 하지 않아도 됩니다.

## <a name="BKMK_deploy_asp_net"></a>Windows Server에 ASP.NET 4.5를 설치 합니다.

IIS에서 ASP.NET을 설치 하는 데 필요한 자세한 정보 참조 [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)합니다.

1. 웹 플랫폼 설치 관리자 (WebPI)를 사용 하 여 ASP.NET 4.5를 설치 하려면 (Windows Server 2012 r 2의 서버 노드에서 선택 **새 웹 플랫폼 구성 요소 가져오기** 한 ASP.NET에 대 한 다음 검색)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > Windows Server 2008 r 2를 사용 하는 경우이 명령을 사용 하는 ASP.NET 4를 설치 합니다.

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe ir**

2. 시스템을 다시 시작 (실행 또는 **net stop가 /y** 뒤 **net 시작 w3svc** 시스템 경로에 대 한 변경을 선택 하기 위해 명령 프롬프트에서).

## <a name="BKMK_install_webdeploy"></a>(선택 사항) 설치 웹 배포 Windows Server에서 3.6

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="BKMK_deploy_asp_net"></a>Windows Server 컴퓨터에 ASP.NET 웹 사이트를 구성 합니다.

1. Windows 탐색기를 열고 새 폴더를 만들 **C:\Publish**, ASP.NET 프로젝트를 나중에 배포 됩니다 있습니다.

2. 열기는 **인터넷 정보 서비스 (IIS) 관리자**합니다. (서버 관리자의 왼쪽된 창에서 선택 **IIS**합니다. 서버를 마우스 오른쪽 단추로 클릭 하 고 선택 **인터넷 정보 서비스 (IIS) 관리자**.)

3. 아래 **연결** 왼쪽된 창에서로 이동 **사이트**합니다.

4. 선택 된 **기본 웹 사이트**, 선택 **기본 설정**, 설정는 **실제 경로** 를 **C:\Publish**합니다.

5. **기본 웹 사이트** 노드를 마우스 오른쪽 단추로 클릭하고 **응용 프로그램 추가**를 선택합니다.

6. 설정의 **별칭** 필드를 **MyASPApp**, 응용 프로그램 풀 기본값을 그대로 (**DefaultAppPool**)을 설정 하 고는 **실제 경로** 를 **C:\Publish**합니다.

7. 아래 **연결**선택, **응용 프로그램 풀**합니다. 열기 **DefaultAppPool** 응용 프로그램 풀 필드를 설정 하 고 **ASP.NET v4.0** (ASP.NET 4.5는 응용 프로그램 풀에 대 한 옵션이 아님).

8. IIS 관리자에서 선택한 사이트를 선택할 **사용 권한 편집**, 해당 IUSR, IIS_IUSRS, 또는 사용자 응용 프로그램 풀에는 읽기 및 실행 권한 가진 인증된 된 사용자에 대해 구성 되었는지 확인 합니다. 이러한 사용자의 아무 특성도 없으면 IUSR 읽기 및 실행 권한이 있는 사용자로 추가 합니다.

## <a name="bkmk_webdeploy"></a>(선택 사항) Visual Studio에서 Web Deploy를 사용 하 여 앱을 배포 및 게시

[!INCLUDE [remote-debugger-deploy-app-web-deploy](../debugger/includes/remote-debugger-deploy-app-web-deploy.md)]

섹션에서 확인할 할 수는 또한 [포트 문제 해결](#bkmk_openports)합니다.

## <a name="optional-publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>(선택 사항) Visual Studio에서 로컬 폴더에 게시 하 여 앱을 배포 및 게시

게시 하 고 파일 시스템 또는 기타 도구를 사용 하 여 앱을 배포할 수도 있습니다.

1. (ASP.NET 4.5.2) Web.config 파일에 올바른 버전의.NET Framework 표시 되어 있는지 확인 합니다.  예를 들어 ASP.NET 4.5.2를 대상으로 하는 경우이 버전은 web.config에 나열 되는지 확인 합니다.
  
    ```xml
    <system.web>
      <compilation debug="true" targetFramework="4.5.2" />
      <httpRuntime targetFramework="4.5.2" />
      <httpModules>
        <add name="ApplicationInsightsWebTracking" type="Microsoft.ApplicationInsights.Web.ApplicationInsightsHttpModule, Microsoft.AI.Web" />
      </httpModules>
    </system.web>
  
    ```

    예를 들어 버전 4.5.2 대신 ASP.NET 4를 설치 하는 경우에 4.0 해야 합니다.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

## <a name="BKMK_msvsmon"></a>다운로드 하 여 Windows Server에서 원격 도구 설치

이 자습서에서는 Visual Studio 2017 사용 했습니다.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> 일부 시나리오에서는 파일 공유에서 원격 디버거를 실행 하는 가장 효율적인 수 있습니다. 자세한 내용은 참조 [파일 공유에서 원격 디버거를 실행](../debugger/remote-debugging.md#fileshare_msvsmon)합니다.
  
## <a name="BKMK_setup"></a>Windows Server에서 원격 디버거 설정

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> 추가 사용자에 대 한 사용 권한을 추가 하는 인증 모드를 변경 하거나 원격 디버거에 대 한 포트 번호에 필요한 경우 참조 [원격 디버거 구성](../debugger/remote-debugging.md#configure_msvsmon)합니다.

원격 디버거를 서비스로 실행에 대 한 정보를 참조 하십시오. [원격 디버거를 서비스로 실행](../debugger/remote-debugging.md#bkmk_configureService)합니다.

## <a name="BKMK_attach"></a> Visual Studio 컴퓨터에서 ASP.NET 응용 프로그램에 연결

1. Visual Studio 컴퓨터에서 열고는 **MyASPApp** 솔루션입니다.
2. Visual Studio에서 클릭 **디버그 > 프로세스에 연결** (Ctrl + Alt + P).

    > [!TIP]
    > Visual Studio 2017에 다시 연결할 수 있습니다 이전에 사용 하 여 연결할 동일한 프로세스에 **디버그 > 프로세스에 다시 연결 중...** (Shift + Alt + P)입니다. 

3. 한정자 필드를 설정  **\<원격 컴퓨터 이름 >: 4022**합니다.
4. 클릭 **새로 고침**합니다.
    일부 프로세스가 **사용 가능한 프로세스** 창에 표시됩니다.

    모든 프로세스가 표시 되지 않으면, (포트는 필수) 원격 컴퓨터 이름 대신 IP 주소를 사용해 보십시오. 사용할 수 있습니다 `ipconfig` IPv4 주소를 얻기 위해 명령줄에 있습니다.

5. **모든 사용자의 프로세스 표시**를 선택합니다.
6. 빠르게 찾기 위해 프로세스 이름의 첫 글자를 입력 **w3wp.exe** ASP.NET 4.5에 대 한 합니다.

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess.png "RemoteDBG_AttachToProcess")

7. 클릭 **연결**

8. 원격 컴퓨터의 웹 사이트를 엽니다. 브라우저에서로 이동 **http://\<원격 컴퓨터 이름 >**합니다.
    
    ASP.NET 웹 페이지가 표시됩니다.
9. 실행 중인 ASP.NET 응용 프로그램에서 링크를 클릭 하 여 **에 대 한** 페이지.

    Visual Studio에서 중단점이 적중됩니다.

## <a name="bkmk_openports"></a>문제 해결: Windows Server에 필요한 포트를 열려면

대부분의 설치 프로그램에서 ASP.NET와 원격 디버거 설치를 통해 필요한 포트가 열립니다. 그러나 포트가 열려 있는지 확인 해야 합니다.

> [!NOTE]
> Azure VM에서 포트를 열어야 통해는 [네트워크 보안 그룹](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80)합니다. 

필요한 포트:

- 80-IIS에 대 한 필요합니다.
- 8172-(웹 배포를 Visual Studio에서 앱을 배포 하는 데 필요한 선택 사항)
- 4022-Visual Studio 2017 원격 디버깅을 위해 필요 합니다. (참조 [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md) 자세한 정보에 대 한 합니다.
- UDP 3702-(선택 사항) 검색 포트 수 있습니다는 **찾을** 단추 Visual Studio에서 원격 디버거를 연결 합니다.

1. Windows Server에서 포트를 열려면는 **시작** 메뉴, 검색할 **고급 보안이 포함 된 Windows 방화벽**합니다.

2. 그런 다음 선택 **인바운드 규칙 > 새 규칙 > 포트**합니다. 선택 **다음** 고 **특정 로컬 포트**, 포트 번호를 입력, 클릭 **다음**, 다음 **연결 허용**, 다음을 클릭 하 고 이름을 추가 합니다 (**IIS**, **웹 배포**, 또는 **msvsmon**) 인바운드 규칙에 대 한 합니다.

    Windows 방화벽 구성에 대 한 자세한 내용은 참조 [원격 디버깅용 Windows 방화벽을 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)합니다.

3. 필요한 포트에 대 한 추가 규칙을 만듭니다.