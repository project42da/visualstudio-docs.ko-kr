---
title: 코어 뷰 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.cores
helpviewer_keywords:
- Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: beec52fe827162720c7c5040f91655d7db02c7e7
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750219"
---
# <a name="cores-view"></a>코어 뷰
**코어 뷰**에는 스레드 실행이 논리 프로세서 코어에 매핑된 방법이 표시됩니다(**분석**>**동시성 시각화 도우미**를 선택하여 동시성 시각화 도우미 시작). 서버 응용 프로그램을 작성할 때 이 뷰를 통해 스레드 선호도 또는 스레드 풀 관리를 사용하여 캐시 성능을 최적화할 수 있습니다. 또한 스레드 선호도를 사용해서 코어 간 마이그레이션 문제가 더 심각해질 수 있는 경우를 조사할 수 있습니다. 코어 뷰에는 그래프와 범례의 두 부분이 포함됩니다.  
  
 그래프에서 Y축에는 논리 코어가 표시되고 X축에는 시간이 표시됩니다. 그래프의 모든 스레드에는 시간 경과에 따라 코어 간 이동을 추적할 수 있도록 고유 색상이 포함됩니다. 범례 영역에서 스레드를 선택하면 이 그래프에서 스레드를 필터링할 수 있습니다.  
  
 범례 영역에는 그래프의 각 색상에 대한 항목이 포함됩니다. 각 항목은 스레드 색상과 이름, 코어 간 컨텍스트 전환 횟수, 총 컨텍스트 전환 횟수 및 코어 간 컨텍스트 전환 비율을 보여줍니다. 범례는 코어 간 컨텍스트 전환 횟수를 기준으로 내림차순으로 정렬됩니다. 표시된 시간 범위 중에 실행된 스레드만 나열됩니다.  확대/축소하거나 이동하면 목록이 업데이트됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [동시성 시각화 도우미](../profiling/concurrency-visualizer.md)   
 [사용률 뷰](../profiling/utilization-view.md)   
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)