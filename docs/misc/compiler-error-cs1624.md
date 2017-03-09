---
title: "컴파일러 오류 CS1624 | Microsoft Docs"
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
  - "CS1624"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1624"
ms.assetid: af7d049d-27e2-4ce1-973c-5c2cb3e56a63
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1624
'type'이 반복기 인터페이스 형식이 아니므로 'accessor'의 본문은 반복기 블록이 될 수 없습니다.  
  
 이 오류는 반복기 접근자가 사용되었지만 반환 형식이 반복기 인터페이스 형식인 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, <xref:System.Collections.Generic.IEnumerator%601> 중 하나가 아닌 경우 발생합니다. 이 오류를 방지하려면 반복기 인터페이스 형식 중 하나를 반환 형식으로 사용합니다.  
  
## 예제  
 다음 샘플에서는 CS1624를 생성합니다.  
  
```  
// CS1624.cs using System; using System.Collections; class C { public int Iterator // Try this instead: // public IEnumerable Iterator { get  // CS1624 { yield return 1; } } }  
```