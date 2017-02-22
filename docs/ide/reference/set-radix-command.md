---
title: "기수 설정 명령 | Microsoft Docs"
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
  - "debug.setradix"
helpviewer_keywords: 
  - "Debug.SetRadix 명령"
  - "기수 설정 명령"
ms.assetid: 6ffd1554-7530-4da4-b5f5-e276a5034f3b
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 기수 설정 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

정수 값을 표시하는 데 사용되는 숫자 밑수를 설정하거나 반환합니다.  
  
## 구문  
  
```  
Debug.SetRadix [10 | 16 | hex | dec]  
```  
  
## 인수  
 `10`이나 `16` 또는 `hex`나 `dec`  
 선택적 요소.  10진수\(10 또는 dec\) 또는 16진수\(16 또는 hex\)를 나타냅니다.  인수를 생략하면 현재 기수 값이 반환됩니다.  
  
## 예제  
 이 예제는 정수 값을 16진수 형식으로 표시하는 환경을 설정합니다.  
  
```  
>Debug.SetRadix hex  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)