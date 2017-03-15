---
title: "컴파일러 오류 CS1513 | Microsoft Docs"
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
  - "CS1513"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1513"
ms.assetid: 28dacbb5-bf60-49ac-878e-c0ce469114eb
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1513
}가 필요합니다.  
  
 컴파일러에서 닫는 중괄호\(`}`\)를 찾았지만 없습니다.  
  
 다음 샘플에서는 CS1513을 생성합니다.  
  
```  
// CS1513 namespace y   // CS1513, no close curly brace { class x { public static void Main() { } }  
```