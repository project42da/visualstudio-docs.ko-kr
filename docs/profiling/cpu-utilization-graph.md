---
title: "CPU 사용률 그래프 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.cpu.graph"
helpviewer_keywords: 
  - "CPU 사용률 그래프 동시성 시각화 도우미, CPU 사용률 그래프"
ms.assetid: 5332fd38-622d-47a3-874f-8c2fd7a30f95
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# CPU 사용률 그래프
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

CPU 사용률 그래프에서는 시간 경과에 따른 응용 프로그램의 응용 수준을 보여 줍니다.  x축은 응용 프로그램의 기간을 나타내고 y축은 시스템의 논리 코어 수를 나타냅니다.  이 그래프에서는 특정 시간에 활성 상태인 코어를 구체적으로 보여 주지는 않습니다.  예를 들어 특정 시간 동안 두 개의 코어가 각각 50% 용량으로 실행되는 경우 이 뷰에서는 하나의 논리 코어가 사용되고 있는 것으로 표시됩니다.  
  
## CPU 사용률 그래프의 색상  
  
-   녹색은 프로파일링된 응용 프로그램에서 소비하는 시스템의 논리 코어를 나타냅니다.  
  
-   노란색은 시스템의 다른 프로세스에서 사용하는 논리 코어를 나타냅니다.  그래프에서 노란색이 차지하는 비율이 높으면 다른 프로세스에 의한 시스템 부하가 높으며 현재 프로세스는 이러한 프로세스에 의해 선점될 가능성이 있음을 나타냅니다.  다른 프로세스에서의 논리 코어 소비량을 줄이려면 시스템에서 실행되는 다른 프로세스의 수를 줄입니다.  
  
-   짙은 회색은 시스템 프로세스에서 소비하는 논리 코어를 나타냅니다.  이는 직접 제어할 수 없지만 현재 프로세스의 논리 코어 가용성이 영향을 받을 수 있으므로 이러한 논리 코어 소비 형태가 나타나는 경우를 알고 있으면 유용합니다.  
  
-   하얀색은 시스템에서 사용되지 않는 논리 코어의 가용성을 나타냅니다.  병렬 처리를 할 수 있는 기회가 더 많이 있으면 이러한 코어를 현재 프로세스에서 사용할 수 있습니다.  
  
## 참고 항목  
 [사용률 뷰](../profiling/utilization-view.md)   
 [평균 CPU 사용률](../profiling/average-cpu-utilization.md)