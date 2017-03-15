---
title: "컴파일러 오류 CS0198 | Microsoft Docs"
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
  - "CS0198"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0198"
ms.assetid: 222c20f6-3f7f-4750-9f99-b5e6ae6c1271
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0198
정적 읽기 전용 필드 'name'의 필드에는 할당할 수 없습니다. 단 정적 생성자 또는 변수 이니셜라이저에서는 예외입니다.  
  
 [readonly](/dotnet/csharp/language-reference/keywords/readonly) 변수에는 초기화하려는 생성자와 동일한 [static](/dotnet/csharp/language-reference/keywords/static)을 사용해야 합니다. 자세한 내용은 [정적 생성자](/dotnet/csharp/programming-guide/classes-and-structs/static-constructors)을 참조하세요.  
  
 다음 샘플에서는 CS0198을 생성합니다.  
  
```  
// CS0198.cs class MyClass { public static readonly int TestInt = 6; MyClass() { TestInt = 11;   // CS0198, constructor is not static and readonly field is } public static void Main() { } }  
```