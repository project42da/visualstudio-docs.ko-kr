---
title: "컴파일러 오류 CS1622 | Microsoft Docs"
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
  - "CS1622"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1622"
ms.assetid: 6b53a777-4cd8-423a-84ff-22ff588044d3
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1622
반복기에서 값을 반환할 수 없습니다. yield return 문을 사용하여 값을 반환하거나 yield break 문을 사용하여 반복을 끝내세요.  
  
 반복기는 return 문 대신 yield 문을 통해 값을 반환하는 특수 함수입니다. 자세한 내용은 **반복기**를 참조하세요.  
  
 다음 샘플에서는 CS1622를 생성합니다.  
  
```  
// CS1622.cs // compile with: /target:library using System.Collections; class C : IEnumerable { public IEnumerator GetEnumerator() { return (IEnumerator) this;  // CS1622 yield return this;   // OK } }  
```