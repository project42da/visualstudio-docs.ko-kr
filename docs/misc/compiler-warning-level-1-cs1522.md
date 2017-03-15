---
title: "컴파일러 경고(수준 1) CS1522 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1522"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1522"
ms.assetid: afb99bbf-a1d9-441e-b392-6845bea23f27
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1522
빈 스위치 블록입니다.  
  
 컴파일러가 **case** 또는 **default** 문 없이 [switch](/dotnet/csharp/language-reference/keywords/switch) 블록을 검색했습니다.`switch` 블록에는 하나 이상의 **case** 또는 **default** 문이 있어야 합니다.  
  
 다음 샘플에서는 CS1522를 생성합니다.  
  
```  
// CS1522.cs // compile with: /W:1 using System; class x { public static void Main() { int i = 6; switch(i)   // CS1522 { // add something to the switch block, for example: /* case (5): Console.WriteLine("5"); return; default: Console.WriteLine("not 5"); return; */ } } }  
```