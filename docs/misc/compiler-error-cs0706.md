---
title: "컴파일러 오류 CS0706 | Microsoft Docs"
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
  - "CS0706"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0706"
ms.assetid: bc3ac5c0-8c96-43c8-b10a-69bd31b38e4a
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0706
잘못된 제약 조건 형식입니다. 제약 조건으로 사용되는 형식은 인터페이스, 봉인되지 않은 클래스 또는 형식 매개 변수여야 합니다.  
  
 이 오류는 제약 조건 절에 잘못된 구문이 사용된 경우 발생합니다. 이 오류를 방지하려면 오류를 발생시킨 구문 대신 인터페이스 또는 봉인되지 않은 클래스를 사용합니다.  
  
## 예제  
 다음 샘플에서는 CS0706을 생성합니다.  
  
```  
// CS0706.cs // compile with: /target:library class A {} class C<T> where T : int[] {}  // CS0706 class D<T> where T : A {}  // OK  
```