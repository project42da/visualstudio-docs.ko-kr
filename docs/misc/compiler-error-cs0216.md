---
title: "컴파일러 오류 CS0216 | Microsoft Docs"
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
  - "CS0216"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0216"
ms.assetid: afb3dd29-3eff-4b62-8267-eb726c2bcee4
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0216
'operator' 연산자를 사용하려면 짝이 되는 'missing\_operator' 연산자도 정의해야 합니다.  
  
 사용자 정의 [true](/dotnet/csharp/language-reference/keywords/true) 연산자를 사용하려면 사용자 정의 [false](/dotnet/csharp/language-reference/keywords/false) 연산자가 필요하며 그 반대도 마찬가지입니다. 자세한 내용은 [연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/operators)을 참조하세요.  
  
 다음 샘플에서는 CS0216을 생성합니다.  
  
```  
// CS0216.cs class MyClass { public static bool operator true (MyClass MyInt)   // CS0216 { return true; } // to resolve, uncomment the following operator definition /* public static bool operator false (MyClass MyInt) { return true; } */ public static void Main() { } }  
```