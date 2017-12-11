---
title: "Visual Studio Tools for Unity Azure Walkthrough 구성 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: BAE62C27-CA7A-4466-8738-3DB880221CE1
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 4e1cf47420cafda2552cdbb625d6d41626c32971
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="configure-easy-tables-in-azure"></a>Azure에서 간편한 테이블 구성

간편한 테이블은 Azure Portal GUI에서 바로 SQL 테이블을 설정 및 관리할 수 있는 [Azure Mobile Apps](https://azure.microsoft.com/services/app-service/mobile/)의 기능입니다. Azure Mobile Apps는 많은 기능을 지원하지만, 이 예의 범위는 Azure Mobile App 백엔드에 저장된 데이터를 Unity 프로젝트에서 읽고 쓰는 것으로 제한되어 있습니다.

## <a name="create-a-new-azure-mobile-app"></a>새 Azure Mobile App 만들기

[Azure Portal](https://ms.portal.azure.com)에 로그인합니다. Azure 구독이 없는 경우 [무료 평가판](https://azure.microsoft.com/en-us/free/) 또는 [Visual Studio Dev Essentials](https://www.visualstudio.com/dev-essentials/)에서 포함된 크레딧이 이 연습을 완료하기에 더 충분할 수 있습니다.

**포털 내부:**

1. **새로 만들기 > 웹 + 모바일 > 모바일 앱 > 만들기**를 선택합니다.

  ![새 모바일 앱 만들기](media/vstu_azure-configure-easy-tables-image1.png)

2. 새 모바일 앱 구성:

  * **앱 이름**. Azure Mobile App 백엔드에 연결하는 데 사용하는 URL를 빌드합니다. 녹색 체크표시로 표시된 고유한 이름을 선택해야 합니다.

  * **구독**. 새 모바일 앱에서 청구에 사용할 구독을 선택합니다.

  * **리소스 그룹**. 리소스 그룹을 통해 관련 리소스를 더 쉽게 관리할 수 있습니다. 기본적으로, Azure는 새 앱과 동일한 이름의 새로운 리소스 그룹을 만듭니다. 기본 설정은 연습에도 효과적입니다.

  *  **App Service 계획/위치**. 서비스 계획은 Azure가 새 모바일 앱을 호스팅하기 위해 사용하는 리소스, 위치 및 컴퓨팅 성능을 자세하 기술합니다. 기본적으로 Azure는 일부 기본 설정으로 새로운 서비스 계획을 만듭니다. 이 연습에 사용할 수 있는 가장 간단한 옵션입니다. 그러나 이 메뉴를 사용하여 새로운 서비스 계획의 가격 책정 계층 또는 지리적 위치를 사용자 지정할 수 있습니다. 또한, 서비스 계획의 설정은 배포 후에 수정할 수 있습니다.

  ![새 모바일 앱 만들기](media/vstu_azure-configure-easy-tables-image2.png)

3. **만들기**를 선택하고 Azure에서 새 리소스를 배포할 때까지 잠시 기다립니다. 배포가 완료되면 Azure Portal에 알림이 표시됩니다.

## <a name="add-a-new-data-connection"></a>새 데이터 연결 추가

4. 배포가 완료되면 **모든 리소스** 단추를 클릭한 다음 새로 만들어진 모바일 앱을 선택합니다.

  ![새 모바일 앱 선택](media/vstu_azure-configure-easy-tables-image3.png)

5. 새로 열린 블레이드에서 왼쪽 메뉴를 아래로 스크롤하고 **MOBILE** 제목 아래에 있는 **간편한 테이블** 단추를 클릭합니다.

  ![간편한 테이블 선택](media/vstu_azure-configure-easy-tables-image4.png)

6. 간편한 테이블 블레이드 맨 위에 표시되는 파란색 **간편한 테이블/간편한 API를 구성해야 합니다.** 알림을 클릭합니다.

  ![간편한 테이구 구성 알림 클릭](media/vstu_azure-configure-easy-tables-image5.png)

7. **간편한 테이블을 사용하려면 데이터베이스가 필요합니다. 데이터베이스를 만들려면 여기를 클릭하세요.** 알림을 클릭합니다.

  ![데이터베이스 만들기 알림 클릭](media/vstu_azure-configure-easy-tables-image6.png)

8. 데이터베이스 연결 블레이드에서 **추가** 단추를 클릭합니다.

  ![추가 단추 클릭](media/vstu_azure-configure-easy-tables-image7.png)

9. 데이터 연결 추가 블레이드에서 **SQL 데이터베이스**를 선택합니다.

  ![SQL 데이터베이스 선택](media/vstu_azure-configure-easy-tables-image8.png)

10. 새 SQL 데이터베이스 및 SQL 서버 구성을 위해 블레이드가 열립니다.

  * **이름**. 데이터베이스의 이름을 입력합니다.

  * **대상 서버**. **대상 서버**를 클릭하여 새 서버 블레이드를 엽니다.

      * **서버 이름**. 서버의 이름을 입력합니다.

      * **서버 관리 로그임 및 암호**. 서버 관리의 사용자 이름과 암호를 만듭니다.

      * **위치**. 서버의 가까운 위치를 선택합니다.

      * **Azure 서비스의 서버 액세스 허용** 확인란이 선택되어 있는지 확인합니다.

      * **선택**을 클릭하여 서버 구성을 완료합니다.

    * **가격 책정 계층**. 연습을 위해 기본 설정을 그대로 유지합니다. 나중에 수정할 수 있습니다.

    * **데이터 정렬**. 기본 설정을 유지합니다.

    * **선택**을 클릭하여 데이터베이스 구성을 완료합니다.

    ![SQL 서버 및 데이터베이스 구성](media/vstu_azure-configure-easy-tables-image9.png)

11. 데이터 추가 연결 블레이드 뒤에서 **연결 문자열**을 클릭합니다. 연결 문자열 블레이드가 나타나면 기본 설정을 그대로 유지하고 **확인**을 클릭합니다.

  ![연결 문자열 클릭](media/vstu_azure-configure-easy-tables-image9.1.png)

12. 데이터 추가 연결 블레이드 뒤에서 "MS_TableConnectionString" 텍스트가 더 이상 기울임꼴로 나타나서는 안 됩니다. **확인**을 클릭하고 Azure가 새 데이터 연결을 만들 때가지 몇 분 기다립니다. 과정이 끝나면 알림이 표시됩니다.

  ![확인 클릭](media/vstu_azure-configure-easy-tables-image9.2.png)

## <a name="complete-the-easy-table-initialization"></a>간편한 테이블 초기화 완료

13. 새 데이터 연결이 성공적으로 만들어지면 **모든 리소스** 단추를 클릭하고 모바일 앱으로 다시 돌아갑니다. 이 단계를 완료하여 간편한 테이블 구성 알림을 새로 고침하는 것이 중요합니다.

14. 아래로 스크롤하여 **간편한 테이블**을 선택하고 한 번 더 파란색 **간편한 테이블/간편한 API를 구성해야 합니다.** 알림을 선택합니다.

  ![간편한 테이블 알림 클릭](media/vstu_azure-configure-easy-tables-image5.png)

15. 이번에 나타나는 블레이드에는 **1** 제목 아래에 “데이터 연결이 이미 있음” 메시지가 표시됩니다. **2** 제목에서 **이렇게 하면 모든 사이트 콘텐츠를 덮어쓴다는 것을 인정합니다.** 확인란을 클릭합니다. 이제 **앱 초기화**를 클릭하고 Azure가 초기화 과정을 완료할 때까지 몇 분 기다립니다. 과정이 완료되면 새로운 알림이 나타납니다.

  ![앱 초기화 클릭](media/vstu_azure-configure-easy-tables-image10.png)

## <a name="next-step"></a>다음 단계

* [간편한 테이블 만들기](visual-studio-tools-for-unity-azure-setup.md)
