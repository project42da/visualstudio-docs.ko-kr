---
title: "컴파일러 오류 CS1627 | Microsoft Docs"
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
  - "CS1627"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1627"
ms.assetid: 58dd6e22-e9ed-4e5c-ae04-ce255f07064e
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1627
yield return 다음에는 식이 필요합니다.  
  
 이 오류는 `yield`가 식 없이 사용될 때 발생합니다. 이 오류를 방지하려면 적절한 식을 문에 삽입합니다.  
  
 다음 샘플에서는 CS1627을 생성합니다.  
  
```  
// CS1627.cs using System.Collections; class C : IEnumerable { public IEnumerator GetEnumerator() { yield return;   // CS1627 // To resolve, add the following line: // yield return 0; } } public class CMain { public static void Main() { } }  
```