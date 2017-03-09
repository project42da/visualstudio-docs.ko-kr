---
title: "컴파일러 오류 CS0035 | Microsoft Docs"
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
  - "CS0035"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0035"
ms.assetid: a622113e-98a4-4583-992c-1fb55139320a
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0035
'operator' 연산자가 모호하여 'type' 형식의 피연산자에 사용할 수 없습니다.  
  
 컴파일러에 사용 가능한 변환이 두 개 이상이고 연산자를 적용하기 전에는 어떤 변환이 선택되는지 알 수 없습니다. 자세한 내용은 [템플릿 기반 사용자 정의 변환](../misc/templated-user-defined-conversions.md) 및 [변환 연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/conversion-operators)를 참조하세요.  
  
 다음 샘플에서는 CS0035를 생성합니다.  
  
```  
// CS0035.cs class MyClass { private int i; public MyClass(int i) { this.i = i; } public static implicit operator double(MyClass x) { return (double) x.i; } public static implicit operator decimal(MyClass x) { return (decimal) x.i; } } class MyClass2 { static void Main() { MyClass x = new MyClass(7); object o = - x;   // CS0035 // try a cast: // object o = - (double)x; } }  
  
```