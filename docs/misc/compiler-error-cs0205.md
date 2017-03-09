---
title: "컴파일러 오류 CS0205 | Microsoft Docs"
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
  - "CS0205"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0205"
ms.assetid: 616d98cf-e7a5-4f8e-93da-fcd6e1e4de35
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0205
추상 기본 멤버를 호출할 수 없습니다. 'method'  
  
 메서드 본문이 없기 때문에 [abstract](/dotnet/csharp/language-reference/keywords/abstract) 메서드를 호출할 수 없습니다. 자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](/dotnet/csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members)을 참조하세요.  
  
 다음 샘플에서는 CS0205를 생성합니다.  
  
```  
// CS0205.cs abstract public class MyClass { abstract public void M(); } public class MyClass2 : MyClass { public override void M() { base.M();   // CS0205, delete this line } public static void Main() { } }  
```