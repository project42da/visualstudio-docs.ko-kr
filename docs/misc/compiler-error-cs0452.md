---
title: "컴파일러 오류 CS0452 | Microsoft Docs"
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
  - "CS0452"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0452"
ms.assetid: 50a87734-fe07-4bce-891d-a76e131db6cc
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0452
제네릭 형식 또는 메서드 'identifier of generic'에서 'type name' 형식을 'parameter name' 매개 변수로 사용하려면 해당 형식이 참조 형식이어야 합니다.  
  
 이 오류는 `struct` 또는 `int` 등의 값 형식을 참조 형식 제약 조건이 있는 제네릭 형식 또는 메서드에 매개 변수로 전달할 때 발생합니다.  
  
## 예제  
 다음 코드에서는 CS0452 오류를 생성합니다.  
  
```  
// CS0452.cs using System; public class BaseClass<S> where S : class { } public class Derived1 : BaseClass<int> { } // CS0452 public class Derived2<S> : BaseClass<S> where S : struct { } // CS0452  
```  
  
## 참고 항목  
 [형식 매개 변수에 대한 제약 조건](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)