---
title: Visual Studio를 로컬 폴더에 배포 | Microsoft Docs
ms.custom: ''
ms.date: 05/08/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, local folder
ms.assetid: adb461c4-812a-4b8c-b2ab-96002379f6a9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a68e7d039fe0b60faf42ea319bb3a3bd4f888d3b
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="deploy-a-web-app-or-net-core-app-to-a-local-folder-using-the-visual-studio-publish-tool"></a>Visual Studio 게시 도구를 사용 하 여 로컬 폴더에 웹 앱 또는.NET Core 응용 프로그램 배포

사용할 수는 **게시** 도구를 로컬 폴더에 앱을 게시 합니다. 

이 단계는 ASP.NET, ASP.NET Core,.NET Core 및 Visual Studio에서 Python 응용 프로그램에 적용 합니다. Node.js에 대 한 단계는 지원 되지만 사용자 인터페이스는 다릅니다.

## <a name="prerequisites"></a>전제 조건

* Visual Studio 2017 설치 되어 있어야 합니다 및 **.NET Framework** 및 **.NET Core** 개발 작업을 설치 합니다.

    아직 Visual Studio를 설치하지 않은 경우 [여기](http://www.visualstudio.com)에서 평가판을 설치합니다.

## <a name="create-a-new-project"></a>새 프로젝트 만들기 

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **.NET Core**를 선택한 다음 가운데 창에서 메뉴 **콘솔 응용 프로그램 (.NET Core)** 합니다.

1. 같은 이름을 입력 **MyLocalApp** 클릭 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

## <a name="deploy-to-a-local-folder"></a>로컬 폴더에 배포

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

    ![선택 게시](../deployment/media/quickstart-publish.png "선택 게시")

1. 모든 게시 프로필을 이전에 구성한 경우는 **게시** 창이 나타납니다. 클릭 **새 프로필 만들기**합니다.

1. 에 **게시 대상 선택** 대화 상자에서 선택 **폴더**합니다.

    ![폴더를 선택](../deployment/media/quickstart-publish-folder.png "폴더를 선택 합니다.")

1. 경로 입력 하거나 클릭 **찾아보기** 로컬 폴더를 찾습니다.

1. **게시**를 클릭합니다.

    Visual Studio 프로젝트를 빌드하고 지정한 폴더에 게시 합니다.

    게시 창 프로필 요약이 표시 됩니다.

1. 배포 설정을 구성 하려면 클릭 **설정을** 프로필 요약 합니다.

    ![프로필 설정](../deployment/media/quickstart-profile-settings.png "프로필 설정") 

1. 디버그 또는 릴리스 구성을 배포 하 고 다음 클릭 여부 등의 옵션 구성 **저장**합니다.

1. 를 다시 게시 하려면 클릭 **게시**합니다.

게시된 파일을 원하는 방식으로 배포합니다. 예를 들어 Zip 파일에 패키지에 간단한 복사 명령을 사용 하거나 사용자가 선택한 모든 설치 패키지와 함께 배포할 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [게시 도구를 사용하여 .NET Core 응용 프로그램 배포](/dotnet/core/deploying/deploy-with-vs?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Microsoft Store(데스크톱 브리지)의 데스크톱 앱 패키지](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- (.NET) [.NET Framework 및 응용 프로그램 배포...](/dotnet/framework/deployment/)
