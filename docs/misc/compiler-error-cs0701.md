---
title: "컴파일러 오류 CS0701 | Microsoft Docs"
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
  - "CS0701"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0701"
ms.assetid: eb844e31-00bd-468d-9f77-11d10a4ef120
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0701
'identifier'가 올바른 제약 조건이 아닙니다. 제약 조건으로 사용되는 형식은 인터페이스, 봉인되지 않은 클래스 또는 형식 매개 변수여야 합니다.  
  
 이 오류는 봉인된 형식을 제약 조건으로 사용하는 경우에 발생합니다. 이 오류를 해결하려면 봉인되지 않은 형식만 제약 조건으로 사용합니다.  
  
## 예제  
 다음 샘플에서는 CS0701을 생성합니다.  
  
```  
// CS0701.cs // compile with: /target:library class C<T> where T : System.String {}   // CS0701 class D<T> where T : System.Attribute {}   // OK  
```