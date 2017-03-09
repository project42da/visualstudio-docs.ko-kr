---
title: "컴파일러 오류 CS1625 | Microsoft Docs"
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
  - "CS1625"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1625"
ms.assetid: 0b25b7f9-a585-49b0-9ee6-4384e87fcea6
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1625
finally 절의 본문에서는 yield를 사용할 수 없습니다.  
  
 yield 문은 finally 절의 본문에 사용할 수 없습니다. 이 오류를 방지하려면 yield 문을 finally 절 밖으로 이동합니다.  
  
 다음 샘플에서는 CS1625를 생성합니다.  
  
```  
// CS1625.cs using System.Collections; class C : IEnumerable { public IEnumerator GetEnumerator() { try { } finally { yield return this;  // CS1625 } } } public class CMain { public static void Main() { } }  
  
```