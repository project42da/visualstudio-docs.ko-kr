---
title: "현재 스레드 설정 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.setcurrentthread"
helpviewer_keywords: 
  - "Debug.SetCurrentThread 명령"
  - "현재 스레드 설정 명령"
ms.assetid: 9917ed1d-6c30-4d94-b2f0-69acce74f1b2
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 현재 스레드 설정 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 스레드를 현재 스레드로 설정합니다.  
  
## 구문  
  
```  
Debug.SetCurrentThread index  
```  
  
## 인수  
 `index`  
 필수 요소.  인덱스를 사용하여 스레드를 선택합니다.  
  
## 예제  
  
```  
>Debug.SetCurrentThread 1  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)