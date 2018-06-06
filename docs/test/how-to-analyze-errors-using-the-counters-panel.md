---
title: Visual Studio에서 카운터 패널을 사용하여 부하 테스트 오류 분석
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Load Test Analyzer, counters panel
ms.assetid: 981b4f1e-505a-4078-a06d-58ae17d996b4
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: bc7beb1100b5e1bfe3fd554da53520ffc9888e64
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751886"
---
# <a name="how-to-analyze-errors-using-the-counters-panel"></a>방법: 카운터 패널을 사용하여 오류 분석

카운터 패널은 부하 테스트가 실행되는 동안이나 부하 테스트 결과를 분석 중일 때 부하 테스트 분석기의 그래프 뷰와 테이블 뷰에 표시됩니다. 자세한 내용은 [그래프 뷰에서 부하 테스트 결과 분석](../test/analyze-load-test-results-in-the-graphs-view.md), [테이블 뷰에서 부하 테스트 결과 및 오류 분석](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) 및 [방법: 분석을 위한 부하 테스트 결과 액세스](../test/how-to-access-load-test-results-for-analysis.md)를 참조하세요.

 카운터 패널의 **오류** 노드에는 부하 테스트 시 발견된 모든 오류가 포함됩니다. 오류 노드에는 여러 다른 종류의 오류(예: **예외** 및 **HTTP 오류**)와 관련된 여러 하위 범주 오류 노드가 포함되어 있습니다.

 ![카운터 패널의 오류 노드](../test/media/ltest_errornode.png)

## <a name="to-analyze-errors-in-the-counters-panel"></a>카운터 패널에서 오류를 분석하려면

1.  부하 테스트가 완료된 후 또는 테스트 결과를 로드한 후, 부하 테스트 분석기의 도구 모음에서 **그래프** 또는 **테이블**을 선택합니다.

     **카운터** 패널이 그래프 뷰나 테이블 뷰에 표시됩니다.

2.  카운터 패널이 표시되지 않으면 도구 모음에서 **카운터 패널 표시**를 선택합니다.

3.  **오류**를 확장하고 분석할 오류 범주나 오류 하위 범주를 선택합니다.

4.  오류를 마우스 오른쪽 단추로 클릭하고 다음 옵션 중 하나를 선택합니다.

    -   **그래프에 카운터 표시**: 그래프 뷰에서 해당 오류가 선택한 그래프에 추가되고 강조 표시됩니다. 자세한 내용은 [방법: 그래프에 카운터 추가 및 삭제](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)를 참조하세요.

    -   **범례에 카운터 표시**: 해당 오류가 범례에 추가되고 강조 표시됩니다. 자세한 내용은 [그래프 뷰 범례를 사용하여 부하 테스트 분석](../test/use-the-graphs-view-legend-to-analyze-load-tests.md)을 참조하세요.

    -   **그래프 추가**:

    1.  **그래프 이름 입력** 대화 상자가 표시됩니다.

    2.  **그래프 이름** 텍스트 상자에 새 그래프의 이름을 입력하고 **확인**을 선택합니다.

    3.  (선택 사항) 오류를 다시 마우스 오른쪽 단추로 클릭하고 **그래프에 카운터 표시**를 선택합니다.

         자세한 내용은 [방법: 사용자 지정 그래프 만들기](../test/how-to-create-custom-graphs-in-load-test-results.md)를 참조하세요.

5.  (선택 사항) 완료된 부하 테스트 결과에서 오류를 분석하는 경우 그래프의 확대/축소 기능을 사용하는 것이 좋습니다. 자세한 내용은 [방법: 그래프의 영역으로 확대](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)를 참조하세요.

    > [!TIP]
    > 부하 테스트를 실행하는 동안 오류가 발견된 경우 "오류"라는 링크가 발견된 횟수와 함께 부하 테스트 분석기 상태 표시줄에 표시됩니다. 이 링크를 선택하여 모든 오류를 테이블 뷰의 **오류** 테이블에 표시할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [그래프 뷰 및 테이블 뷰의 카운터 패널 사용](../test/counters-panel-in-load-test-analyzer.md)
- [부하 테스트 결과 분석](../test/analyze-load-test-results-using-the-load-test-analyzer.md)