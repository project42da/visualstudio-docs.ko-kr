---
title: "컴파일러 오류 CS0199 | Microsoft Docs"
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
  - "CS0199"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0199"
ms.assetid: 9eede3f2-b55a-4b85-a05d-6bf177e1c602
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0199
정적 읽기 전용 필드 'name'의 필드는 ref 또는 out으로 전달할 수 없습니다. 단 정적 생성자에서는 예외입니다.  
  
 [readonly](/dotnet/csharp/language-reference/keywords/readonly) 변수에는 [ref](/dotnet/csharp/language-reference/keywords/ref) 또는 [out](/dotnet/csharp/language-reference/keywords/out) 매개 변수로 전달하려는 생성자와 동일한 [static](/dotnet/csharp/language-reference/keywords/static)을 사용해야 합니다. 자세한 내용은 [매개 변수 전달](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0199를 생성합니다.  
  
```  
// CS0199.cs class MyClass { public static readonly int TestInt = 6; static void TestMethod(ref int testInt) { testInt = 0; } MyClass() { TestMethod(ref TestInt);   // CS0199, TestInt is static } public static void Main() { } }  
```