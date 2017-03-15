---
title: "&#39;Continue While&#39;은 &#39;While&#39; 문 내부에만 사용할 수 있습니다. | Microsoft Docs"
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
  - "vbc30784"
  - "bc30784"
helpviewer_keywords: 
  - "BC30784"
ms.assetid: b26c77b2-36ae-4dce-b048-f7c4b196faa4
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Continue While&#39;은 &#39;While&#39; 문 내부에만 사용할 수 있습니다.
`Continue While` 문은 `For...Next` 루프 내에서만 사용할 수 있습니다.  
  
 **오류 ID:** BC30784  
  
### 이 오류를 해결하려면  
  
1.  `Continue While` 문이 `Do...Loop` 루프에 있는 경우 해당 문을 `Continue Do`로 변경합니다.  
  
2.  `Continue While` 문이 `For...Next` 루프에 있는 경우 해당 문을 `Continue For`로 변경합니다.  
  
3.  그렇지 않으면 `Continue While` 문을 제거합니다.  
  
## 참고 항목  
 [Continue Statement](/dotnet/visual-basic/language-reference/statements/continue-statement)   
 [While...End While Statement](/dotnet/visual-basic/language-reference/statements/while-end-while-statement)