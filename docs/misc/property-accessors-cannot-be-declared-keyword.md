---
title: "속성 접근자를 &#39;&lt;keyword&gt;&#39;로 선언할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31099"
  - "bc31099"
helpviewer_keywords: 
  - "BC31099"
ms.assetid: d6f3b989-39b9-4c47-995a-bd83ec03d7b8
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 속성 접근자를 &#39;&lt;keyword&gt;&#39;로 선언할 수 없습니다.
`Get` 또는 `Set` 프로시저 선언에 속성 프로시저에 적합하지 않은 키워드가 포함되어 있습니다.  
  
 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement) 및 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)에서는 액세스 한정자\(`Public`, `Protected`, `Friend`, `Protected Friend`, `Private`\)만 허용됩니다.  
  
 **오류 ID:** BC31099  
  
### 이 오류를 해결하려면  
  
-   `Get` 또는 `Set` 문에서 잘못된 키워드를 제거합니다.  
  
## 참고 항목  
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)