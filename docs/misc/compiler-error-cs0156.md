---
title: "컴파일러 오류 CS0156 | Microsoft Docs"
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
  - "CS0156"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0156"
ms.assetid: 32026b1b-bcd7-4464-b63f-3b38c00452a6
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0156
바로 바깥쪽 catch 절에 중첩된 finally 절에는 인수가 없는 throw 문을 사용할 수 없습니다.  
  
 매개 변수가 없는 [throw](/dotnet/csharp/language-reference/keywords/throw) 문은 매개 변수를 사용하지 않는 **catch** 절에서만 나타날 수 있습니다.  
  
 자세한 내용은 [예외 처리문](/dotnet/csharp/language-reference/keywords/exception-handling-statements) 및 [예외 및 예외 처리](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling)를 참조하세요.  
  
 다음 샘플에서는 CS0156을 생성합니다.  
  
```  
// CS0156.cs using System; namespace MyNamespace { public class MyClass2 : Exception { } public class MyClass { public static void Main() { try { throw;   // CS0156 } catch(MyClass2) { throw;   // this throw is valid } } } }  
```