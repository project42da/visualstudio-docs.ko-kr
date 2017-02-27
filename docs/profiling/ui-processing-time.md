---
title: "UI 처리 시간 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.threads.timeline.uiprocessing"
helpviewer_keywords: 
  - "동시성 시각화 도우미, UI 처리 시간"
ms.assetid: 0ddb05a3-8c6b-448b-8488-2751c1e5abcc
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# UI 처리 시간
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

시간 표시 막대의 이러한 세그먼트는 UI 처리로 분류되는 차단 시간과 연결되어 있습니다.  UI 처리란 스레드에서 Windows 메시지를 펌프하거나 다른 UI\(사용자 인터페이스\) 작업을 수행하고 있음을 의미합니다.  이 시간 동안 스레드는 동시성 시각화 도우미에서 UI 처리로 간주하는 API에서 차단되어 있습니다.  `GetMessage()` 및 `MsgWaitForMultipleObjects()` 등의 API가 이 그룹에 포함됩니다.  
  
 미리 정의된 차단 API가 확인되지 않으면 호출 스택과 프로필 보고서를 검토하여 근본적인 지연 원인을 확인합니다.  
  
 UI 처리 범주는 GUI 응용 프로그램의 응답성을 파악하는 데 중요하며, UI 응답성의 영향을 많이 받는 응용 프로그램에서 유용하게 사용됩니다.  예를 들어 응용 프로그램의 UI 스레드에서 UI 처리에 소요하는 시간이 100%에 도달하면 응답성이 매우 좋은 것입니다.  하지만 UI 스레드에서 다른 범주에 상당한 시간을 소요하는 경우에는 근본 원인을 찾고 해당 스레드에서 UI 이외의 범주를 줄이는 옵션을 사용하는 것이 좋습니다.  
  
## 참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)