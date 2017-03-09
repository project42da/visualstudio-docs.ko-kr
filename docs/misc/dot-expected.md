---
title: "&#39;.&#39;가 필요합니다. | Microsoft Docs"
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
  - "bc30287"
  - "vbc30287"
helpviewer_keywords: 
  - "BC30287"
ms.assetid: 7d7b4934-b521-4ed3-b054-aeb71f8daacf
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;.&#39;가 필요합니다.
코드에 느낌표\(`!`\)를 포함하는 `Handles` 절이 있습니다.  
  
 **오류 ID:** BC30287  
  
### 이 오류를 해결하려면  
  
1.  `Handles` 절이 개체 내의 이벤트를 참조하는 경우 마침표\(`.`\)를 사용하여 이벤트에서 개체를 분리합니다.  
  
     이 예제에서는 `Button1` 개체의 `Click` 이벤트를 처리합니다.  
  
     [!CODE [VbVbalrEventError#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#21)]  
  
## 참고 항목  
 [Handles](/dotnet/visual-basic/language-reference/statements/handles-clause)