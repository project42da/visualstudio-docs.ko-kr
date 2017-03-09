---
title: "컴파일러 오류 CS1022 | Microsoft Docs"
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
  - "CS1022"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1022"
ms.assetid: 76b9f32b-2ebf-471d-a635-852daf8877d7
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1022
형식이나 네임스페이스 정의 또는 파일 끝\(EOF\)이 필요합니다.  
  
 소스 코드 파일에 일치하는 중괄호 집합이 없습니다.  
  
 다음 샘플에서는 CS1022를 생성합니다.  
  
```  
// CS1022.cs namespace x { } }   // CS1022  
```