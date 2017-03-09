---
title: "컴파일러 오류 CS1671 | Microsoft Docs"
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
  - "CS1671"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1671"
ms.assetid: 34255d2b-6ff6-4ac1-b617-3199e16726cf
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1671
네임스페이스 선언에는 한정자 또는 특성을 사용할 수 없습니다.  
  
 한정자는 네임스페이스에 적용할 때 의미가 없으므로 사용할 수 없습니다.  
  
 다음 샘플에서는 CS1671을 생성합니다.  
  
```  
// CS1671.cs public namespace NS // CS1671 { }  
```