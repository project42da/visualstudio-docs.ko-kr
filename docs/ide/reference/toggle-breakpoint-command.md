---
title: "중단점 설정/해제 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.togglebreakpoint"
helpviewer_keywords: 
  - "Debug.ToggleBreakPoint 명령"
  - "중단점 설정/해제 명령"
  - "ToggleBreakpoint 명령"
ms.assetid: d50dfadb-ce79-4d5e-9c09-1cfddd57876d
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 중단점 설정/해제 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

중단점의 현재 상태에 따라 파일의 현재 위치에서 중단점을 설정하거나 해제합니다.  
  
## 구문  
  
```  
Debug.ToggleBreakpoint [text]  
```  
  
## 인수  
 `text`  
 선택적 요소.  텍스트를 지정하면 줄은 명명된 중단점으로 표시됩니다.  텍스트를 지정하지 않으면 줄은 명명되지 않은 중단점으로 표시되는데 이는 F9 키를 누르면 발생하는 현상과 비슷합니다.  
  
## 예제  
 다음 예제에서는 현재 중단점을 설정하거나 해제합니다.  
  
```  
>Debug.ToggleBreakpoint  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)