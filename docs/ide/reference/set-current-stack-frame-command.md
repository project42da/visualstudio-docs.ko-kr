---
title: "현재 스택 프레임 설정 명령 | Microsoft Docs"
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
  - "debug.setcurrentstackframe"
helpviewer_keywords: 
  - "Debug.SetCurrentStackFrame 명령"
  - "현재 스택 프레임 설정 명령"
ms.assetid: 3dcf52c0-6781-4598-bac2-0094dce67c20
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 현재 스택 프레임 설정 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

특정 스택 프레임을 설정할 수 있습니다.  
  
## 구문  
  
```  
Debug.SetCurrentStackFrame index  
```  
  
## 인수  
 `index`  
 필수 요소.  인덱스를 사용하여 스택 프레임을 선택합니다.  
  
## 예제  
  
```  
>Debug.SetCurrentStackFrame 1  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)