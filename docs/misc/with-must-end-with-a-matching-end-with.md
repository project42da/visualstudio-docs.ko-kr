---
title: "&#39;With&#39;는 짝이 되는 &#39;End With&#39;로 끝나야 합니다. | Microsoft Docs"
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
  - "bc30085"
  - "vbc30085"
helpviewer_keywords: 
  - "BC30085"
ms.assetid: aa88f4d0-be5f-4efe-a4ef-80e6d6124e6e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;With&#39;는 짝이 되는 &#39;End With&#39;로 끝나야 합니다.
`With` 문이 해당 `End With` 문 없이 발생합니다.`End With` 문은 `With` 블록을 종료하는 데 사용되어야 합니다.  
  
 **오류 ID:** BC30085  
  
### 이 오류를 해결하려면  
  
-   이 `With` 블록이 중첩된 `With` 블록 집합의 일부인 경우 각 블록이 올바르게 종료되었는지 확인합니다.  
  
-   `With` 블록 끝에 `End With` 문을 추가합니다.  
  
## 참고 항목  
 [With...End With Statement](/dotnet/visual-basic/language-reference/statements/with-end-with-statement)