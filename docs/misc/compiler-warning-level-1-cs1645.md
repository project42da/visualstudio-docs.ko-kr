---
title: "컴파일러 경고(수준 1) CS1645 | Microsoft Docs"
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
  - "CS1645"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1645"
ms.assetid: ea45fb20-b696-4d4e-b893-edde9d96bd3a
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1645
'feature' 기능은 표준화된 ISO C\# 언어 사양의 일부가 아니므로 다른 컴파일러에서 지원하지 않을 수도 있습니다.  
  
 사용 중인 기능이 ISO 표준에 속하지 않습니다. 이 기능을 사용하는 코드가 다른 컴파일러에서 컴파일되지 않을 수 있습니다.  
  
```  
// CS1645.cs // compile with: /W:1 /t:module /langversion:ISO-1 [assembly:System.CLSCompliant(false)] // To supress the warning use the switch: /nowarn:1645 [module:System.CLSCompliant(false)]   // CS1645 class Test { }  
```