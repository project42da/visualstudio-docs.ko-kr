---
title: "컴파일러 오류 CS0155 | Microsoft Docs"
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
  - "CS0155"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0155"
ms.assetid: 6c92984a-2b10-453e-9cb7-e6a1d1b98aa6
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0155
Catch 또는 Throw된 형식은 System.Exception에서 파생되어야 합니다.  
  
 **System.Exception**에서 파생되지 않는 데이터 형식을 [catch](/dotnet/csharp/language-reference/keywords/try-catch) 블록에 전달하려고 했습니다.**System.Exception**에서 파생된 데이터 형식만 **catch** 블록에 전달할 수 있습니다. 자세한 내용은 [예외 처리문](/dotnet/csharp/language-reference/keywords/exception-handling-statements) 및 [예외 및 예외 처리](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling)를 참조하세요.  
  
 다음 샘플에서는 CS0155를 생성합니다.  
  
```  
// CS0155.cs using System; namespace MyNamespace { public class MyClass2 // try the following line instead // public class MyClass2 : Exception { } public class MyClass { public static void Main() { try { } catch (MyClass2)   // CS0155, resolves if you derive MyClass2 from Exception { } } } }  
```