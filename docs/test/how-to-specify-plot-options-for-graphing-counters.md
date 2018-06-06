---
title: Visual Studio에서 부하 테스트에 대한 그래프 카운터의 출력 옵션
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, graphing counters
ms.assetid: 1969c20b-e0eb-48f6-a49f-a9090cd86008
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 7a5f87a83b8c743ae869a700618051e07c8c2e75
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750924"
---
# <a name="how-to-specify-plot-options-for-graphing-counters"></a>방법: 그래프 카운터에 대한 출력 옵션 지정

**출력 옵션** 대화 상자를 사용하여 그래프에 표시되는 카운터의 색과 선 스타일을 변경할 수 있습니다. 범위를 특정 값으로 고정하거나 샘플링된 데이터에 따라 범위가 자동으로 조정되도록 설정할 수 있습니다.

![출력 옵션 대화 상자](../test/media/ltest_plotoptions.png)

## <a name="to-specify-plotting-options-for-graphs"></a>그래프의 출력 옵션을 지정하려면

1.  부하 테스트 분석기에서 부하 테스트 도구 모음의 **그래프**를 선택합니다.

     부하 테스트 결과가 그래프 뷰에 표시됩니다.

2.  범례나 그래프에서 출력 옵션을 변경할 성능 카운터의 행 또는 현재 그리기 선을 마우스 오른쪽 단추로 클릭하고 **출력 옵션**을 선택합니다.

     **출력 옵션** 대화 상자가 표시됩니다.

3.  **색** 드롭다운 목록에서 성능 카운터를 그래프에 표시하는 데 사용할 색을 선택합니다.

4.  **스타일** 드롭다운 목록에서 성능 카운터를 그래프에 표시하는 데 사용할 스타일을 선택합니다.

5.  다음 작업 중 하나를 수행합니다.

     **자동 범위 조정**(기본값) 선택

     \- 또는 -

     **자동 범위 조정**의 선택을 취소하고 **범위** 드롭다운 목록을 사용하여 성능 카운터를 그래프에 표시하는 데 사용할 범위를 지정합니다.

6.  **확인**을 선택합니다.

     옵션을 변경한 성능 카운터가 지정된 설정으로 그래프에 표시됩니다.

## <a name="see-also"></a>참고 항목

- [그래프 뷰에서 부하 테스트 결과 분석](../test/analyze-load-test-results-in-the-graphs-view.md)
- [방법: 사용자 지정 그래프 만들기](../test/how-to-create-custom-graphs-in-load-test-results.md)
- [그래프 뷰에서 부하 테스트 결과 분석](../test/analyze-load-test-results-in-the-graphs-view.md)