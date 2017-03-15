---
title: "컴파일러 오류 CS0191 | Microsoft Docs"
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
  - "CS0191"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0191"
ms.assetid: 512479e4-656e-4dcb-8d71-801541d72dcd
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0191
'name' 속성 또는 인덱서는 읽기 전용이므로 할당할 수 없습니다.  
  
 [readonly](/dotnet/csharp/language-reference/keywords/readonly) 필드는 생성자에서 또는 선언 시에만 할당을 사용할 수 있습니다. 자세한 내용은 [생성자](/dotnet/csharp/programming-guide/classes-and-structs/constructors)을 참조하세요.  
  
 CS0191은 `readonly` 필드가 [static](/dotnet/csharp/language-reference/keywords/static)인데 생성자가 `static`으로 표시되지 않은 경우에도 발생합니다.  
  
## 예제  
 다음 샘플에서는 CS0191을 생성합니다.  
  
```  
// CS0191.cs class MyClass { public readonly int TestInt = 6;  // OK to assign to readonly field in declaration MyClass() { TestInt = 11; // OK to assign to readonly field in constructor } public void TestReadOnly() { TestInt = 19;                  // CS0191 } public static void Main() { } }  
```