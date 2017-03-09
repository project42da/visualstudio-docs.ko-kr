---
title: "컴파일러 오류 CS1722 | Microsoft Docs"
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
  - "CS1722"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1722"
ms.assetid: cf698a80-e4c9-46e2-96a0-8b8b5a08fc37
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1722
기본 클래스 'class'는 다른 모든 인터페이스보다 앞에 와야 합니다.  
  
 상속할 클래스 및 구현할 인터페이스를 지정하는 경우 클래스 이름을 먼저 지정해야 합니다.  
  
## 예제  
 다음 샘플에서는 CS1722를 생성합니다.  
  
```  
// CS1722.cs // compile with: /target:library public class A {} interface I {} public class MyClass : I, A {}   // CS1722 public class MyClass2 : A, I {}   // OK  
```