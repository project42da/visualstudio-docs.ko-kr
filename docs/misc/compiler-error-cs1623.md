---
title: "컴파일러 오류 CS1623 | Microsoft Docs"
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
  - "CS1623"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1623"
ms.assetid: e52bc2d6-5116-40a2-90bc-23a3fa2c73e7
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1623
반복기에는 ref 또는 out 매개 변수를 사용할 수 없습니다.  
  
 이 오류는 반복기 메서드가 `ref` 또는 `out` 매개 변수를 사용하는 경우 발생합니다. 이 오류를 방지하려면 메서드 서명에서 `ref` 또는 `out` 키워드를 제거합니다.  
  
## 예제  
 다음 샘플에서는 CS1623을 생성합니다.  
  
```  
// CS1623.cs using System.Collections; class C : IEnumerable { public IEnumerator GetEnumerator() { yield return 0; } // To resolve the error, remove ref public IEnumerator GetEnumerator(ref int i)  // CS1623 { yield return i; } // To resolve the error, remove out public IEnumerator GetEnumerator(out float f)  // CS1623 { f = 0.0F; yield return f; } }  
```