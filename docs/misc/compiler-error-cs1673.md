---
title: "컴파일러 오류 CS1673 | Microsoft Docs"
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
  - "CS1673"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1673"
ms.assetid: 5c7dd58b-dcbc-45c9-be36-7d15fafaa067
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1673
구조체 안의 무명 메서드, 람다 식 및 쿼리식은 'this'의 인스턴스 멤버에 액세스할 수 없습니다. 'this'를 무명 메서드, 람다 식 또는 쿼리 식 외부에 있는 지역 변수에 복사한 다음 이 지역 변수를 대신 사용하세요.  
  
 다음 샘플에서는 CS1673을 생성합니다.  
  
```  
// CS1673.cs delegate int MyDelegate(); public struct S { int member; public int F(int i) { member = i; // Try assigning to a local variable // S s = this; MyDelegate d = delegate() { i = this.member;  // CS1673 // And use the local variable instead of "this" // i =  s.member; return i; }; return d(); } } class CMain { public static void Main() { } }  
```