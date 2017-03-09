---
title: "컴파일러 오류 CS1529 | Microsoft Docs"
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
  - "CS1529"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1529"
ms.assetid: 672a6fd1-3a1f-422c-a29f-46f196d15211
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1529
extern 별칭 선언을 제외하고 using 절은 네임스페이스에 정의된 다른 모든 요소보다 앞에 와야 합니다.  
  
 [using](/dotnet/csharp/language-reference/keywords/using) 절은 네임스페이스에 첫 번째로 표시되어야 합니다.  
  
## 예제  
 다음 샘플에서는 CS1529를 생성합니다.  
  
```  
// CS1529.cs namespace X { namespace Subspace { using Microsoft; class SomeClass { }; using Microsoft;      // CS1529, place before class definition } using System.Reflection;  // CS1529, place before namespace 'Subspace' } using System;                 // CS1529, place at the beginning of the file  
```