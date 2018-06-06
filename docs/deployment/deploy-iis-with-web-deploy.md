---
title: 웹 배포를 사용 하 여 IIS에 ASP.NET 배포
ms.custom: ''
ms.date: 06/04/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
ms.assetid: 9cb339b5-3caf-4755-aad1-4a5da54b2a23
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: a63d9947f544ddff1de81aaf34ed62c9646fba3d
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34794201"
---
# <a name="deploy-aspnet-to-a-remote-iis-computer-using-web-deploy-in-visual-studio"></a>ASP.NET 웹 배포를 사용 하 여 Visual Studio에서 원격 IIS 컴퓨터에 배포

이 문서에서는 설정 및 Visual Studio 2017 ASP.NET MVC 4.5.2 응용 프로그램을 구성 하 고 IIS에 배포 하는 방법에 설명 합니다. 이 문서는 Windows 서버에 IIS의 기본 구성 설정 하 고 Visual Studio에서 앱을 배포 하는 단계를 포함 합니다. 이러한 단계는 서버 구성 요소가 설치 되어 있는지 필수 있고 하면 배포할 준비가 되어 있는지 확인 하기 위해 포함 합니다. ASP.NET Core 응용 프로그램을 배포 하는 경우 몇 가지 단계가 서로 다릅니다. ASP.NET Core 응용 프로그램을 배포 하려면 참조 [게시 설정을 가져와서 IIS에 응용 프로그램 게시](../deployment/tutorial-import-publish-settings-iis.md) 지침에 대 한 합니다. ASP.NET 및 ASP.NET Core 일부 시나리오에서는 것이 더 빠릅니다를 배포 하려면 IIS를 가져와서 게시 설정 합니다.

이러한 절차 이러한 서버 구성에서 테스트 되었으며:
* Windows Server 2012 R2 및 IIS 8 (Windows Server 2008 R2에 대 한 서버 단계는 다른)

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>ASP.NET 4.5.2를 만들려면 Visual Studio 컴퓨터에 응용 프로그램
  
1. Visual Studio를 실행 하는 컴퓨터에서 선택 **파일 > 새 프로젝트**합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **웹**, 한 다음 가운데 창에서 하나를 선택 하 고 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 클릭 하 고 **확인**합니다.

    지정 된 프로젝트 템플릿이 보이지 않으면 클릭는 **Open Visual Studio 설치 관리자** 의 왼쪽된 창에서 링크는 **새 프로젝트** 대화 상자. Visual Studio 설치 관리자가 시작됩니다. 이 문서를 설치 해야는 필요한 Visual Studio 작업의 필수 구성 요소를 참조 하십시오.

1. 선택 **MVC** (.NET Framework) 되어 있는지 확인 **인증 안 함** 을 선택한 다음 클릭 **확인**합니다.

1. 같은 이름을 입력 **MyWebApp** 클릭 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

1. 선택 **빌드 > 솔루션 빌드** 프로젝트를 빌드합니다.

## <a name="bkmk_configureIIS"></a> 설치 하 고 Windows 서버에서 IIS를 구성 합니다.

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Windows Server에서 브라우저 보안 설정을 업데이트합니다

(기본적으로 사용 됩니다) Internet Explorer에서 보안 강화 구성을 사용 하면 일부 도메인을 웹 서버 구성 요소 중 일부를 다운로드할 수 있도록를 신뢰할 수 있는 사이트로 추가 해야 할 수 있습니다. 로 이동 하 여 신뢰할 수 있는 사이트 추가 **인터넷 옵션 > 보안 > 신뢰할 수 있는 사이트 > 사이트**합니다. 다음 도메인을 추가 합니다.

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- iis.net

소프트웨어를 다운로드 하는 경우에 다양 한 웹 사이트 스크립트 및 리소스를 로드할 수 있는 권한을 부여 하는 요청 발생할 수 있습니다. 필요 하지 않지만 프로세스를 간소화 하기 위해 클릭 이러한 리소스 중 일부 **추가** 대화 상자가 나타나면 합니다.

## <a name="BKMK_deploy_asp_net"></a> Windows Server에 ASP.NET 4.5를 설치 합니다.

IIS에서 ASP.NET을 설치 하는 데 필요한 자세한 정보 참조 [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)합니다.

1. 서버 관리자의 왼쪽된 창에서 선택 **IIS**합니다. 서버를 마우스 오른쪽 단추로 클릭 하 고 선택 **인터넷 정보 서비스 (IIS) 관리자**합니다.

1. 웹 플랫폼 설치 관리자 (WebPI)를 사용 하 여 ASP.NET 4.5를 설치 하려면 (Windows Server 2012 r 2의 서버 노드에서 선택 **새 웹 플랫폼 구성 요소 가져오기** 한 ASP.NET에 대 한 다음 검색)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > Windows Server 2008 r 2를 사용 하는 경우이 명령을 사용 하는 ASP.NET 4를 설치 합니다.

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. 시스템을 다시 시작 (실행 또는 **net stop가 /y** 뒤 **net 시작 w3svc** 시스템 경로에 대 한 변경을 선택 하기 위해 명령 프롬프트에서).

## <a name="BKMK_install_webdeploy"></a> 설치 웹 배포 Windows Server에서 3.6

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="BKMK_deploy_asp_net"></a> Windows Server 컴퓨터에 ASP.NET 웹 사이트를 구성 합니다.

1. Windows 탐색기를 열고 새 폴더를 만들 **C:\Publish**, ASP.NET 프로젝트를 나중에 배포 됩니다 있습니다.

2. 열려 있지 않으면 엽니다는 **인터넷 정보 서비스 (IIS) 관리자**합니다. (서버 관리자의 왼쪽된 창에서 선택 **IIS**합니다. 서버를 마우스 오른쪽 단추로 클릭 하 고 선택 **인터넷 정보 서비스 (IIS) 관리자**.)

3. 아래 **연결** 왼쪽된 창에서로 이동 **사이트**합니다.

4. 선택 된 **기본 웹 사이트**, 선택 **기본 설정**, 설정는 **실제 경로** 를 **C:\Publish**합니다.

5. **기본 웹 사이트** 노드를 마우스 오른쪽 단추로 클릭하고 **응용 프로그램 추가**를 선택합니다.

6. 설정의 **별칭** 필드를 **MyASPApp**, 응용 프로그램 풀 기본값을 그대로 (**DefaultAppPool**)을 설정 하 고는 **실제 경로** 를 **C:\Publish**합니다.

7. 아래 **연결**선택, **응용 프로그램 풀**합니다. 열기 **DefaultAppPool** 응용 프로그램 풀 필드를 설정 하 고 **ASP.NET v4.0** (ASP.NET 4.5는 응용 프로그램 풀에 대 한 옵션이 아님).

8. IIS 관리자에서 선택한 사이트를 선택할 **사용 권한 편집**, 해당 IUSR, IIS_IUSRS, 또는 사용자 응용 프로그램 풀에는 읽기 및 실행 권한 가진 인증된 된 사용자에 대해 구성 되었는지 확인 합니다. 이러한 사용자의 아무 특성도 없으면 IUSR 읽기 및 실행 권한이 있는 사용자로 추가 합니다.

## <a name="bkmk_webdeploy"></a> Visual Studio에서 Web Deploy를 사용 하 여 앱을 배포 및 게시

[!INCLUDE [deploy-app-web-deploy](../deployment/includes/deploy-app-web-deploy.md)]

섹션에서 확인할 할 수는 또한 [포트 문제 해결](#bkmk_openports)합니다.

## <a name="bkmk_openports"></a> 문제 해결: Windows Server에 필요한 포트를 열려면

대부분의 설치 프로그램에서 ASP.NET 및 웹 배포 설치를 통해 필요한 포트가 열립니다. 그러나 포트가 열려 있는지 확인 해야 합니다.

> [!NOTE]
> Azure VM에서 포트를 열어야 통해는 [네트워크 보안 그룹](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80)합니다. 

필요한 포트:

* 80-IIS에 대 한 필요합니다.
* 8172-Visual Studio에서 앱을 배포 하려면 웹 배포에 필요한 합니다.

1. Windows Server에서 포트를 열려면는 **시작** 메뉴, 검색할 **고급 보안이 포함 된 Windows 방화벽**합니다.

2. 그런 다음 선택 **인바운드 규칙 > 새 규칙 > 포트**합니다. 선택 **다음** 고 **특정 로컬 포트**, 포트 번호를 입력, 클릭 **다음**, 다음 **연결 허용**, 다음을 클릭 하 고 이름을 추가 합니다 (**IIS**, **웹 배포**, 또는 **msvsmon**) 인바운드 규칙에 대 한 합니다.

    Windows 방화벽 구성에 대 한 자세한 내용은 참조 [원격 디버깅용 Windows 방화벽을 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)합니다.

3. 필요한 포트에 대 한 추가 규칙을 만듭니다.

## <a name="next-steps"></a>다음 단계

게시 설정 파일을 만든이 자습서에서는 Visual Studio로 가져올을 IIS에 ASP.NET 응용 프로그램을 배포 합니다. 가져와서 배포할 수도 게시 설정 합니다.

> [!div class="nextstepaction"]
> [에 배포를 가져와서 IIS 게시 설정](../deployment/tutorial-import-publish-settings-iis.md)