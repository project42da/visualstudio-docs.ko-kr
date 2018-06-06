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
ms.openlocfilehash: 02e6ae6e06daf43a6aec08097df2b37a21d2aaa3
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766680"
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

* Visual Studio 2017 설치 되어 있어야 하며 **ASP.NET** 및 **.NET Framework** 개발 작업 합니다. .NET Core 응용 프로그램에 대해도 필요는 **.NET Core** 작업 합니다.

    아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

* IIS에서 게시 설정 파일을 생성 하려면 Windows Server 2012 또는 Windows Server 2016을 실행 하는 컴퓨터 있어야 하며 올바르게 구성 하는 IIS 웹 서버 역할에 있어야 합니다. ASP.NET 4.5 또는 ASP.NET Core도 설치 해야 합니다. ASP.NET Core 참조 [를 IIS에 게시](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)합니다. ASP.NET 4.5에 대해 참조 [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)합니다.

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

[!INCLUDE [create-publish-settings-iis](../deployment/includes/create-publish-settings-iis.md)]

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio에서 게시 설정 가져오기 및 배포

[!INCLUDE [import-publish-settings](../deployment/includes/import-publish-settings-vs.md)]

응용 프로그램을 성공적으로 배포 후 자동으로 시작 해야 합니다. Visual Studio에서 시작 되지 않으면, IIS에서 앱을 시작 합니다. ASP.NET Core 응용 프로그램 풀 필드에 있는지 확인 해야는 **DefaultAppPool** 로 설정 된 **관리 코드 없음**합니다.

## <a name="next-steps"></a>다음 단계

게시 설정 파일을 만든이 자습서에서는 Visual Studio로 가져올을 IIS에 ASP.NET 응용 프로그램을 배포 합니다. Visual Studio에서 기타 게시 옵션의 개요를 할 수 있습니다.

> [!div class="nextstepaction"]
> [배포 소개](../deployment/deploying-applications-services-and-components.md)
