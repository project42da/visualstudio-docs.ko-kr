---
title: "&#39;If&#39;는 짝이 되는 &#39;End If&#39;로 끝나야 합니다. | Microsoft Docs"
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
  - "bc30081"
  - "vbc30081"
helpviewer_keywords: 
  - "BC30081"
ms.assetid: e5905d59-56bb-4daf-aca5-5ff847fc62f6
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;If&#39;는 짝이 되는 &#39;End If&#39;로 끝나야 합니다.
`If` 문이 해당 `End If` 문 없이 발생합니다.`End If` 문은 `If` 블록을 종료하는 데 사용되어야 합니다.  
  
 **오류 ID:** BC30081  
  
### 이 오류를 해결하려면  
  
1.  이 `If` 블록이 중첩된 `If` 블록 집합의 일부인 경우 각 블록이 올바르게 종료되었는지 확인합니다.  
  
2.  `If` 블록 끝에 `End If` 문을 추가합니다.  
  
## 참고 항목  
 [If...Then...Else Statement](/dotnet/visual-basic/language-reference/statements/if-then-else-statement)