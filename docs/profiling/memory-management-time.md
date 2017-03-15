---
title: "메모리 관리 시간 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.threads.timeline.paging"
helpviewer_keywords: 
  - "동시성 시각화 도우미, 페이징 시간"
ms.assetid: 67af3509-3a7d-435d-bc37-5262448da915
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 메모리 관리 시간
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

시간 표시 막대의 이러한 세그먼트는 메모리 관리로 분류되는 차단 시간과 연결되어 있습니다.  이는 페이징 등의 메모리 관리 작업과 관련된 이벤트에 의해 스레드가 차단되었음을 의미합니다.  이 시간 동안 스레드는 동시성 시각화 도우미에서 메모리 관리로 간주하는 API 또는 커널 상태에서 차단되어 있습니다.  여기에는 페이징 및 메모리 할당 등의 이벤트가 포함됩니다.  
  
 관련된 호출 스택과 프로필 보고서를 검사하여 메모리 관리로 분류되는 차단에 대한 근본적인 원인을 보다 쉽게 파악할 수 있습니다.  
  
## 참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)