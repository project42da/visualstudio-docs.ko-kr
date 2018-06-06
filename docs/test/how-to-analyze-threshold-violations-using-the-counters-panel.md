---
title: Visual Studio에서 부하 테스트에 대한 임계값 위반
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, threshold violations
ms.assetid: 0126d7b7-0538-4ea9-9046-6556654b3b9d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: fdb54122344ce91fe873d854768d0890a83f198a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751808"
---
# <a name="how-to-analyze-threshold-violations-using-the-counters-panel-in-load-test-analyzer"></a>방법: 부하 테스트 분석기의 카운터 패널을 사용하여 임계값 위반 분석

카운터 패널은 부하 테스트가 실행되는 동안이나 부하 테스트 결과를 분석 중일 때 부하 테스트 분석기의 그래프 뷰와 테이블 뷰에 표시됩니다. [그래프 뷰에서 부하 테스트 결과 분석](../test/analyze-load-test-results-in-the-graphs-view.md), [테이블 뷰에서 부하 테스트 결과 및 오류 분석](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) 및 [방법: 분석을 위한 부하 테스트 결과 액세스](../test/how-to-access-load-test-results-for-analysis.md)를 참조하세요.

 임계값 위반은 특정 성능 카운터와 연결되며, 성능 카운터가 설정된 임계값을 초과했거나 그 아래로 떨어졌음을 나타냅니다. 카운터 패널의 아이콘을 통해 임계값 위반이 표시됩니다.

 ![카운터 패널의 컴퓨터 노드](../test/media/ltest_compnode.png)

 임계값 위반에 대한 아이콘은 오류가 발생한 카운터가 있는 트리 노드에서 루트로 전파됩니다. 이러한 아이콘을 통해 사용자는 트리를 확장하지 않아 트리에 카운터가 표시되지 않은 경우에도 카운터에서 위반이 발생했음을 확인할 수 있습니다. 이 아이콘의 예는 위 그림의 카운터 패널에 있는 **컴퓨터 노드**에서 볼 수 있습니다.

 이러한 아이콘은 다음 중 하나입니다.

 ![임계값 위반 없음](../test/media/icon_ltest_1.gif) 임계값 위반 없음

 ![마지막 기간에서 중요한 임계값 위반 발생](../test/media/icon_ltest_2.gif) 마지막 간격에서 중요 임계값 위반이 발생함

 ![이전 기간에서 중요한 임계값 위반 발생](../test/media/icon_ltest_3.gif) 이전 간격에서 중요 임계값 위반이 발생함

 ![마지막 기간에서 경고 임계값 위반 발생](../test/media/icon_ltest_4.gif) 마지막 간격에서 경고 임계값 위반이 발생함

 ![이전 기간에서 경고 임계값 위반 발생](../test/media/icon_ltest_5.gif) 이전 간격에서 경고 임계값 위반이 발생함

## <a name="to-analyze-threshold-violations-in-the-counters-panel"></a>카운터 패널에서 임계값 위반을 분석하려면

1.  부하 테스트가 완료된 후 또는 테스트 결과를 로드한 후, 부하 테스트 분석기의 도구 모음에서 **그래프** 또는 **테이블**을 선택합니다.

     카운터 패널이 그래프 뷰나 테이블 뷰에 표시됩니다.

2.  카운터 패널이 표시되지 않으면 도구 모음에서 **카운터 패널 표시**를 선택합니다.

     임계값 위반이 발생한 노드에는 위에 나열된 아이콘 중 하나가 포함됩니다.

3.  위의 "카운터 패널에서 임계값 위반으로 표시된 컴퓨터 노드" 그림에 표시된 **컴퓨터** 노드와 같이 임계값 아이콘이 포함된 노드를 확장합니다. 임계값 위반이 발생한 성능 카운터에 도달할 때까지 노드를 계속 확장합니다. 예를 들어 위의 그림에서는 오류가 발생한 **Microsoft 가상 머신 버스 네트워크 어댑터** 인스턴스를 보여 줍니다.

4.  (선택 사항) 임계값 위반이 발생한 성능 카운터를 마우스 오른쪽 단추로 클릭하고 다음 옵션 중 하나를 선택합니다.

    -   **그래프에 카운터 표시**: 그래프 뷰에서 해당 성능 카운터가 선택한 그래프에 추가되고 강조 표시됩니다. 자세한 내용은 [방법: 그래프에서 카운터 추가 및 삭제](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)를 참조하세요.

        > [!NOTE]
        > 그래프 뷰의 그래프에 임계값 위반 아이콘이 표시될 수도 있습니다. 임계값 아이콘은 그래프에서 임계값 위반이 발생한 데이터 요소 옆에 표시됩니다. 이렇게 하려면 도구 모음에서 **범례 표시** 드롭다운을 선택하고 **그래프에 임계값 위반 표시**를 선택합니다.

    -   **범례에 카운터 표시**: 범례에서 해당 성능 카운터가 추가되고 강조 표시됩니다. 자세한 내용은 [그래프 뷰 범례를 사용하여 부하 테스트 분석](../test/use-the-graphs-view-legend-to-analyze-load-tests.md)을 참조하세요.

    -   **그래프 추가**:

    1.  **그래프 이름 입력** 대화 상자가 표시됩니다.

    2.  **그래프 이름** 텍스트 상자에 새 그래프의 이름을 입력하고 **확인**을 선택합니다.

    3.  (선택 사항) 성능 카운터를 다시 마우스 오른쪽 단추로 클릭하고 **그래프에 카운터 표시**를 선택합니다.

         자세한 내용은 [방법: 사용자 지정 그래프 만들기](../test/how-to-create-custom-graphs-in-load-test-results.md)를 참조하세요.

5.  (선택 사항) 완료된 부하 테스트 결과에서 임계값 위반을 분석하는 경우 그래프 뷰의 확대/축소 기능을 사용하는 것이 좋습니다. 자세한 내용은 [방법: 그래프의 영역으로 확대](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)를 참조하세요.

    > [!TIP]
    > 부하 테스트를 실행하는 동안 임계값 위반이 발견된 경우 "임계값 위반"이라는 링크가 위반 횟수와 함께 부하 테스트 분석기 상태 표시줄에 표시됩니다. 이 링크를 선택하여 모든 임계값 위반을 테이블 뷰의 **임계값** 테이블에 표시할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [그래프 뷰 및 테이블 뷰의 카운터 패널 사용](../test/counters-panel-in-load-test-analyzer.md)
- [부하 테스트 결과 분석](../test/analyze-load-test-results-using-the-load-test-analyzer.md)