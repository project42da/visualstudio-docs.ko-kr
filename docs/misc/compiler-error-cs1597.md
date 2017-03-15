---
title: "컴파일러 오류 CS1597 | Microsoft Docs"
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
  - "CS1597"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1597"
ms.assetid: 735e7cde-38de-4e15-96cc-ce75ffe34ff2
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1597
메서드 또는 접근자 블록 뒤의 세미콜론이 잘못되었습니다.  
  
 메서드 또는 접근자 블록을 끝내기 위해 세미콜론이 필요하지\(또는 허용되지\) 않습니다.  
  
 다음 샘플에서는 CS1597을 생성합니다.  
  
```  
// CS1597.cs class TestClass { public static void Main() { };   // CS1597, remove semicolon }  
```