---
title: "컴파일러 오류 CS0210 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0210"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0210"
ms.assetid: 9f2ec1b8-6ca4-4147-b004-e3b43e7e8754
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0210
fixed 또는 using 문 선언에 이니셜라이저를 입력해야 합니다.  
  
 [fixed 문](/dotnet/csharp/language-reference/keywords/fixed-statement)에서 변수를 선언하고 초기화해야 합니다. 자세한 내용은 [안전하지 않은 코드 및 포인터](/dotnet/csharp/programming-guide/unsafe-code-pointers/index)을 참조하세요.  
  
 다음 샘플에서는 CS0210을 생성합니다.  
  
```  
// CS0210a.cs // compile with: /unsafe class Point { public int x, y; } public class MyClass { unsafe public static void Main() { Point pt = new Point(); fixed (int i)    // CS0210 { } // try the following lines instead /* fixed (int* p = &pt.x) { } fixed (int* q = &pt.y) { } */ } }  
```  
  
 또한 다음 샘플에서는 [using 문](/dotnet/csharp/language-reference/keywords/using-statement)에 이니셜라이저가 없기 때문에 CS0210을 생성합니다.  
  
```  
// CS0210b.cs using System.IO; class Test { static void Main() { using (StreamWriter w) // CS0210 // Try this line instead: // using (StreamWriter w = new StreamWriter("TestFile.txt")) { w.WriteLine("Hello there"); } } }  
```