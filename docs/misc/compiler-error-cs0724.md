---
title: "컴파일러 오류 CS0724 | Microsoft Docs"
ms.custom: ""
ms.date: "10/01/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0724"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0724"
ms.assetid: bcdb2017-7a43-4242-b4e2-a1ae03d6d73f
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0724
어셈블리에 CLSCompliant 특성이 없으므로 CLSCompliant 특성이 필요하지 않습니다.  
  
 다음 예제에서는 `finally` 절 블록 내의 `throw` 문 때문에 CS0724를 생성합니다.  
  
## 예제  
 다음 예제에서는 CS0724를 생성합니다.  
  
```  
// CS0724.cs using System; class X { static void Test() { try { throw new Exception(); } catch { try { } finally { throw; // CS0724 } } } static void Main() { } }  
```