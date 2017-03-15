---
title: "컴파일러 오류 CS1629 | Microsoft Docs"
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
  - "CS1629"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1629"
ms.assetid: 907eae46-0265-4cd0-b27b-ff555d004259
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1629
반복기에는 안전하지 않은 코드를 사용할 수 없습니다.  
  
 C\# 언어 사양은 반복기에서 안전하지 않은 코드를 허용하지 않습니다.  
  
 다음 샘플에서는 CS1629를 생성합니다.  
  
```  
// CS1629.cs // compile with: /unsafe using System.Collections.Generic; class C { IEnumerator<int> IteratorMeth() { int i; unsafe  // CS1629 { int *p = &i; yield return *p; } } }  
```