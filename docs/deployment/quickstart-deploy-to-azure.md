---
title: Azure 앱 서비스-Visual Studio에 게시 | Microsoft Docs
ms.custom: ''
ms.date: 11/22/2017
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: f91fd6e8c101b674b745c120978a47adb17c9b91
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765377"
---
# <a name="publish-an-aspnet-or-aspnet-core-app-to-azure-app-service-using-visual-studio"></a>Visual Studio를 사용 하 여 Azure 응용 프로그램 서비스에 ASP.NET 또는 ASP.NET Core 응용 프로그램 게시

사용할 수는 **게시** Azure 앱 서비스에 ASP.NET, ASP.NET Core, Python, Node.js, 및.NET Core 응용 프로그램을 게시 하는 도구입니다.

Azure 계정이 아직 없는 경우 다음을 할 수 있습니다 [여기 등록](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio)합니다.

## <a name="prerequisites"></a>전제 조건

* 설치 된 Visual Studio 2017 있어야 및 **ASP.NET 및 웹 개발** 작업 부하 및. **NET 데스크톱 개발** 작업 합니다. .NET Core 앱에 대 한 필요한는 합니다. **NET 코어** 작업 합니다.

    아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

## <a name="create-a-new-project"></a>새 프로젝트 만들기 

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **웹**, 한 다음 가운데 창에서 하나를 선택 하 고 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 또는 (C#만) **ASP.NET Core 웹 응용 프로그램**, 클릭 하 고 **확인**합니다.

1. 선택 **MVC** (선택 또는 **웹 응용 프로그램 (모델-뷰-컨트롤러)** .NET Core에 대 한), 다음 사항을 확인 **인증 안 함** 을 선택한 다음 클릭 **확인** .

1. 같은 이름을 입력 **MyWebApp** 클릭 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

1. 선택 **빌드 > 솔루션 빌드** 프로젝트를 빌드합니다.

## <a name="publish-to-azure-app-service"></a>Azure App Service에 게시

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

    ![선택 게시](../deployment/media/quickstart-publish-aspnet.png "선택 게시")

1. 모든 게시 프로필을 이전에 구성한 경우는 **게시** 창이 나타납니다. 클릭 **새 프로필 만들기**합니다.

1. 에 **게시 대상 선택** 대화 상자에서 선택 **앱 서비스**합니다.

    ![Azure 앱 서비스 선택](../deployment/media/quickstart-publish-azure.png "Azure 앱 서비스 선택")

1. **게시**를 클릭합니다.

    **응용 프로그램 서비스 만들기** 대화 상자가 나타납니다.

    ![응용 프로그램 서비스를 만들](../deployment/media/quickstart-publish-settings-app-service.png "Azure 앱 서비스 만들기")
    
1. Visual Studio에 로그인 하지 않은 경우 로그인 한 후 기본 응용 프로그램 서비스 설정 필드를 채웁니다.

    프로필 게시 설정 대화 상자가 열립니다.

    ![폴더를 선택](../deployment/media/quickstart-publish-settings-web.png "폴더를 선택 합니다.")

    이 대화 상자에서 사용 하는 구독을 선택, 선택 하거나 등 Azure 리소스 그룹을 만들 수 있습니다.

1. **만들기**를 클릭합니다.

    Azure 앱 서비스에 앱을 배포 하는 visual Studio 및 브라우저에서 웹 앱이 로드 합니다.

    에 대 한 요약에는 **게시** 창에서 새 Azure 앱 서비스에 대 한 사이트 URL을 표시 합니다.

## <a name="next-steps"></a>다음 단계

이 빠른 시작에서는 Azure에 배포에 대 한 게시 프로필을 만들려면 Visual Studio를 사용 하는 방법을 알아보았습니다. 게시를 구성할 수도 있습니다를 가져와서 프로필 게시 Azure 앱 서비스에서 설정 합니다.

> [!div class="nextstepaction"]
> [게시 설정 가져오기 및 Azure에 배포](tutorial-import-publish-settings-azure.md)
