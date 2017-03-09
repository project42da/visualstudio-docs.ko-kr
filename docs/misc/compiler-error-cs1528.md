---
title: "컴파일러 오류 CS1528 | Microsoft Docs"
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
  - "CS1528"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1528"
ms.assetid: 38aabc5c-b32f-4bea-a585-c4212f42751d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1528
; 또는 \=가 필요합니다. 선언에서는 생성자 인수를 지정할 수 없습니다.  
  
 클래스에 대한 참조가 클래스에 대한 개체가 생성되는 것처럼 형성되었습니다. 예를 들어 생성자에 변수를 전달하려는 시도가 있었습니다. 클래스의 개체를 만들려면 [new](/dotnet/csharp/language-reference/keywords/new) 연산자를 사용합니다.  
  
 다음 샘플에서는 CS1528을 생성합니다.  
  
```  
// CS1528.cs using System; public class B { public B(int i) { _i = i; } public void PrintB() { Console.WriteLine(_i); } private int _i; } public class mine { public static void Main() { B b(3);   // CS1528, reference is not an object // try one of the following // B b; // or // B bb = new B(3); // bb.PrintB(); } }  
```