---
title: "Spy++ Toolbar | Microsoft Docs"
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
  - "Spy++ toolbar"
ms.assetid: 949c18fb-bb25-42ed-9130-c4a47869f24d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Spy++ Toolbar
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Spy\+\+에서 도구 모음은 메뉴 모음 아래에 표시됩니다.  도구 모음을 표시하거나 숨기려면 **보기** 메뉴에서 **도구 모음**을 클릭합니다.  
  
 다음 컨트롤은 도구 모음에서 사용할 수 있습니다.  
  
## UI 요소 목록  
  
|Button|Effect|  
|------------|------------|  
|![Spy&#43;&#43; Windows 단추](../debugger/media/icon_spy--_windows.png "Icon\_Spy\+\+\_Windows")|시스템에 창 및 컨트롤의 트리 뷰를 표시합니다.  자세한 내용은 [Windows View](../debugger/windows-view.md)를 참조하십시오.|  
|![Spy&#43;&#43; 프로세스 단추](../debugger/media/icon_spy--_processes.png "Icon\_Spy\+\+\_Processes")|시스템에 프로세스의 트리 뷰를 표시합니다.  자세한 내용은 [Processes View](../debugger/processes-view.md)를 참조하십시오.|  
|![Spy&#43;&#43; 스레드 단추](../debugger/media/icon_spy--_threads.png "Icon\_Spy\+\+\_Threads")|시스템에 스레드의 트리 뷰를 표시합니다.  자세한 내용은 [Threads View](../debugger/threads-view.md)를 참조하십시오.|  
|![Spy&#43;&#43; 메시지 단추](../debugger/media/icon_spy--_messages.png "Icon\_Spy\+\+\_Messages")|창 메시지를 표시하는 창을 만들고 메시지가 표시될 창을 선택하고 다른 옵션도 선택할 수 있도록 **메시지 옵션** 대화 상자를 엽니다.  자세한 내용은 [Messages View](../debugger/messages-view.md)를 참조하십시오.|  
|![Spy&#43;&#43; 로그 시작 단추](../debugger/media/icon_spy--_startlog.png "Icon\_Spy\+\+\_StartLog")|메시지 로깅을 시작하고 메시지 스트림을 표시합니다.  이 컨트롤은 **메시지** 창이 활성 창인 경우에만 사용할 수 있습니다.  자세한 내용은 [How to: Start and Stop the Message Log Display](../debugger/how-to-start-and-stop-the-message-log-display.md)를 참조하십시오.|  
|![Spy&#43;&#43; 로그 중지 단추](../debugger/media/icon_spy--_stoplog.png "Icon\_Spy\+\+\_StopLog")|메시지 로깅과 메시지 스트림 표시를 중지합니다.  이 컨트롤은 **메시지** 창이 활성 창인 경우에만 사용할 수 있습니다.  자세한 내용은 [How to: Start and Stop the Message Log Display](../debugger/how-to-start-and-stop-the-message-log-display.md)를 참조하십시오.|  
|![Spy&#43;&#43; 로그 옵션 단추](../debugger/media/icon_spy--_logoptions.png "Icon\_Spy\+\+\_LogOptions")|[메시지 옵션](../debugger/message-options-dialog-box.md) 대화 상자를 표시합니다.  표시할 창과 메시지 형식을 선택하려면 이 대화 상자를 사용합니다.  이 컨트롤은 **메시지** 창이 활성 창인 경우에만 사용할 수 있습니다.|  
|![Spy&#43;&#43; 로그 지우기 단추](../debugger/media/spy--_clearlog.png "Spy\+\+\_ClearLog")|활성 **메시지** 창의 내용을 지웁니다.  이 컨트롤은 **메시지** 창이 활성 창인 경우에만 사용할 수 있습니다.|  
|![Spy&#43;&#43; 창 찾기 단추](../debugger/media/icon_spy--_findwindow.png "Icon\_Spy\+\+\_FindWindow")|창 검색 기준을 설정하고 속성이나 메시지를 표시할 수 있는 [찾기 창](../debugger/find-window-dialog-box.md) 대화 상자를 엽니다.  자세한 내용은 [How to: Use the Finder Tool](../debugger/how-to-use-the-finder-tool.md)를 참조하십시오.|  
|![Spy&#43;&#43; 첫 번째 창 찾기 단추](../debugger/media/icon_spy--_window.png "Icon\_Spy\+\+\_Window")|일치하는 창, 프로세스, 스레드 또는 메시지의 현재 뷰를 검색합니다.|  
|![Spy&#43;&#43; 다음 창 찾기 단추](../debugger/media/icon_spy--_nextwindow.png "Icon\_Spy\+\+\_NextWindow")|일치하는 다음 창, 프로세스, 스레드 또는 메시지의 현재 뷰를 검색합니다.  이 컨트롤과 관련 메뉴 명령은 고유하지 않은 유효한 검색 결과가 있는 경우에만 사용할 수 있습니다.  예를 들어, 창 트리에서 창 핸들을 검색 조건으로 사용하면 창 트리에서 이 핸들을 가진 창이 하나만 있기 때문에 고유한 결과가 생성됩니다. 이 인스턴스에서는 **다음 찾기**는 사용할 수 없습니다.|  
|![Spy&#43;&#43; 이전 창 찾기 단추](../debugger/media/icon_spy--_prevwindow.png "Icon\_Spy\+\+\_PrevWindow")|일치하는 이전 창, 프로세스, 스레드 또는 메시지의 현재 뷰를 검색합니다.  이 컨트롤과 관련 메뉴 명령은 고유하지 않은 유효한 검색 결과가 있는 경우에만 사용할 수 있습니다.  예를 들어, 창 트리에서 창 핸들을 검색 조건으로 사용하면 창 트리에서 이 핸들을 가진 창이 하나만 있기 때문에 고유한 결과가 생성됩니다. 이 인스턴스에서는 **이전 찾기**는 사용할 수 없습니다.|  
|![Spy&#43;&#43; 속성 탐색기 단추](../debugger/media/icon_spy--_propexp.png "Icon\_Spy\+\+\_PropExp")|창 뷰에서 선택한 창의 속성을 표시합니다.|  
|![Spy&#43;&#43; 새로 고침 단추](../debugger/media/icon_spy--_refresh.png "Icon\_Spy\+\+\_Refresh")|시스템 뷰를 새로 고칩니다.|  
  
## 참고 항목  
 [Using Spy\+\+](../debugger/using-spy-increment.md)   
 [Spy\+\+ Views](../debugger/spy-increment-views.md)   
 [Spy\+\+ Reference](../debugger/spy-increment-reference.md)