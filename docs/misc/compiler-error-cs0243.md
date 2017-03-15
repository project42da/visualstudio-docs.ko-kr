---
title: "컴파일러 오류 CS0243 | Microsoft Docs"
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
  - "CS0243"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0243"
ms.assetid: 2506e4cb-dc26-46b4-a58c-ab6bf1601144
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0243
'method'는 재정의 메서드이기 때문에 Conditional 특성을 사용할 수 없습니다.  
  
 [Conditional](http://msdn.microsoft.com/ko-kr/e1c4913b-74d0-421a-8a6d-c14b3f0e68fb) 특성은 [override](/dotnet/csharp/language-reference/keywords/override) 키워드로 표시된 메서드에서 사용할 수 없습니다. 자세한 내용은 [Override 및 New 키워드를 사용해야 하는 경우](/dotnet/csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords)을 참조하세요.  
  
 컴파일러는 재정의 메서드에 바인딩되지 않습니다. 컴파일러는 기본 메서드에만 바인딩되며, 공용 언어 런타임에서 재정의를 적절하게 호출합니다.  
  
 다음 샘플에서는 CS0243을 생성합니다.  
  
```  
// CS0243.cs // compile with: /target:library public class MyClass { public virtual void M() {} } public class MyClass2 : MyClass { [System.Diagnostics.ConditionalAttribute("MySymbol")]   // CS0243 // remove Conditional attribute or remove override keyword public override void M() {} }  
```