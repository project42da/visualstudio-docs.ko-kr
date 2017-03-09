---
title: "&#39;While&#39;은 짝이 되는 &#39;End While&#39;로 끝나야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30082"
  - "vbc30082"
helpviewer_keywords: 
  - "BC30082"
ms.assetid: 50b722b1-906f-4cb1-b5d4-fefab2ba3907
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;While&#39;은 짝이 되는 &#39;End While&#39;로 끝나야 합니다.
`While` 문이 해당 `End While` 문 없이 발생합니다.`End While` 문은 `While` 블록을 종료하는 데 사용되어야 합니다.  
  
 **오류 ID:** BC30082  
  
### 이 오류를 해결하려면  
  
1.  이 `While` 블록이 중첩된 `While` 블록 집합의 일부인 경우 각 블록이 올바르게 종료되었는지 확인합니다.  
  
2.  `While` 블록 끝에 `End While` 문을 추가합니다.  
  
## 참고 항목  
 [While...End While Statement](/dotnet/visual-basic/language-reference/statements/while-end-while-statement)