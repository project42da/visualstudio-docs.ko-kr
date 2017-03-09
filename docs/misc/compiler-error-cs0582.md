---
title: "컴파일러 오류 CS0582 | Microsoft Docs"
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
  - "CS0582"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0582"
ms.assetid: cc0f4c75-c41d-423e-a4dc-e55a124f5cae
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0582
인터페이스 멤버에서는 Conditional을 사용할 수 없습니다.  
  
 인터페이스 멤버에서는 **ConditionalAttribute**를 사용할 수 없습니다.  
  
 다음 샘플에서는 CS0582를 생성합니다.  
  
```  
// CS0582.cs // compile with: /target:library using System.Diagnostics; interface MyIFace { [ConditionalAttribute("DEBUG")]   // CS0582 void zz(); }  
```