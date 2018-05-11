---
title: 웹 사이트-Visual Studio에 게시 | Microsoft Docs
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
- multiple
ms.openlocfilehash: 6fa914b1b6b353d4e15bd8293f1fc141dd0ae371
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="publish-a-web-app-or-a-net-core-app-to-a-web-site-using-the-visual-studio-publish-tool"></a>Visual Studio 게시 도구를 사용 하 여 웹 사이트에 웹 앱 또는.NET Core 응용 프로그램 게시

사용할 수는 **게시** 웹 사이트에 ASP.NET 응용 프로그램을 게시 하는 도구입니다.

이 단계는 ASP.NET, ASP.NET Core,.NET Core 및 Visual Studio에서 Python 응용 프로그램에 적용 합니다. Node.js에 대 한 단계는 지원 되지만 사용자 인터페이스는 다릅니다.

## <a name="prerequisites"></a>전제 조건

* Visual Studio 2017 설치 되어 있어야 하며 **ASP.NET** 및 **.NET Framework** 개발 작업 합니다. .NET Core 응용 프로그램에 대해도 필요는 **.NET Core** 작업 합니다.

    아직 Visual Studio를 설치하지 않은 경우 [여기](http://www.visualstudio.com)에서 평가판을 설치합니다.

## <a name="create-a-new-project"></a>새 프로젝트 만들기 

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **웹**, 한 다음 가운데 창에서 하나를 선택 하 고 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 또는 (C#만) **ASP.NET Core 웹 응용 프로그램**, 클릭 하 고 **확인**합니다.

1. 선택 **MVC** (선택 또는 **웹 응용 프로그램 (모델-뷰-컨트롤러)** .NET Core에 대 한), 다음 사항을 확인 **인증 안 함** 을 선택한 다음 클릭 **확인** .

1. 같은 이름을 입력 **MyWebApp** 클릭 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

1. 선택 **빌드 > 솔루션 빌드** 프로젝트를 빌드합니다.

## <a name="publish-to-a-web-site"></a>웹 사이트에 게시

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

    ![선택 게시](../deployment/media/quickstart-publish-aspnet.png "선택 게시")

1. 모든 게시 프로필을 이전에 구성한 경우는 **게시** 창이 나타납니다. 클릭 **새 프로필 만들기**합니다.

1. 에 **게시 대상 선택** 대화 상자에서 선택 **IIS, FTP, 등**합니다.

    ![IIS, FTP, 등 선택](../deployment/media/quickstart-publish-iis-ftp.png "IIS 선택, FTP, 등입니다.")

1. **게시**를 클릭합니다.

    프로필 게시 설정 대화 상자가 열립니다.

    ![폴더를 선택](../deployment/media/quickstart-publish-settings-web.png "폴더를 선택 합니다.")

1. 에 **게시 방법** 필드와 같은 메서드를 선택 합니다 **웹 배포** 또는 **FTP**합니다.

    볼 수 있는 설정 옆 게시 메서드에 해당 합니다. 웹 배포는 IIS 서버에 웹 응용 프로그램 및 웹 사이트의 배포를 단순화 하 고 서버에서 응용 프로그램으로 설치 해야 합니다. 사용 하 여는 [웹 플랫폼 설치 관리자](https://www.microsoft.com/web/downloads/platform.aspx) 를 설치 합니다.

1. 게시 방법에 대 한 필요한 설정을 구성 하 고 클릭 **연결 유효성 검사**합니다.

    서버 또는 대상을 사용할 수 있고 설정이 잘못 된 경우 연결 되었음을 나타내는 메시지의 유효성을 검사 하 고 게시할 준비가 되었습니다. 나타납니다.

    ![연결 확인](../deployment/media/quickstart-publish-web-deploy.png "연결 확인")

1. 다른 배포 설정을 구성 하려면 클릭 **설정을**합니다.

    디버그 또는 릴리스 구성을 배포 하 고 클릭 여부와 같은 옵션을 구성할 수 있습니다 **저장**합니다. 원격으로 디버깅 하는 경우는 디버그 구성은 필요 합니다.

1. 을 게시 하려면 **게시**합니다.

    출력 창에는 배포 진행률 및 결과 표시 합니다.

## <a name="next-steps"></a>다음 단계

이 퀵 스타트의 게시 프로필을 만들려면 Visual Studio를 사용 하는 방법을 배웠습니다. 게시를 구성할 수도 있습니다를 가져와서 프로필 게시 설정 합니다.

> [!div class="nextstepaction"]
> [게시 설정 하 고 IIS에 배포 하는 가져오기](tutorial-import-publish-settings-iis.md)
