---
title: "컴파일러 오류 CS0069 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0069"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0069"
ms.assetid: a1b32906-7773-47c6-8515-162a201a9be5
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0069
인터페이스의 이벤트에는 add 또는 remove 접근자를 사용할 수 없습니다.  
  
 [인터페이스](/dotnet/csharp/language-reference/keywords/interface)에서 이벤트의 접근자 함수를 정의할 수 없습니다. 자세한 내용은 [이벤트](/dotnet/csharp/programming-guide/events/index) 및 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)를 참조하세요.  
  
 다음 샘플에서는 CS0069를 생성합니다.  
  
```  
// CS0069.cs // compile with: /target:library public delegate void EventHandler(); public interface a { event EventHandler Click { remove {} }   // CS0069 event EventHandler Click2;   // OK }  
```