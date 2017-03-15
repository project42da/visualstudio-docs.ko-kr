---
title: "컴파일러 오류 CS0406 | Microsoft Docs"
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
  - "CS0406"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0406"
ms.assetid: 9d69681c-e261-4e5e-9361-ea566de12f2e
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0406
클래스 형식 제약 조건 'constraint'는 다른 모든 제약 조건보다 앞에 와야 합니다.  
  
 제네릭 형식 또는 메서드에 클래스 형식 제약 조건이 있는 경우 해당 제약 조건이 먼저 나열되어야 합니다. 이 오류를 방지하려면 클래스 형식 제약 조건을 제약 조건 목록의 시작 부분으로 이동합니다.  
  
## 예제  
 다음 샘플에서는 CS0406을 생성합니다.  
  
```  
// CS0406.cs // compile with: /target:library interface I {} class C {} class D<T> where T : I, C {}   // CS0406 class D2<T> where T : C, I {}   // OK  
```