---
title: "웹 사이트-Visual Studio에 게시 | Microsoft Docs"
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
ms.workload: multiple
ms.openlocfilehash: 07944d5690433831889e56375cfa13ba774aaa8b
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="publish-a-web-app-or-a-net-core-app-to-a-web-site-using-the-visual-studio-publish-tool"></a>Visual Studio 게시 도구를 사용 하 여 웹 사이트에 웹 앱 또는.NET Core 응용 프로그램 게시

사용할 수는 **게시** 웹 사이트에 ASP.NET 응용 프로그램을 게시 하는 도구입니다.

이 단계는 ASP.NET, ASP.NET Core,.NET Core 및 Visual Studio에서 Python 응용 프로그램에 적용 합니다. Node.js에 대 한 단계는 지원 되지만 사용자 인터페이스는 다릅니다.

## <a name="create-a-new-project"></a>새 프로젝트 만들기 

1. Visual Studio에서 선택 **파일 > 새 프로젝트**합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **웹**, 한 다음 가운데 창에서 하나를 선택 하 고 **ASP.NET 웹 응용 프로그램 (.NET Framework)**또는 (C#만) **ASP.NET Core 웹 응용 프로그램**, 클릭 하 고 **확인**합니다.

1. 선택 **MVC**, 다음 사항을 확인 **인증 안 함** 을 선택한 다음 클릭 **확인**합니다.

1. 같은 이름을 입력 **MyWebApp** 클릭 **확인**합니다.

    Visual Studio 프로젝트를 만듭니다.

1. 선택 **빌드 > 솔루션 빌드** 프로젝트를 빌드합니다.

## <a name="publish-to-a-web-site"></a>웹 사이트에 게시

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시**합니다.

    ![선택 게시](../deployment/media/quickstart-publish-aspnet.png "선택 게시")

1. 에 **게시** 창 선택 **IIS, FTP, 등**합니다.

    ![IIS, FTP, 등 선택](../deployment/media/quickstart-publish-iis-ftp.png "IIS 선택, FTP, 등입니다.")

1. **게시**를 클릭합니다.

    프로필 게시 설정 대화 상자가 열립니다.

    ![폴더를 선택](../deployment/media/quickstart-publish-settings-web.png "폴더를 선택 합니다.")

1. 에 **게시 방법** 필드와 같은 메서드를 선택 합니다 **웹 배포** 또는 **FTP**합니다.

    볼 수 있는 설정 옆 게시 메서드에 해당 합니다.

1. 게시 방법에 대 한 필요한 설정을 구성 하 고 클릭 **연결 유효성 검사**합니다.

    서버 또는 대상을 사용할 수 있고 설정이 잘못 된 경우 연결 되었음을 나타내는 메시지의 유효성을 검사 하 고 게시할 준비가 되었습니다. 나타납니다.

    ![연결 확인](../deployment/media/quickstart-publish-web-deploy.png "연결 확인")

1. 다른 배포 설정을 구성 하려면 클릭 **설정을**합니다.

    디버그 또는 릴리스 구성을 배포 하 고 클릭 여부와 같은 옵션을 구성할 수 있습니다 **저장**합니다. 원격으로 디버깅 하는 경우는 디버그 구성은 필요 합니다.

1. 을 게시 하려면 **게시**합니다.

    출력 창에는 배포 진행률 및 결과 표시 합니다.

## <a name="next-steps"></a>다음 단계

- [IIS에 ASP.NET 배포](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)
