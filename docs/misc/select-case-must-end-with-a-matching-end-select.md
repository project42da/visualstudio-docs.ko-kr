---
title: "&#39;Select Case&#39;는 짝이 되는 &#39;End Select&#39;로 끝나야 합니다. | Microsoft Docs"
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
  - "vbc30095"
  - "bc30095"
helpviewer_keywords: 
  - "BC30095"
ms.assetid: f0809aa5-e6c9-43c9-9664-4ff02825c3d8
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Select Case&#39;는 짝이 되는 &#39;End Select&#39;로 끝나야 합니다.
`Select` 또는 `Select Case` 문이 해당 `End Select` 문 없이 발생합니다.`End Select` 문은 `Select` 블록을 종료하는 데 사용되어야 합니다.  
  
 **오류 ID:** BC30095  
  
### 이 오류를 해결하려면  
  
1.  이 `Select` 블록이 중첩된 `Select` 블록 집합의 일부인 경우 각 블록이 올바르게 종료되었는지 확인합니다.  
  
2.  `Select` 블록 끝에 `End Select` 문을 추가합니다.  
  
## 참고 항목  
 [Select...Case Statement](/dotnet/visual-basic/language-reference/statements/select-case-statement)