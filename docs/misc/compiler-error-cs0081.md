---
title: "컴파일러 오류 CS0081 | Microsoft Docs"
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
  - "CS0081"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0081"
ms.assetid: a5649abc-89ea-4f64-8c3c-eb36df926561
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0081
형식 매개 변수 선언은 형식이 아니라 식별자여야 합니다.  
  
 제네릭 메서드 또는 형식을 선언할 때 형식 매개 변수를 "T" 또는 "inputType"과 같은 식별자로 지정합니다. 클라이언트 코드가 메서드를 호출하면 이 메서드가 형식을 제공하며 메서드 또는 클래스 본문에서 각 식별자 발생을 대체합니다. 자세한 내용은 [제네릭 형식 매개 변수](/dotnet/csharp/programming-guide/generics/generic-type-parameters)을 참조하세요.  
  
```  
// CS0081.cs class MyClass { public void F<int>() {}   // CS0081 public void F<T>(T input) {}   // OK public static void Main() { MyClass a = new MyClass(); a.F<int>(2); a.F<double>(.05); } }  
```  
  
## 참고 항목  
 [제네릭](/dotnet/csharp/programming-guide/generics/index)