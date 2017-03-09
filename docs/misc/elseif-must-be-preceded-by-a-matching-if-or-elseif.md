---
title: "&#39;ElseIf&#39;는 짝이 되는 &#39;If&#39; 또는 &#39;ElseIf&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "bc36005"
  - "vbc36005"
helpviewer_keywords: 
  - "BC36005"
ms.assetid: bcebae85-b438-4839-bada-2f8f8dcc8a86
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ElseIf&#39;는 짝이 되는 &#39;If&#39; 또는 &#39;ElseIf&#39; 뒤에 와야 합니다.
`ElseIf` 문이 해당 `If` 문 없이 발생합니다.`ElseIf`는 `If` 문 또는 다른 `ElseIf` 문 뒤에 와야 합니다.  
  
 **오류 ID:** BC36005  
  
### 이 오류를 해결하려면  
  
1.  이 `If` 블록이 중첩된 제어 구조 집합의 일부인 경우 각 구조가 올바르게 종료되었는지 확인합니다.  
  
2.  이 `If` 블록 내에 중첩된 다른 제어 구조가 올바르게 종료되었는지 확인합니다.  
  
3.  이 `If` 블록의 형식이 올바르게 설정되었는지 확인합니다.  
  
## 참고 항목  
 [If...Then...Else Statement](/dotnet/visual-basic/language-reference/statements/if-then-else-statement)   
 [Decision Structures](/dotnet/visual-basic/programming-guide/language-features/control-flow/decision-structures)