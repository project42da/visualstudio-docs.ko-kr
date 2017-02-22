---
title: "현재 프로세스 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Debug.SetCurrentProcess 명령"
  - "현재 프로세스 설정 명령"
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 현재 프로세스 설정
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정된 프로세스를 디버거에서 활성 프로세스로 설정합니다.  
  
## 구문  
  
```  
Debug.SetCurrentProcess index  
```  
  
## 인수  
 `index`  
 필수 요소.  프로세스의 인덱스입니다.  
  
## 설명  
 디버깅하는 동안 여러 프로세스에 연결할 수 있지만 한 번에 프로세스 하나만 디버거에서 활성화됩니다.  `SetCurrentProcess` 명령을 사용하여 활성 프로세스를 설정할 수 있습니다.  
  
## 예제  
  
```  
>Debug.SetCurrentProcess 1  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)