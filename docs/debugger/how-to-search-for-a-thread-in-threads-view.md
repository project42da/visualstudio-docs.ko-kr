---
title: "How to: Search for a Thread in Threads View | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "threads, searching"
ms.assetid: 5609a9b3-c279-4426-9e2e-dd87896a6d6f
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# How to: Search for a Thread in Threads View
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

스레드 ID나 모듈 문자열을 검색 조건으로 사용하여 스레드 뷰에서 특정 스레드를 검색할 수 있으며,  검색의 초기 방향을 지정할 수도 있습니다.  이 대화 상자의 필드에는 스레드 트리에서 선택한 스레드의 특성이 표시됩니다.  
  
### 스레드 뷰에서 스레드를 검색하려면  
  
1.  Spy\+\+와 활성 [스레드 뷰](../debugger/threads-view.md) 창이 보이도록 창을 정렬합니다.  
  
2.  **검색** 메뉴에서 **스레드 찾기**를 선택합니다.  
  
     [스레드 검색 대화 상자](../debugger/thread-search-dialog-box.md)가 열립니다.  
  
3.  스레드 ID나 모듈 문자열을 검색 조건으로 입력합니다.  
  
4.  값을 지정하지 않을 모든 필드를 지웁니다.  
  
    > [!TIP]
    >  모듈이 소유하고 있는 모든 스레드를 찾으려면 **스레드** 텍스트 상자를 지우고 **모듈** 상자에 모듈 이름을 입력합니다.  그런 후 **다음 찾기**를 사용하여 스레드를 계속 검색합니다.  
  
5.  검색의 초기 방향으로 **위로** 또는 **아래로**를 선택합니다.  
  
6.  **확인**을 클릭합니다.  
  
 일치하는 스레드가 발견되면 스레드 뷰 창에서 강조 표시됩니다.