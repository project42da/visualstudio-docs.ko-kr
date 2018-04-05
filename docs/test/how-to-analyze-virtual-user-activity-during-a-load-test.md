---
title: Visual Studio에서 부하 테스트에 대한 가상 사용자 동작 분석 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- virtual user activity chart, viewing
ms.assetid: 8bda19b3-91c1-4daf-b6c7-09108bddadff
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: c23963f7e3fde399209c965e4de8132370e4b06a
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-analyze-what-virtual-users-are-doing-during-a-load-test-using-the-virtual-user-activity-chart"></a>방법: 가상 사용자 동작 차트를 사용하여 부하 테스트 중에 가상 사용자가 수행하는 작업 분석

가상 사용자 동작 차트를 사용하여 부하 테스트와 관련된 가상 사용자 동작을 확인합니다. 차트의 각 행은 개별 가상 사용자를 나타냅니다. 가상 사용자 동작 차트에는 각 가상 사용자가 테스트 중에 실행한 작업이 정확하게 표시됩니다. 사용자 동작의 패턴(부하 패턴)을 확인하고, 실패했거나 느린 테스트를 연결하고, 다른 가상 사용자 동작 요청을 확인할 수 있습니다. 가상 사용자 동작 차트는 부하 테스트를 완료한 이후에만 사용할 수 있습니다.

아래의 절차에서는 가상 사용자 동작 차트를 보는 방법, 특정 사용자 동작을 조사하는 방법, 필터 사용 방법 등을 보여 줍니다.

## <a name="to-view-the-virtual-user-activity-chart-in-your-load-test-results"></a>부하 테스트 결과에서 가상 사용자 동작 차트를 보려면

1.  가상 사용자 데이터를 보려면 부하 테스트와 연결된 **타이밍 정보 저장소** 속성에 대한 **모든 개인 정보** 설정을 구성해야 합니다. 그런 다음 부하 테스트를 실행합니다. 자세한 내용은 [방법: 가상 사용자 동작 차트를 활성화하도록 전체 정보 수집 구성](../test/how-to-configure-load-tests-to-collect-full-details.md)을 참조하세요.

2.  부하 테스트를 실행하면 테스트 결과 요약 페이지가 표시됩니다. 도구 모음에서 **사용자 정보** 단추를 선택합니다.

     또는

     도구 모음에서 **그래프** 단추를 선택하여 그래프 뷰를 엽니다. 그래프를 마우스 오른쪽 단추로 클릭한 다음, **사용자 정보로 이동**을 선택합니다.

     이 옵션을 사용하는 경우 가상 사용자 동작 차트가 마우스 오른쪽 단추를 클릭한 테스트 부분으로 자동 확대/축소됩니다. 예를 들어 약 30초 표시에 포인터를 놓으면 세부 정보 뷰가 가상 사용자 동작 차트의 아래쪽에 있는 **특정 기간 확대** 도구에서 약 30초 표시에 나타납니다.

     가상 사용자 동작 차트에서 특정 사용자 동작 정보를 조사할 수 있습니다.

## <a name="to-investigate-a-specific-users-activity-in-the-virtual-user-activity-chart"></a>가상 사용자 동작 차트에서 특정 사용자 동작을 조사하려면

1.  가상 사용자 동작 차트의 아래쪽에 있는 특정 기간 확대 도구를 사용하여 차트에서 특정 사용자에 대한 정보를 조사할 영역을 선택합니다.

2.  그래프의 특정 정보에 포인터를 올려 놓습니다. 다음 정보가 도구 설명에 표시됩니다.

    -   **User Id**

    -   **시나리오**

    -   **테스트**

    -   **URL**(테스트 또는 트랜잭션에 표시되지 않음)

    -   **결과**

    -   **브라우저**(테스트 또는 트랜잭션에 표시되지 않음)

    -   **Network**

    -   **시작 시간**

    -   **기간**

    -   **에이전트**

    -   **테스트 로그**(테스트 로그 링크)

        > [!NOTE]
        > 응용 프로그램 디버깅을 돕기 위해 테스트 로그 링크를 선택하면 로그에 연결된 웹 테스트 결과 또는 단위 테스트 결과가 열립니다.

     가상 사용자 동작 차트에 제공되는 필터링 및 강조 표시 작업을 사용할 수 있습니다.

## <a name="to-use-filtering-options-in-the-virtual-user-activity-chart"></a>가상 사용자 동작 차트에서 필터링 옵션을 사용하려면

1.  정보 범례에서 드롭다운 목록을 사용하여 **테스트**, **페이지** 또는 **트랜잭션**을 선택합니다.

     **정보 범례 패널**

     ![정보 범례 패널](../test/media/ltest_detailslegend.png "LTest_DetailsLegend")

2.  부하 테스트와 연결된 오류, 로그, 테스트, 검색 및 aspx 페이지에 대한 확인란을 선택하거나 선택 취소합니다.

     가상 사용자 동작 차트가 적절하게 업데이트됩니다.

     가상 사용자 동작 차트를 사용하여 다양한 기준에 따라 테스트, 페이지 및 트랜잭션을 필터링할 수 있습니다. 특정 테스트를 뷰에서 제거하거나, 모든 성공한 테스트를 제거하거나, 특정 오류로 실패한 테스트를 제거할 수 있습니다. 또한 로그가 없는 모든 테스트를 제거할 수 있습니다.

     예를 들어 **(오류 강조 표시)** 옵션을 선택할 수 있습니다. 그러면 모든 오류가 차트에 빨간색으로 표시됩니다. **(로그 포함 결과 강조 표시)** 옵션을 선택할 수도 있습니다. 그러면 로그가 있는 모든 테스트 결과가 차트에 녹색으로 표시됩니다.

     **필터 결과 패널**

     ![필터 결과 패널](../test/media/ltest_filterresults.png "LTest_FilterResults")

3.  필터 결과에서 다음 필터 옵션에 대한 확인란을 선택하거나 선택 취소합니다.

    -   **로그 포함 결과만 표시** 테스트 로그가 연결되어 있는 테스트 결과만 표시합니다.

    -   **성공적인 결과 표시** 성공적인 결과를 표시합니다.

    -   **오류가 있는 결과 표시** 디버깅을 지원할 수 있는 오류가 있는 결과를 표시합니다.

        > [!NOTE]
        > 웹 성능 테스트 결과 뷰어 도구 모음에서 테이블 단추를 선택하여 **오류가 있는 결과 표시** 노드 아래에 나열된 오류 유형 목록을 자세히 조사할 수 있습니다. 자세한 내용은 [테이블 뷰에서 부하 테스트 결과 및 오류 분석](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)을 참조하세요.

     가상 사용자 동작 차트가 적절하게 업데이트됩니다.

## <a name="see-also"></a>참고 항목

- [세부 정보 뷰에서 가상 사용자 동작 분석](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [연습: 가상 사용자 동작 차트를 사용하여 문제 격리](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)