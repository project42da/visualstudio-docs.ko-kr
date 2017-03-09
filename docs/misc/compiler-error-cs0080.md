---
title: "컴파일러 오류 CS0080 | Microsoft Docs"
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
  - "CS0080"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0080"
ms.assetid: 99035371-37d1-48b2-a8b9-e8a1ebd04f0f
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0080
제네릭이 아닌 선언에는 제약 조건을 사용할 수 없습니다.  
  
 발견된 구문은 형식 매개 변수에 제약 조건을 적용하기 위해 제네릭 선언에만 사용할 수 있습니다. 자세한 내용은 [제네릭](/dotnet/csharp/programming-guide/generics/index)을 참조하세요.  
  
 다음 샘플에서는 MyClass가 제네릭 클래스가 아니고 Foo가 제네릭 메서드가 아니기 때문에 CS0080를 생성합니다.  
  
```  
namespace MyNamespace { public class MyClass where MyClass : System.IDisposable // CS0080    //the following line shows an example of correct syntax //public class MyClass<T> where T : System.IDisposable { public void Foo() where Foo : new() // CS0080 //the following line shows an example of correct syntax //public void Foo<U>() where U : struct { } } public class Program { public static void Main() { } } }  
```