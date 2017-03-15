---
title: "컴파일러 오류 CS1637 | Microsoft Docs"
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
  - "CS1637"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1637"
ms.assetid: 95aa82ab-bd52-4def-b5f3-d65e6dcb3855
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1637
반복기에 안전하지 않은 매개 변수 또는 yield 형식을 사용할 수 없습니다.  
  
 반복기의 인수 목록 및 yield 문의 형식을 검사하여 안전하지 않은 형식을 사용하고 있지 않은지 확인합니다.  
  
## 예제  
 다음 샘플에서는 CS1637을 생성합니다.  
  
```  
// CS1637.cs // compile with: /unsafe using System.Collections; public unsafe class C { public IEnumerator Iterator1(int* p)  // CS1637 { yield return null; } }  
```