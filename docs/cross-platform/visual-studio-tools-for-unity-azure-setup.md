---
title: "Visual Studio Tools for Unity Azure Walkthrough 설정 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: FFE17FC6-0B47-4A00-A125-01BD49E3873C
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 447f32c2e736084a08223b56f4188ca7c8abeea5
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="create-easy-tables"></a>간편한 테이블 만들기

이제 간편한 테이블로 Azure에서 모바일 앱이 초기화되었으므로, Unity 게임에서 보낸 데이터를 추적할 테이블을 빌드할 시간입니다.

## <a name="setup-the-crash-heatmap-table"></a>충돌 열 지도 테이블 설정

1. Azure Portal에서 모든 리소스를 클릭한 다음, 이전 단계에서 간편한 테이블용으로 구성한 모바일 앱을 선택합니다.

  ![모바일 앱 선택](media/vstu_azure-setup-table-schema-image1.png)

2. **모바일** 제목까지 아래로 스크롤하여 **간편한 테이블**을 선택합니다. 간편한 테이블 초기화에 대해 더 이상 어떠한 알림도 없습니다.  

  ![간편한 테이블 선택](media/vstu_azure-setup-table-schema-image2.png)

3. **추가** 단추를 클릭합니다.

  ![추가 클릭](media/vstu_azure-setup-table-schema-image3.png)

4. 테이블의 이름을 "**CrashInfo**"로 지정하고 **확인**을 클릭합니다. 나머지 옵션은 기본 설정 옵션을 유지합니다.

  > [!WARNING]
  > 이 이름은 연습의 뒷부분에서 생성된 데이터 모델 클래스의 이름과 일치해야 합니다.

  ![이름을 지정하고 확인](media/vstu_azure-setup-table-schema-image4.png)

5. 새 테이블이 생성되면 알림이 발생합니다.

> [!NOTE]
> 간편한 테이블을 통해 데이터가 추가되면 테이블 스키마가 실제 동적으로 생성됩니다. 즉, 적합한 데이터 열은 이 단계 중 수동으로 설정할 필요가 없습니다.

## <a name="setup-the-leaderboard-table"></a>순위표 테이블 설정

1. 간편한 테이블 블레이드로 다시 이동하고 **추가**를 클릭하여 두 번째 테이블을 추가합니다.

  ![두 번째 테이블 추가](media/vstu_azure-setup-table-schema-image10.png)

2. 새 테이블의 이름을 "**HighScoreInfo**"로 지정하고 **확인**을 클릭합니다. 나머지 옵션은 기본 설정 옵션을 유지합니다.

  > [!WARNING]
  > 이 이름은 연습의 뒷부분에서 생성된 데이터 모델 클래스의 이름과 일치해야 합니다.

  ![이름을 지정하고 확인](media/vstu_azure-setup-table-schema-image11.png)

3. 새 테이블이 생성되면 알림이 발생합니다.


## <a name="next-step"></a>다음 단계

* [개발 환경 준비](visual-studio-tools-for-unity-azure-prepare.md)
