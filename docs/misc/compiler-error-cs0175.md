---
title: "컴파일러 오류 CS0175 | Microsoft Docs"
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
  - "CS0175"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0175"
ms.assetid: cedd769d-8258-4235-a321-362981b9f84b
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0175
이 컨텍스트에서는 'base' 키워드를 사용할 수 없습니다.  
  
 [base](/dotnet/csharp/language-reference/keywords/base) 키워드를 사용하여 기본 클래스의 특정 멤버를 지정해야 합니다. 자세한 내용은 [생성자](/dotnet/csharp/programming-guide/classes-and-structs/constructors)을 참조하세요.  
  
 다음 샘플에서는 CS0175를 생성합니다.  
  
```  
// CS0175.cs using System; class BaseClass { public int TestInt = 0; } class MyClass : BaseClass { public static void Main() { MyClass aClass = new MyClass(); aClass.BaseTest(); } public void BaseTest() { Console.WriteLine(base); // CS0175 // Try the following line instead: // Console.WriteLine(base.TestInt); base = 9;   // CS0175 // Try the following line instead: // base.TestInt = 9; } }  
```