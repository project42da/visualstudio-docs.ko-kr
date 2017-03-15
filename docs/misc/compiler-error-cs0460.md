---
title: "컴파일러 오류 CS0460 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0460"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0460"
ms.assetid: 98d39ded-d3f9-4520-b912-892e574c056b
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0460
재정의 및 명시적 인터페이스 구현 메서드에 대한 제약 조건은 기본 메서드에서 상속되므로 직접 지정할 수 없습니다.  
  
 파생 클래스의 일부인 제네릭 메서드가 기본 클래스의 메서드를 재정의하는 경우 재정의된 메서드에 제약 조건을 지정할 수 없습니다. 파생 클래스의 재정의 메서드는 기본 클래스의 메서드에서 해당 제약 조건을 상속합니다.  
  
## 예제  
 다음 샘플에서는 CS0460을 생성합니다.  
  
```  
// CS0460.cs // compile with: /target:library class BaseClass { BaseClass() { } } interface I { void F1<T>() where T : BaseClass; void F2<T>() where T : struct; void F3<T>() where T : BaseClass; } class ExpImpl : I { void I.F1<T>() where T : BaseClass {}   // CS0460 void I.F2<T>() where T : class {}  // CS0460 }  
```