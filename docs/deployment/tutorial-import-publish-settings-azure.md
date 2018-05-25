---
title: 가져와서 Azure에 게시 게시 설정
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to Azure App Service
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
ms.openlocfilehash: 2cf6c17f3017bb1021423b19b32b36749fe0744d
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2018
---
# <a name="publish-an-application-to-azure-app-service-by-importing-publish-settings-in-visual-studio"></a>Azure 앱 서비스에 응용 프로그램을 가져와서 게시 Visual Studio에서 게시 설정

사용할 수는 **게시** 가져오도록 게시 설정 하 고 다음 앱을 배포 합니다. 이 문서에서는 사용 하 여 Azure 앱 서비스에 대 한 설정을 게시 하지만 사용할 수 있습니다를 가져오려면 유사한 단계 게시 설정에서 [IIS](../deployment/tutorial-import-publish-settings-iis.md)합니다. 일부 시나리오에서 사용 하 여의 게시 설정 프로필을 수동으로 Visual Studio의 각 설치에 대 한 서비스에 대 한 배포를 구성할 때 보다 더 빠를 수 있습니다.

이 단계는 Visual Studio에서 ASP.NET, ASP.NET Core 및.NET Core 응용 프로그램에 적용 합니다. 가져올 수도 있습니다 게시에 대 한 설정 [Python](/visualstudio/python/publishing-python-web-applications-to-azure-from-visual-studio) 앱. Visual Studio 2017 15.6 버전에 해당 하는 단계입니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * Azure 앱 서비스에서 게시 설정 파일을 생성 합니다.
> * Visual Studio에 게시 설정 파일 가져오기
> * Azure 앱 서비스에 앱을 배포 합니다.

게시 설정 파일 (*\*.publishsettings*)은 게시 프로필 다릅니다 (*\*.pubxml*) Visual Studio에서 만든 합니다. 게시 설정 파일을 Azure 앱 서비스에 의해 만들어지고 Visual Studio로 가져올 수 있습니다.

> [!NOTE]
> Visual Studio 게시 프로필을 복사 해야 하는 경우 (*\*.pubxml* 파일)를 다른 Visual Studio의 한 설치에서 게시 프로필을 찾을 수 있습니다  *\<profilename\>.pubxml*에  *\\< p r o j\>\Properties\PublishProfiles* 관리 되는 프로젝트 형식에 대 한 폴더입니다. 웹 사이트의 경우에서 찾아봅니다는 *\App_Data* 폴더입니다. 게시 프로필에는 MSBuild XML 파일입니다.

## <a name="prerequisites"></a>전제 조건

* Visual Studio 2017 설치 되어 있어야 하며 **ASP.NET** 및 **.NET Framework** 개발 작업 합니다. .NET Core 응용 프로그램에 대해도 필요는 **.NET Core** 작업 합니다.

    아직 Visual Studio를 설치하지 않은 경우 [여기](http://www.visualstudio.com)에서 평가판을 설치합니다.

* Azure 앱 서비스를 만듭니다. 자세한 내용은 참조 [Visual Studio를 사용 하 여 Azure에 ASP.NET Core 웹 앱을 배포](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)합니다. 

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Visual Studio에서 새 ASP.NET 프로젝트 만들기

1. Visual Studio를 실행 하는 컴퓨터에서 선택 **파일 > 새 프로젝트**합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **웹**, 한 다음 가운데 창에서 하나를 선택 하 고 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 또는 (C#만) **ASP.NET Core 웹 응용 프로그램**, 클릭 하 고 **확인**합니다.

    지정 된 프로젝트 템플릿이 보이지 않으면 클릭는 **Open Visual Studio 설치 관리자** 의 왼쪽된 창에서 링크는 **새 프로젝트** 대화 상자. Visual Studio 설치 관리자가 시작됩니다. 이 문서를 설치 해야는 필요한 Visual Studio 작업의 필수 구성 요소를 참조 하십시오.

1. 중 하나를 선택 **MVC** (.NET Framework) 또는 **웹 응용 프로그램 (모델-뷰-컨트롤러)** (.NET Core)에 있는지 확인 하 고 **인증 안 함** 을 선택한 다음 클릭 **확인**합니다.

1. 같은 이름을 입력 **MyWebApp** 클릭 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

1. 선택 **빌드 > 솔루션 빌드** 프로젝트를 빌드합니다.

## <a name="create-the-publish-settings-file-in-azure-app-service"></a>Azure 앱 서비스에서 게시 설정 파일 만들기

1. Azure 포털에서 Azure 응용 프로그램 서비스를 엽니다.

1. 클릭 **Get 게시 프로필** 프로 파일을 로컬로 저장 합니다.

    ![게시 프로필 가져오기](../deployment/media/tutorial-azure-app-service-get-publish-profile.png)

    파일을 한 *.publishsettings* 사용자가 저장 위치에 생성 된 파일 확장명입니다. 다음 코드에서는 부분적으로 더 읽기 쉬운 서식) (파일의 예를 보여 줍니다.

    ```xml
    <publishData>
      <publishProfile
        profileName="DeployASPDotNetCore - Web Deploy"
        publishMethod="MSDeploy"
        publishUrl="deployaspdotnetcore.scm.azurewebsites.net:443"
        msdeploySite="DeployASPDotNetCore"
        userName="$DeployASPDotNetCore"
        userPWD="abcdefghijklmnopqrstuzwxyz"
        destinationAppUrl="http://deployaspdotnetcore20180508031824.azurewebsites.net"
        SQLServerDBConnectionString=""
        mySQLDBConnectionString=""
        hostingProviderForumLink=""
        controlPanelLink="http://windows.azure.com"
        webSystem="WebSites">
        <databases />
      </publishProfile>
    </publishData>
    ```
    일반적으로 이전 *.publishsettings 파일에는 웹 배포 하 고 하나를 사용 하 여 FTP를 사용 하 여 배포를 배포 하는 Visual Studio에서 사용할 수 있는 두 개의 게시 프로필이 포함 됩니다. 위의 코드에서는 웹 배포 프로필을 보여 줍니다. 프로필을 가져올 때 두 프로필이 모두 나중에 가져올 수 있습니다.

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio에서 게시 설정 가져오기 및 배포

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/import-publish-settings-vs.md)]

## <a name="next-steps"></a>다음 단계

게시 설정 파일을 만든이 자습서에서는 Visual Studio로 가져올 및 Azure 앱 서비스에 ASP.NET 응용 프로그램을 배포 합니다.

> [!div class="nextstepaction"]
> [배포 소개](../deployment/deploying-applications-services-and-components.md)
