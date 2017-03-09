---
title: "컴파일러 오류 CS0567 | Microsoft Docs"
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
  - "CS0567"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0567"
ms.assetid: 90aefbf9-d216-4eb4-96d4-44926fa23b1e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0567
인터페이스는 연산자를 포함할 수 없습니다.  
  
 연산자가 [interface](/dotnet/csharp/language-reference/keywords/interface) 정의에 허용되지 않습니다.  
  
 다음 샘플에서는 CS0567을 생성합니다.  
  
```  
// CS0567.cs interface IA { int operator +(int aa, int bb);   // CS0567 } class Sample { public static void Main() { } }  
```