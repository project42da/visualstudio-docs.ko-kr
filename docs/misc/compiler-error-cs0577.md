---
title: "컴파일러 오류 CS0577 | Microsoft Docs"
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
  - "CS0577"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0577"
ms.assetid: 34f8f453-f016-4f2c-981a-0d61449cd74b
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0577
생성자, 소멸자, 연산자 또는 명시적 인터페이스 구현이므로 'function'에서 Conditional 특성을 사용할 수 없습니다.  
  
 지정된 메서드에 `Conditional`을 적용할 수 없습니다.  
  
 예를 들어 명시적 인터페이스 정의에 일부 특성을 사용할 수 없습니다. 다음 샘플에서는 CS0577을 생성합니다.  
  
```  
// CS0577.cs // compile with: /target:library interface I { void m(); } public class MyClass : I { [System.Diagnostics.Conditional("a")]   // CS0577 void I.m() {} }  
```