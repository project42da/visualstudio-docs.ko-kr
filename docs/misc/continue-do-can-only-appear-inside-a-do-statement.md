---
title: "&#39;Continue Do&#39;는 &#39;Do&#39; 문 내부에만 사용할 수 있습니다. | Microsoft Docs"
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
  - "vbc30782"
  - "bc30782"
helpviewer_keywords: 
  - "BC30782"
ms.assetid: c6b35e63-4d84-449d-9685-41a1bc0a7f35
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Continue Do&#39;는 &#39;Do&#39; 문 내부에만 사용할 수 있습니다.
`Continue Do` 문은 `Do...Loop` 루프 내에서만 사용할 수 있습니다.  
  
 **오류 ID:** BC30782  
  
### 이 오류를 해결하려면  
  
1.  `Continue Do` 문이 `For...Next` 루프에 있는 경우 해당 문을 `Continue For`로 변경합니다.  
  
2.  `Continue Do` 문이 `While...End While` 루프에 있는 경우 해당 문을 `Continue While`로 변경합니다.  
  
3.  그렇지 않으면 `Continue Do` 문을 제거합니다.  
  
## 참고 항목  
 [Continue Statement](/dotnet/visual-basic/language-reference/statements/continue-statement)   
 [Do...Loop Statement](/dotnet/visual-basic/language-reference/statements/do-loop-statement)