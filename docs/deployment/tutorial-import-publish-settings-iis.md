---
title: 에 게시를 가져와서 IIS 게시 설정
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to IIS
ms.date: 05/07/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b023349454f71835e13e7cc891b8be92b90c153f
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="publish-an-application-to-iis-by-importing-publish-settings-in-visual-studio"></a>IIS에 응용 프로그램을 가져와서 게시 Visual Studio에서 게시 설정

사용할 수는 **게시** 가져오도록 게시 설정 하 고 다음 앱을 배포 합니다. 이 문서에서는 사용 하 여 게시 IIS에 대 한 설정 하지만 사용할 수 있습니다를 가져오려면 비슷한 단계에 대 한 설정을 게시 [Azure 앱 서비스](../deployment/tutorial-import-publish-settings-azure.md)합니다. 일부 시나리오에서 사용 하 여의 게시 설정 프로필을 수동으로 IIS에 Visual Studio의 각 설치에 대 한 배포를 구성할 때 보다 더 빠를 수 있습니다.

이 단계는 Visual Studio에서 ASP.NET, ASP.NET Core 및.NET Core 응용 프로그램에 적용 합니다. Visual Studio 2017 15.6 버전에 해당 하는 단계입니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 게시 설정 파일을 생성할 수 있도록 IIS를 구성 합니다.
> * 게시 설정 파일 만들기
> * Visual Studio에 게시 설정 파일 가져오기
> * IIS에 응용 프로그램 배포

게시 설정 파일 (*\*.publishsettings*)은 게시 프로필 다릅니다 (*\*.pubxml*) Visual Studio에서 만든 합니다. 게시 설정 파일을 IIS 또는 Azure 앱 서비스 또는 수동으로 작성할 수 있습니다, 만들어지고 Visual Studio로 가져올 수 있습니다.

> [!NOTE]
> Visual Studio 게시 프로필을 복사 해야 하는 경우 (\*.pubxml 파일)를 다른 Visual Studio의 한 설치에서 게시 프로필을 찾을 수 있습니다  *\<profilename\>.pubxml*, 에  *\\< p r o j\>\Properties\PublishProfiles* 관리 되는 프로젝트 형식에 대 한 폴더입니다. 웹 사이트의 경우에서 찾아봅니다는 *\App_Data* 폴더입니다. 게시 프로필에는 MSBuild XML 파일입니다.

## <a name="prerequisites"></a>전제 조건

* Visual Studio가 설치 되어 있어야 하며 **ASP.NET** 및 **.NET Framework** 개발 작업 합니다. .NET Core 응용 프로그램에 대해도 필요는 **.NET Core** 작업 합니다.

    아직 Visual Studio를 설치하지 않은 경우 [여기](http://www.visualstudio.com)에서 평가판을 설치합니다.

    이 문서의 단계는 Visual Studio 2017 기반

* IIS 8.0 웹 서버 역할이 제대로 구성 되어 있는 Windows Server 2012를 실행 하는 컴퓨터를 IIS에서 게시 설정 파일을 생성 하려면 있어야 하며 ASP.NET Core 또는 ASP.NET 4.5를 설치 합니다. ASP.NET Core 참조 [를 IIS에 게시](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)합니다. ASP.NET 4.5에 대해 참조 [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)합니다.

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Visual Studio에서 새 ASP.NET 프로젝트 만들기

1. Visual Studio를 실행 하는 컴퓨터에서 선택 **파일 > 새 프로젝트**합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **웹**, 한 다음 가운데 창에서 하나를 선택 하 고 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 또는 (C#만) **ASP.NET Core 웹 응용 프로그램**, 클릭 하 고 **확인**합니다.

    지정 된 프로젝트 템플릿이 보이지 않으면 클릭는 **Open Visual Studio 설치 관리자** 의 왼쪽된 창에서 링크는 **새 프로젝트** 대화 상자. Visual Studio 설치 관리자가 시작됩니다. 이 문서를 설치 해야는 필요한 Visual Studio 작업의 필수 구성 요소를 참조 하십시오.

1. 중 하나를 선택 **MVC** (.NET Framework) 또는 **웹 응용 프로그램 (모델-뷰-컨트롤러)** (.NET Core)에 있는지 확인 하 고 **인증 안 함** 을 선택한 다음 클릭 **확인**합니다.

1. 같은 이름을 입력 **MyWebApp** 클릭 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

1. 선택 **빌드 > 솔루션 빌드** 프로젝트를 빌드합니다.

## <a name="install-and-configure-web-deploy-on-windows-server"></a>설치 하 고 Windows 서버에 웹 배포를 구성 합니다.

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Windows Server에는 IIS에서 게시 설정 파일 만들기

1. IIS에서 마우스 오른쪽 단추로 클릭는 **기본 웹 사이트**, 선택 **배포** > **구성할 웹 배포 게시**합니다.

    ![웹 배포 구성을 구성합니다](../deployment/media/tutorial-configure-web-deploy-publishing.png)

1. 에 **구성할 웹 배포 게시** 대화 상자에서 설정을 검토 합니다.

1. 클릭 **설치**합니다.

    에 **결과** 패널 권한 액세스 하는 출력에 표시 된에 부여 되어 있고 지정된 된 사용자 파일을는 *.publishsettings* 에 표시 된 위치에 생성 된 파일 확장명은 대화 상자입니다.

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <publishData>
      <publishProfile
        publishUrl="https://myhostname:8172/msdeploy.axd"
        msdeploySite="Default Web Site"
        destinationAppUrl="http://myhostname:80/"
        mySQLDBConnectionString=""
        SQLServerDBConnectionString=""
        profileName="Default Settings"
        publishMethod="MSDeploy"
        userName="myhostname\myusername" />
    </publishData>
    ```

    Windows Server 및 IIS 구성에 따라 다른 값이 표시 됩니다. 표시 되는 값에 대 한 몇 가지 세부 사항은 다음과 같습니다.

    * *msdeploy.axd* 파일에서 참조 되는 `publishUrl` 특성이 웹 배포에 대 한 동적으로 생성 된 HTTP 처리기 파일입니다. (테스트 목적으로 `http://myhostname:8172` 은 일반적으로 작동 합니다.)
    * `publishUrl` 포트는 일반적으로 웹 배포에 대 한 기본값, 8172 포트로 설정 됩니다.
    * `destinationAppUrl` 포트는 일반적으로 IIS에 대 한 기본값은 포트 80로 설정 됩니다.
    * 이후 단계에서 호스트 이름을 사용 하 여 Visual Studio에서 원격 호스트에 연결할 수 없는 경우 호스트 이름 대신 IP 주소를 테스트 합니다.

    > [!NOTE]
    > Azure VM에서 실행 되는 IIS에 게시 하는 경우 웹 배포 및 IIS 포트를 네트워크 보안 그룹에 열려 있어야 합니다. 자세한 내용은 참조 [설치 및 실행된 IIS](/azure/virtual-machines/windows/quick-create-portal#open-port-80-for-web-traffic)합니다.

1. Visual Studio를 실행 중인 컴퓨터에이 파일을 복사 합니다.

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio에서 게시 설정 가져오기 및 배포

1. ASP.NET 프로젝트가 Visual Studio에서 열려 있는 컴퓨터에서 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시**합니다.

1. 모든 게시 프로필을 이전에 구성한 경우는 **게시** 창이 나타납니다. 클릭 **새 프로필 만들기**합니다.

1. 에 **게시 대상 선택** 대화 상자를 클릭 **프로필 가져오기**합니다.

    ![선택 게시](../deployment/media/tutorial-publish-tool-import-profile.png)

1. 이전 섹션에서 만든 게시 설정 파일의 위치로 이동 합니다.

1. 에 **게시 설정 파일 가져오기** 대화 상자, 탐색 하 고 이전 섹션에서 만든 프로필을 선택한 클릭 **열려**합니다.

    Visual Studio는 배포 프로세스를 시작 하 고 진행률 및 결과 출력 창에 표시 합니다.

    모든 배포 오류가 발생 하면 클릭 **설정을** 설정을 편집할 수 있습니다. 설정을 수정 하 고 클릭 **유효성 검사** 새 설정을 테스트 합니다.

    ![게시 도구에는 설정 편집](../deployment/media/tutorial-configure-publish-settings-in-tool.png)

## <a name="next-steps"></a>다음 단계

게시 설정 파일을 만든이 자습서에서는 Visual Studio로 가져올을 IIS에 ASP.NET 응용 프로그램을 배포 합니다.

> [!div class="nextstepaction"]
> [배포 소개](../deployment/deploying-applications-services-and-components.md)
