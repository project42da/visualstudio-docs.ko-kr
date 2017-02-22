---
title: "동기화 시간 | Microsoft Docs"
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
  - "vs.cv.threads.timeline.synchronization"
helpviewer_keywords: 
  - "동시성 시각화 도우미, 동기화 시간"
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 동기화 시간
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

시간 표시 막대의 이러한 세그먼트는 동기화로 분류되는 차단 시간과 연결되어 있습니다.  스레드가 동기화 중 차단된 것으로 표시될 경우 다음 중 하나를 나타냅니다.  
  
-   스레드 실행 결과로 `EnterCriticalSection()` 또는 `WaitForSingleObject()`와 같은 잘 알려진 스레드 동기화 API가 호출되었을 수 있습니다.  
  
-   API 일치 알고리즘은 완전히 포괄적일 수 없으며, 따라서 호출 스택의 프레임은 최종적으로는 이 범주에 매핑된 내부 커널 차단 기본 형식에 도달하므로 다른 범주에 매핑될 수 있는 일부 API도 동기화로 나타날 수 있습니다.  
  
 스레드 차단 이벤트의 근본 원인을 파악하려면 차단 호출 스택과 프로필 보고서를 주의 깊게 조사해야 합니다.  
  
## 참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)