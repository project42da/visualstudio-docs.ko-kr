---
title: "GPU 작업 그래프 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.cpu.graph.gpu"
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# GPU 작업 그래프
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

GPU 작업 그래프 동시성 시각화 도우미에서 시간이 지남에 따라 사용 중인 DirectX 엔진 수로 측정 된 시스템에 DirectX 활동의 수준을 표시 합니다.  그래프는 특정 엔진을 사용한 기록이 표시 되지 않습니다.  엔진은 GPU 작업 처리를 하는 경우 사용 중인 것으로 간주 됩니다.  
  
## GPU 작업 그래프의 색상  
 현재 프로세스에서 DirectX 엔진 소비 녹색을 나타냅니다.  
  
 밝은 회색의 DirectX 엔진 시스템의 다른 프로세스에서 소비를 나타냅니다.  다른 프로세스에서의 DirectX 엔진의 소비량을 줄이려면 시스템에서 실행되는 다른 프로세스의 수를 줄입니다.  
  
 흰색은 시스템에서 사용하지 않는 DirectX 엔진의 가용성을 나타냅니다.  병렬 처리를 할 수 있는 기회가 더 많이 있으면 이러한 엔진을 현재 프로세스에서 사용할 수 있습니다.  일부 엔진은 특정 종류의 작업에만 사용할 수 있습니다.  
  
## 참고 항목  
 [사용률 뷰](../profiling/utilization-view.md)