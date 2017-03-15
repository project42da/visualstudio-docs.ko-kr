---
title: "컴파일러 오류 CS0678 | Microsoft Docs"
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
  - "CS0678"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0678"
ms.assetid: ca389fc9-da78-4e16-b68c-782f90b17c83
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0678
'variable': 필드는 volatile이면서 readonly일 수 없습니다.  
  
 [volatile](/dotnet/csharp/language-reference/keywords/volatile) 및 [readonly](/dotnet/csharp/language-reference/keywords/readonly) 키워드는 함께 사용할 수 없습니다.  
  
 다음 샘플에서는 CS0678을 생성합니다.  
  
```  
// CS0678.cs using System; class TestClass { private readonly volatile int i;   // CS0678 // try the following line instead // private volatile int i; public static void Main() { } }  
```