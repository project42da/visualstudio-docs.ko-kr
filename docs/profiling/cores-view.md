---
title: "코어 뷰 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.view.cores"
helpviewer_keywords: 
  - "동시성 시각화 도우미, 코어 뷰"
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# 코어 뷰
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

코어 뷰 논리 프로세서 코어에 매핑된 스레드 실행 방법을 보여 줍니다.  서버 응용 프로그램을 작성할 때 이 뷰를 통해 스레드 선호도 또는 스레드 풀 관리를 사용하여 캐시 성능을 최적화할 수 있습니다.  또한 이 뷰에서는 스레드 선호도를 사용함으로써 실제로 교차 코어 마이그레이션의 문제가 악화된 경우를 쉽게 시험할 수 있습니다.  코어 뷰 범례를 그래프와 두 부분에 있습니다.  
  
 위쪽 그래프에서 Y축에는 논리 코어가 표시되고 X축에는 시간이 표시됩니다.  시간 경과에 따른 각 스레드의 코어 이동을 볼 수 있도록 그래프의 모든 스레드는 고유 색으로 표시됩니다.  이 그래프에 스레드 범례 영역에서 선택하여 필터링 할 수 있습니다.  
  
 범례 영역 그래프에서 각 색상에 대한 항목이 있습니다.  스레드 색과 이름, 코어 간 컨텍스트 전환 횟수, 총 컨텍스트 전환 횟수, 코어간 컨텍스트 전환의 백분율이 여기에 표시됩니다.  범례는 코어 간 컨텍스트 전환 횟수를 기준으로 내림차순으로 정렬됩니다.  표시된 시간 범위 동안 실행 스레드를 나열 합니다.  확대\/축소 하거나 팬 하면 목록이 업데이트 됩니다.  
  
## 참고 항목  
 [동시성 시각화 도우미](../profiling/concurrency-visualizer.md)   
 [사용률 뷰](../profiling/utilization-view.md)   
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)