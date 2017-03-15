---
title: "스레드 목록 표시 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.listthreads"
helpviewer_keywords: 
  - "Debug.ListThreads 명령"
  - "스레드 목록 표시 명령"
  - "ListThreads 명령"
ms.assetid: 34b665c0-d46f-4c1a-a066-b678eba5ac54
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 스레드 목록 표시 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

현재 프로그램에 있는 스레드의 목록을 표시합니다.  
  
## 구문  
  
```  
Debug.ListThreads [index]  
```  
  
## 인수  
 `index`  
 선택적 요소.  인덱스를 사용하여 현재 스레드가 될 스레드를 선택합니다.  
  
## 설명  
 `index` 인수를 지정하면 지정된 스레드가 현재 스레드로 표시됩니다.  목록에서 현재 스레드 옆에 별표\(\*\)가 표시됩니다.  
  
## 예제  
  
```  
>Debug.ListThreads   
```  
  
## 참고 항목  
 [호출 스택 목록 표시 명령](../../ide/reference/list-call-stack-command.md)   
 [디스어셈블리 목록 표시 명령](../../ide/reference/list-disassembly-command.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)