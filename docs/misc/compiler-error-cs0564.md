---
title: "컴파일러 오류 CS0564 | Microsoft Docs"
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
  - "CS0564"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0564"
ms.assetid: 4c152e10-eb22-4437-a85f-1599c76470e0
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0564
오버로드된 시프트 연산자의 첫 번째 피연산자는 포함하는 형식과 동일한 형식이어야 하며 두 번째 피연산자는 정수 형식이어야 합니다.  
  
 형식이 올바르지 않은 피연산자를 사용하여 시프트 연산자\(\<\< 또는 \>\>\)를 오버로드하려고 했습니다. 첫 번째 피연산자는 형식이어야 하고 두 번째 피연산자는 `int` 형식이어야 합니다.  
  
 다음 샘플에서는 CS0564를 생성합니다.  
  
```  
// CS0564.cs using System; class C { public static int operator << (C c1, C c2) // CS0564 // To correct, change second operand to int, like so: // public static int operator << (C c1, int c2) { return 0; } static void Main() { } }  
```