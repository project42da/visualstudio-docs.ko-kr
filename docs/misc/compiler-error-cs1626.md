---
title: "컴파일러 오류 CS1626 | Microsoft Docs"
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
  - "CS1626"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1626"
ms.assetid: 3ba03383-eb24-4fd8-bf40-8b0f7d6baf0d
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1626
catch 절이 포함된 try 블록의 본문에서는 값을 생성할 수 없습니다.  
  
 yield 문은 try 블록과 연결된 catch 절이 있는 경우 try 블록에 사용할 수 없습니다. 이 오류를 방지하려면 yield 문을 catch 절 밖으로 이동합니다.  
  
 다음 샘플에서는 CS1626을 생성합니다.  
  
```  
// CS1626.cs using System.Collections; class C : IEnumerable { public IEnumerator GetEnumerator() { try { yield return this;  // CS1626 } catch { } } } public class CMain { public static void Main() { } }  
  
```