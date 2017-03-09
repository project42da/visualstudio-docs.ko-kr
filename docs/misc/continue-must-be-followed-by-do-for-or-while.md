---
title: "&#39;Continue&#39; 다음에는 &#39;Do&#39;, &#39;For&#39; 또는 &#39;While&#39;이 와야 합니다. | Microsoft Docs"
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
  - "bc30781"
  - "vbc30781"
helpviewer_keywords: 
  - "BC30781"
ms.assetid: a0d5854d-ca44-4c6b-9458-4fc50d29281a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Continue&#39; 다음에는 &#39;Do&#39;, &#39;For&#39; 또는 &#39;While&#39;이 와야 합니다.
`Continue` 문이 `Do...Loop` 루프, `For...Next` 루프 또는 `While...End While` 루프 내에 표시되는지에 따라 `Continue` 문 뒤에는 `Do`, `For` 또는 `While`이 와야 합니다.  
  
 **오류 ID:** BC30781  
  
### 이 오류를 해결하려면  
  
1.  `Continue` 문이 `Do...Loop` 루프에 있는 경우 해당 문을 `Continue Do`로 변경합니다.  
  
2.  `Continue` 문이 `For...Next` 루프에 있는 경우 해당 문을 `Continue For`로 변경합니다.  
  
3.  `Continue` 문이 `While...End While` 루프에 있는 경우 해당 문을 `Continue While`로 변경합니다.  
  
4.  그렇지 않으면 `Continue` 문을 제거합니다.  
  
## 참고 항목  
 [Continue Statement](/dotnet/visual-basic/language-reference/statements/continue-statement)