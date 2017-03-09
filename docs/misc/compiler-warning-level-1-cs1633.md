---
title: "컴파일러 경고(수준 1) CS1633 | Microsoft Docs"
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
  - "CS1633"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1633"
ms.assetid: f31db218-f880-4fc4-ab34-8bcdc49011da
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1633
인식할 수 없는 \#pragma 지시문입니다.  
  
 사용된 pragma가 C\# 컴파일러에서 지원된다고 알려진 pragma 중 하나가 아닙니다. 이 오류를 해결하려면 지원되는 pragma만 사용합니다.  
  
 다음 샘플에서는 CS1633을 생성합니다.  
  
```  
// CS1633.cs // compile with: /W:1 #pragma unknown  // CS1633 class C { public static void Main() { } }  
```