---
title: Visual Studio에서 부하 테스트에 대한 가상 사용자의 전체 정보 수집 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, virtual user activity chart, configuring
- virtual user activity chart, configuring
ms.assetid: cb22e43b-af4d-4e09-9389-3c3fa00786f7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: b410c91ff2b6c57b86c7fe377df4bf31173f9384
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-configure-load-tests-to-collect-full-details-to-enable-virtual-user-activity-in-test-results"></a>방법: 전체 정보를 수집하여 테스트 결과에서 가상 사용자 동작을 활성화하도록 부하 테스트 구성

부하 테스트에서 가상 사용자 동작 차트를 사용하려면 전체 정보를 수집하도록 부하 테스트를 구성해야 합니다. 전체 정보를 수집하도록 부하 테스트를 구성하려면 부하 테스트와 연결된 **타이밍 정보 저장소** 속성에 대해 **모든 개인 정보** 설정을 선택합니다. 이 모드의 부하 테스트에서는 모든 테스트, 페이지 및 트랜잭션에 대한 자세한 정보를 수집합니다.

 이전 버전의 Visual Studio 부하 테스트에서 프로젝트를 업그레이드할 경우 다음 절차의 단계를 수행하여 전체 정보 컬렉션을 사용하도록 설정합니다.

 **타이밍 정보 저장소** 속성에 대한 **모든 개인 정보** 설정을 다음 옵션 중 하나로 설정할 수 있습니다.

-   **모든 개인 정보:** 테스트 중에 생성된 각 테스트, 트랜잭션 및 페이지에 대한 개별 타이밍 데이터를 수집하여 저장합니다.

    > [!NOTE]
    > 부하 테스트 결과에서 가상 사용자 데이터 정보를 사용하려면 **모든 개인 정보** 옵션을 선택해야 합니다.

-   **없음:** 개별 타이밍 정보를 수집하지 않습니다. 그러나 이 경우에도 평균값은 사용할 수 있습니다.

-   **통계만:** 개별 타이밍 데이터를 백분위수 데이터로만 저장합니다. 따라서 공간 리소스가 절약됩니다.

## <a name="to-configure-the-timing-details-storage-property-in-a-load-test"></a>부하 테스트에서 타이밍 정보 저장소 속성을 구성하려면

1.  부하 테스트 편집기에서 부하 테스트를 엽니다.

2.  부하 테스트에서 **실행 설정** 노드를 확장합니다.

3.  구성할 실행 설정(예: **Run Settings1[Active]**)을 선택합니다.

4.  속성 창을 엽니다. **보기** 메뉴에서 **속성 창**을 선택합니다.

5.  **결과** 범주에서 **타이밍 정보 저장소** 속성을 선택하고 **모든 개인 정보**를 선택합니다.

     **타이밍 정보 저장소** 속성에 대해 **모든 개인 정보** 설정을 구성하면 부하 테스트를 실행하고 가상 사용자 동작 차트를 볼 수 있습니다. 자세한 내용은 [방법: 부하 테스트 중에 가상 사용자가 수행하는 작업 분석](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [세부 정보 뷰에서 가상 사용자 동작 분석](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [연습: 가상 사용자 동작 차트를 사용하여 문제 격리](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)