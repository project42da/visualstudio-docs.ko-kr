---
title: "컴파일러 오류 CS0255 | Microsoft Docs"
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
  - "CS0255"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0255"
ms.assetid: b45f5d5a-1923-4fe1-a858-e5ef5590a108
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0255
stackalloc는 catch 또는 finally 블록에 사용할 수 없습니다.  
  
 [stackalloc](/dotnet/csharp/language-reference/keywords/stackalloc) 키워드는 [catch](/dotnet/csharp/language-reference/keywords/try-catch) 또는 [finally](/dotnet/csharp/language-reference/keywords/try-catch-finally) 블록에 사용할 수 없습니다. 자세한 내용은 [예외 및 예외 처리](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling)을 참조하세요.  
  
 다음 샘플에서는 CS0255를 생성합니다.  
  
```  
// CS0255.cs // compile with: /unsafe using System; public class TestTryFinally { public static unsafe void Test() { int i = 123; string s = "Some string"; object o = s; try { // Conversion is not valid; o contains a string not an int i = (int) o; } finally { Console.Write("i = {0}", i); int* fib = stackalloc int[100];   // CS0255 } } public static void Main() { } }  
```