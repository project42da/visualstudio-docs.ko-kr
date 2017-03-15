---
title: "컴파일러 오류 CS0157 | Microsoft Docs"
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
  - "CS0157"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0157"
ms.assetid: a5d9d506-81f8-47dd-85b6-85f8170bcbef
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0157
제어가 finally 절의 본문을 벗어날 수 없습니다.  
  
 [finally](/dotnet/csharp/language-reference/keywords/try-catch-finally) 절의 모든 문을 실행해야 합니다. 자세한 내용은 [예외 처리문](/dotnet/csharp/language-reference/keywords/exception-handling-statements) 및 [예외 및 예외 처리](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling)를 참조하세요.  
  
 다음 샘플에서는 CS0157을 생성합니다.  
  
```  
// CS0157.cs using System; namespace MyNamespace { public class MyClass2 : Exception { } public class MyClass { public static void Main() { try { } finally { return;   // CS0157, cannot leave finally clause } } } }  
```