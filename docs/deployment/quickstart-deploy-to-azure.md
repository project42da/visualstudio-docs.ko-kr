---
title: "Azure 앱 서비스-Visual Studio에 게시 | Microsoft Docs"
ms.custom: 
ms.date: 11/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords: deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c1fa8867c4f9ab46b50f0b2a144970d772cbd71
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2017
---
# <a name="publish-an-aspnet-or-aspnet-core-app-to-azure-app-service-using-visual-studio"></a>Visual Studio를 사용 하 여 Azure 응용 프로그램 서비스에 ASP.NET 또는 ASP.NET Core 응용 프로그램 게시

사용할 수는 **게시** Azure 앱 서비스에 ASP.NET, ASP.NET Core, Python, Node.js, 및.NET Core 응용 프로그램을 게시 하는 도구입니다.

Azure 계정이 아직 없는 경우 다음을 할 수 있습니다 [여기 등록](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio)합니다.

## <a name="create-a-new-project"></a>새 프로젝트 만들기 

1. Visual Studio에서 선택 **파일 > 새 프로젝트**합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **웹**, 한 다음 가운데 창에서 하나를 선택 하 고 **ASP.NET 웹 응용 프로그램 (.NET Framework)**또는 (C#만) **ASP.NET Core 웹 응용 프로그램**, 클릭 하 고 **확인**합니다.

1. 선택 **MVC**, 다음 사항을 확인 **인증 안 함** 을 선택한 다음 클릭 **확인**합니다.

1. 같은 이름을 입력 **MyWebApp** 클릭 **확인**합니다.

    Visual Studio 프로젝트를 만듭니다.

1. 선택 **빌드 > 솔루션 빌드** 프로젝트를 빌드합니다.

## <a name="publish-to-azure-app-service"></a>Azure App Service에 게시

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시**합니다.

    ![선택 게시](../deployment/media/quickstart-publish-aspnet.png "선택 게시")

1. 에 **게시** 창 선택 **Microsoft Azure 앱 서비스**합니다.

    ![Azure 앱 서비스 선택](../deployment/media/quickstart-publish-azure.png "Azure 앱 서비스 선택")

1. **게시**를 클릭합니다.

    **응용 프로그램 서비스 만들기** 대화 상자가 나타납니다.

    ![응용 프로그램 서비스를 만들](../deployment/media/quickstart-publish-settings-app-service.png "Azure 앱 서비스 만들기")
    
1. Visual Studio에 로그인 하지 않은 경우 로그인 한 후 기본 응용 프로그램 서비스 설정 필드를 채웁니다.

    프로필 게시 설정 대화 상자가 열립니다.

    ![폴더를 선택](../deployment/media/quickstart-publish-settings-web.png "폴더를 선택 합니다.")

    이 대화 상자에서 사용 하는 구독을 선택, 선택 하거나 등 Azure 리소스 그룹을 만들 수 있습니다.

1. 
              **만들기**를 클릭합니다.

    Azure 앱 서비스에 앱을 배포 하는 visual Studio 및 브라우저에서 웹 앱이 로드 합니다.

    에 대 한 요약에는 **게시** 창에서 새 Azure 앱 서비스에 대 한 사이트 URL을 표시 합니다.

## <a name="next-steps"></a>다음 단계

- [Azure에 ASP.NET Core 응용 프로그램을 배포 합니다.](https://docs.microsoft.com/en-us/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)
- [Git 사용 하 여 Azure에 ASP.NET Core의 연속 배포](https://docs.microsoft.com/en-us/aspnet/core/publishing/azure-continuous-deployment)
