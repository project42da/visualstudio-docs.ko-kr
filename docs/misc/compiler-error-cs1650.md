---
title: "컴파일러 오류 CS1650 | Microsoft Docs"
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
  - "CS1650"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1650"
ms.assetid: 251a3a67-6e56-4795-874a-d54610c70595
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1650
정적 읽기 전용 필드 'identifier'의 필드에는 할당할 수 없습니다. 단 정적 생성자 또는 변수 이니셜라이저에서는 예외입니다.  
  
 이 오류는 수정을 할 수 없는 읽기 전용 필드 및 정적 필드의 멤버를 수정하려고 시도할 때 발생합니다. 이 오류를 해결하려면 읽기 전용 필드에 대한 할당을 생성자 또는 변수 이니셜라이저로 제한하거나 필드의 선언에서 `readonly` 키워드를 제거합니다.  
  
```  
// CS1650.cs public struct Inner { public int i; } class Outer { public static readonly Inner inner = new Inner(); } class D { static void Main() { Outer.inner.i = 1;  // CS1650 } }  
```