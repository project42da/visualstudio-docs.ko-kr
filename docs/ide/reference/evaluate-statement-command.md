---
title: "문 실행 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.evaluatestatement"
helpviewer_keywords: 
  - "Debug.EvaluateStatement 명령"
  - "문 실행 명령"
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# 문 실행 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정된 문을 실행하고 표시합니다.  
  
## 구문  
  
```  
Debug.EvaluateStatement text   
```  
  
## 인수  
 `text`  
 필수 요소.  실행할 문입니다.  
  
## 설명  
 **EvaluateStatement** 명령을 입력하는 데 사용되는 창은 등호\(\=\)가 비교 연산자로 해석되는지 아니면 할당 연산자로 해석되는지 결정합니다.  
  
 **명령** 창에서는 등호\(\=\)가 비교 연산자로 해석되므로  예를 들어, `a` 및 `b` 변수의 값이 다를 경우  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 위의 명령은 `false` 값을 반환합니다.  
  
 반대로 **직접 실행** 창에서는 등호\(\=\)가 할당 연산자로 해석되므로  예를 들어,  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 위의 명령은 `a` 변수에 `b` 변수의 값을 할당합니다.  
  
## 예제  
  
```  
>Debug.EvaluateStatement(a+b)  
```  
  
## 참고 항목  
 [인쇄 명령](../../ide/reference/print-command.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)