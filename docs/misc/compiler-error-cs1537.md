---
title: "컴파일러 오류 CS1537 | Microsoft Docs"
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
  - "CS1537"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1537"
ms.assetid: fdc17f3e-05b3-4d04-8825-4563aec816f5
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1537
using 별칭 'alias'를 이전에 이 네임스페이스에서 사용했습니다.  
  
 네임스페이스에 대한 별칭으로 기호를 두 번 정의했습니다. 기호는 한 번만 정의할 수 있습니다.  
  
 다음 샘플에서는 CS1537을 생성합니다.  
  
```  
// CS1537.cs namespace x { using System; using Object = System.Object; using Object = System.Object;   // CS1537, delete this line to resolve using System = System; }  
```