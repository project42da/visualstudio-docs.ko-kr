---
title: "컴파일러 오류 CS0192 | Microsoft Docs"
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
  - "CS0192"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0192"
ms.assetid: d3fb6d18-dbf3-42c3-a280-afe55b97c2d1
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0192
정적 읽기 전용 필드 'name'의 필드는 ref 또는 out으로 전달할 수 없습니다. 단 정적 생성자에서는 예외입니다.  
  
 [readonly](/dotnet/csharp/language-reference/keywords/readonly) 키워드로 표시된 필드\(변수\)를 생성자 내부를 제외하고 [ref](/dotnet/csharp/language-reference/keywords/ref) 또는 [out](/dotnet/csharp/language-reference/keywords/out) 매개 변수로 전달할 수 없습니다. 자세한 내용은 [필드](/dotnet/csharp/programming-guide/classes-and-structs/fields)을 참조하세요.  
  
 CS0192는 `readonly` 필드가 [static](/dotnet/csharp/language-reference/keywords/static)인데 생성자가 `static`으로 표시되지 않은 경우에도 발생합니다.  
  
## 예제  
 다음 샘플에서는 CS0192를 생성합니다.  
  
```  
// CS0192.cs class MyClass { public readonly int TestInt = 6; static void TestMethod(ref int testInt) { testInt = 0; } MyClass() { TestMethod(ref TestInt);   // OK } public void PassReadOnlyRef() { TestMethod(ref TestInt);   // CS0192 } public static void Main() { } }  
```