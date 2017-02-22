---
title: "How to: Search for a Message in Messages View | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Message Search dialog box"
  - "Messages view"
  - "messages, searching for"
ms.assetid: 732b7ccc-54ea-41db-823b-2b96e3e4083e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# How to: Search for a Message in Messages View
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

핸들, 형식 또는 메시지 ID를 검색 조건으로 사용하여 메시지 뷰에서 특정 메시지를 검색할 수 있습니다.  이러한 요소 중 하나 또는 이러한 요소의 조합은 유효한 검색 조건으로 사용됩니다.  또한 검색의 초기 방향을 지정할 수도 있습니다.  이 대화 상자의 필드에는 현재 선택된 메시지의 특성이 미리 로드됩니다.  
  
### 메시지 뷰에서 메시지를 검색하려면  
  
1.  Spy\+\+와 활성 [메시지 뷰](../debugger/messages-view.md) 창이 보이도록 창을 정렬합니다.  
  
2.  **검색** 메뉴에서 **메시지 찾기**를 선택합니다.  
  
     [메시지 검색 대화 상자](../debugger/message-search-dialog-box.md)가 열립니다.  
  
3.  **찾기 도구**를 원하는 창 위로 끌어 옵니다.  이 도구를 끌어 올 때 **메시지 검색** 대화 상자에는 선택된 창의 세부 내용이 표시됩니다.  
  
     – 또는 –  
  
     메시지를 검사할 창의 핸들이 있으면 **핸들** 텍스트 상자에 이 핸들을 입력합니다.  
  
     – 또는 –  
  
     원하는 메시지 형식 및\/또는 메시지 ID를 알고 있으면 **형식**과 **메시지** 드롭다운 메뉴에서 해당 메시지 형식과 메시지 ID를 각각 선택하고 **핸들** 텍스트 상자를 지웁니다.  
  
4.  값을 지정하지 않을 모든 필드를 지웁니다.  
  
    > [!TIP]
    >  화면을 간결하게 만들려면 **Spy 숨기기** 옵션을 선택합니다.  이 옵션은 Spy\+\+의 주 창을 숨기고 **창 찾기** 대화 상자만 다른 응용 프로그램 위에 표시된 상태로 둡니다.  **확인** 또는 **취소**를 클릭하거나 **Spy\+\+ 숨기기** 옵션의 선택을 취소하면 Spy\+\+의 주 창이 복원됩니다.  
  
5.  검색의 초기 방향으로 **위로** 또는 **아래로**를 선택합니다.  
  
6.  **확인**을 클릭합니다.  
  
 일치하는 메시지가 발견되면 메시지 뷰 창에서 강조 표시됩니다.  [메시지 뷰](../debugger/messages-view.md)를 참조하십시오.