---
title: "Visual Studio에서 Azure App Service에 Python 앱 게시 | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85031f91-3a65-463b-a678-1e69f1b843e6
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a42f5a30375192c89c9984e40ba0104da98d7253
ms.openlocfilehash: 0163d1279b41ef8fecf9ca774cd3e67f0f47f1b1
ms.lasthandoff: 03/07/2017

---

# <a name="publishing-to-azure-app-service"></a>Azure App Service에 게시

다음 단계를 통해 Visual Studio에서 Python 웹 사이트를 신속하게 빌드하기 시작하고 Azure App Service에 게시할 수 있습니다.

- [Azure 구독 만들기](#create-an-azure-subscription)
- [초기 프로젝트 만들기 및 테스트](#create-and-test-the-initial-project)
- [Azure App Service에 게시](#publish-to-azure-app-service)

이 프로세스의 짧은 연습은 [Visual Studio Python 자습서: 웹 사이트 빌드](https://www.youtube.com/watch?v=FJx5mutt1uk&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff&index=6)(youtube.com, 3분10초)에서 찾을 수 있습니다. 

> [!VIDEO https://www.youtube.com/embed/FJx5mutt1uk] 

## <a name="create-an-azure-subscription"></a>Azure 구독 만들기

Azure에 게시하려면 Azure 구독이 필요합니다. 또는 임시 사이트를 사용할 수 있습니다.

구독은 [전체 무료 Azure 계정](https://azure.microsoft.com/en-us/free/)을 시작하세요. 여기에는 Azure 서비스에 대한 일반적인 크레딧을 포함합니다. 또한 한 해 동안 매달 $25 크레딧을 제공하는 [Visual Studio Dev Essentials](https://azure.microsoft.com/en-us/pricing/member-offers/vs-dev-essentials/)에 등록을 고려해보세요.

Azure App Service에서 Azure 구독이 필요 없이 임시 사이트를 만들려면:

1. 브라우저를 [try.azurewebsites.net](https://try.azurewebsites.net)로 엽니다.
1. 앱 유형에 **Web App**을 선택하고 **다음**을 선택합니다.
1. 템플릿에 **빈 사이트**를 선택하고 **만들기 >**를 선택합니다.
1. 선택한 소셜 로그인을 사용하여 로그인하면 잠시 후에 사이트가 표시된 URL에서 준비됩니다.
1. **게시 프로필 다운로드**를 선택하고 `.publishsettings` 파일을 저장합니다. 이 파일을 나중에 사용할 수 있습니다.

## <a name="create-and-test-the-initial-project"></a>초기 프로젝트 만들기 및 테스트

1. Visual Studio에서 **파일 > 새로 만들기 > 프로젝트**를 선택하고 "Bottle"을 검색하고 **Bottle 웹 프로젝트**를 선택하고 **확인**을 클릭합니다.    

1. 외부 패키지를 설치하라는 메시지가 표시되면 **가상 환경에 설치**를 선택합니다. 대화 상자 맨 아래에 있는 **필수 패키지 표시** 컨트롤이 설치할 패키지를 표시합니다.

  ![필수 패키지 설치](media/tutorials-common-external-packages.png)

1. 가상 환경에 기본 설정된 기본 해석기(예: **Python 2.7** 또는 **Python 3.4**)를 선택하고 **만들기**를 클릭합니다.

  ![프로젝트를 만들 경우 가상 환경 추가](media/tutorials-common-add-virtual-environment.png)

1. 프로젝트를 만들면 **디버그 > 디버깅 시작**을 선택하거나 F5 키를 눌러서 로컬로 테스트합니다. 기본적으로 응용 프로그램은 구성이 필요하지 않은 메모리 내 리포지토리를 사용합니다. 웹 서버가 중지되면 모든 데이터가 손실됩니다.

1. 해당 작업을 보려면 응용 프로그램 주위를 클릭합니다.

1. 작업이 완료되면 디버거를 중지합니다(**디버그 > 디버깅 중지** 또는 Shift + F5).

## <a name="publish-to-azure-app-service"></a>Azure App Service에 게시

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다. 

1. **게시** 대화 상자에서 **Microsoft Azure App Service**를 선택합니다.

  ![Azure에 게시 1단계](media/tutorials-common-publish-1.png)

1. 대상을 선택합니다.

    - Azure 구독이 있는 경우 **Microsoft Azure App Service**를 게시 대상으로 선택하고 다음 대화 상자에서 기존 App Service를 선택하거나 **새로 만들기**를 선택하여 새 계정을 만듭니다.
    - try.azurewebsites.net에서 임시 사이트를 사용하는 경우 **가져오기**를 게시 대상으로 선택한 다음 사이트에서 다운로드한 `.publishsettings` 파일을 찾아보고 **확인**을 선택합니다.

1. App Service 세부 정보는 아래에서 **게시** 대화 상자의 **연결** 탭에 표시됩니다.

  ![Azure에 게시 2단계](media/tutorials-common-publish-2.png)

1. 추가 설정을 검토하는 데 필요하면 **다음 >**을 선택합니다. [Azure에서 Python 코드를 원격으로 디버그](debugging-azure-remote.md)하려는 경우 **구성**을 **디버그**로 설정해야 합니다.
1. **게시**를 선택합니다. 응용 프로그램을 Azure에 배포하면 해당 사이트에서 기본 브라우저가 열립니다. 
