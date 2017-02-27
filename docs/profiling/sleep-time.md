---
title: "중지 시간 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.threads.timeline.sleep"
helpviewer_keywords: 
  - "동시성 시각화 도우미, 중지 시간"
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# 중지 시간
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

시간 표시 막대의 이러한 세그먼트는 중지로 분류되는 차단 시간과 연결되어 있습니다.  중지 범주는 스레드에서 자발적으로 논리 코어를 포기했으며 아무 작업도 수행하고 있지 않음을 의미합니다.  이 시간 동안 스레드는 동시성 시각화 도우미에서 중지로 간주하는 API에서 차단되어 있습니다.  `Sleep()` 및 `SwitchToThread()` 등의 API가 이 그룹에 포함됩니다.  
  
## 참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)