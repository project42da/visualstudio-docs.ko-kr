---
title: "컴파일러 오류 CS2017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS2017"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2017"
ms.assetid: 16fd0c3b-018f-4734-809d-8d98d05a254c
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS2017
모듈이나 라이브러리를 빌드하고 있으면 \/main을 지정할 수 없습니다.  
  
 [\/target: library](../Topic/-target:library%20\(C%23%20Compiler%20Options\).md)를 작성할 때 주 진입점을 지정할 수 없습니다.  
  
 다음 샘플에서는 CS2017을 생성합니다.  
  
```  
// CS2017.cs // compile with: /main:MyClass /target:library // CS2017 expected class MyClass { public static void Main() { } }  
```