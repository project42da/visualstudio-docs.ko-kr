---
title: "컴파일러 오류 CS0466 | Microsoft Docs"
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
  - "CS0466"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0466"
ms.assetid: db6be72b-120a-4b48-b41c-a738d02adae0
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0466
'method1'이 없어 'method2'에 params 매개 변수를 사용할 수 없습니다.  
  
 구현된 인터페이스가 `params` 매개 변수를 사용할 수 없는 경우 클래스 맴버에서 해당 매개 변수를 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS0466을 생성합니다.  
  
```  
// CS0466.cs interface I { void F1(params int[] a); void F2(int[] a); } class C : I { void I.F1(params int[] a) {} void I.F2(params int[] a) {}   // CS0466 void I.F2(int[] a) {}   // OK public static void Main() { I i = (I) new C(); i.F1(new int[] {1, 2} ); i.F2(new int[] {1, 2} ); } }  
```