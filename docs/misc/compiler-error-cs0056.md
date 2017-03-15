---
title: "컴파일러 오류 CS0056 | Microsoft Docs"
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
  - "CS0056"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0056"
ms.assetid: 8878b09c-5b7b-40e0-be0d-61ef5b36c151
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0056
일관성 없는 접근성: 'type' 반환 형식이 'operator' 연산자보다 액세스하기 어렵습니다.  
  
 공용 구문은 공개적으로 액세스 가능한 개체를 반환해야 합니다. 자세한 내용은 [액세스 한정자](/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)을 참조하세요.  
  
 다음 샘플에서는 CS0056을 생성합니다.  
  
```  
// CS0056.cs class MyClass // try the following line instead // public class MyClass { } public class A { public static implicit operator MyClass(A a)   // CS0056 { return new MyClass(); } public static void Main() { } }  
```