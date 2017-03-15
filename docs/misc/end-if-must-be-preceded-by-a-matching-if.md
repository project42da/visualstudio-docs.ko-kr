---
title: "&#39;End If&#39;는 짝이 되는 &#39;If&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "bc30087"
  - "vbc30087"
helpviewer_keywords: 
  - "BC30087"
ms.assetid: 81c056bb-267e-44ef-9a44-3a41273090ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End If&#39;는 짝이 되는 &#39;If&#39; 뒤에 와야 합니다.
`End If` 문이 해당 `If` 문 없이 발생합니다.`End If`는 `If` 문 뒤에 와야 합니다.  
  
 **오류 ID:** BC30087  
  
### 이 오류를 해결하려면  
  
1.  이 `If` 블록이 중첩된 `If` 블록 집합의 일부인 경우 각 블록이 올바르게 종료되었는지 확인합니다.  
  
2.  `If` 블록 내의 다른 컨트롤 구조체가 올바르게 종료되었는지 확인합니다.  
  
3.  이 `If` 블록의 형식이 올바르게 설정되었는지 확인합니다.  
  
## 참고 항목  
 [If...Then...Else Statement](/dotnet/visual-basic/language-reference/statements/if-then-else-statement)