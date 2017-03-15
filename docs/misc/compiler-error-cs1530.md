---
title: "컴파일러 오류 CS1530 | Microsoft Docs"
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
  - "CS1530"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1530"
ms.assetid: 3844b5ef-e0ec-42df-9267-72689020f128
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1530
네임스페이스에 정의된 요소에는 'new' 키워드를 사용할 수 없습니다.  
  
 [네임스페이스](/dotnet/csharp/language-reference/keywords/namespace)에 있는 생성자에 [new](/dotnet/csharp/language-reference/keywords/new) 키워드를 지정할 필요가 없습니다.  
  
 다음 샘플에서는 CS1530을 생성합니다.  
  
```  
// CS1530.cs namespace a { new class i   // CS1530 { } // try the following instead class ii { public static void Main() { } } }  
```