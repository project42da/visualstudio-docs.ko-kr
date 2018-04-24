---
title: 범위 표식 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.markers.span
ms.assetid: 736b7765-9c71-44d7-85e5-79787d13d91c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f6952408611bfdd59a3d488db2a7f34524588edf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="span-markers"></a>범위 표식
범위 표식은 응용 프로그램에서 중요한 한 단계를 나타냅니다. 예를 들어 범위를 사용하면 특정 작업 항목을 처리하는 기간의 간격을 나타낼 수 있습니다. 범위의 길이는 해당 응용 프로그램 단계의 길이를 나타냅니다. 다음 그림은 동시성 시각화 도우미에서 범위를 보여줍니다.  
  
 ![Concurrency 시각화의 범위 표식](../profiling/media/cvmarkerspan.png "CVMarkerSpan")  
동시성 시각화 도우미의 범위 표식  
  
## <a name="span-category"></a>범위 범주  
 범위 표식은 해당 범주에 따라 5가지 색상 중 하나로 표시됩니다. 범주가 5개 이상이면 색상이 반복됩니다. 범주는 임의의 정수일 수 있습니다. 다음 그림은 5가지 사용 가능한 색상을 보여줍니다.  
  
 ![다양한 범주의 5가지 범위](../profiling/media/cvmarkerspancategory.png "CVMarkerSpanCategory")  
처음 5개 범위 범주에 대한 색상  
  
## <a name="span-aggregation-markers"></a>범위 집계 표식  
 일부 경우에는 동시성 시각화 도우미에서 범위 표식이 너무 가깝게 표시되어 개별적으로 그리기 어려울 수 있습니다. 이 경우에는 내부 범위를 나타내는 회색 *범위 집계 표식*이 표시됩니다. 이러한 아이콘 중 하나에 포인터를 놓으면 안에 있는 범위 수가 도구 설명에 표시됩니다. 범위를 보려면 확대하십시오. 끝까지 확대해도 범위 집계 표식이 보이면 [표식 보고서](../profiling/markers-report.md)에서 내부 범위 표식을 볼 수 있습니다. 다음 그림은 범위 집계 표식을 보여줍니다.  
  
 ![Concurrency 시각화의 집계 범위 표식](../profiling/media/cvmarkerspanaggregate.png "CVMarkerSpanAggregate")  
범위 집계 표식  
  
## <a name="see-also"></a>참고 항목  
 [동시성 시각화 도우미 표식](../profiling/concurrency-visualizer-markers.md)   
 [동시성 시각화 도우미 SDK](../profiling/concurrency-visualizer-sdk.md)