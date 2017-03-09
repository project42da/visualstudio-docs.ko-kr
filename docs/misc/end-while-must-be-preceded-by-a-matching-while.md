---
title: "&#39;End While&#39;은 짝이 되는 &#39;While&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "vbc30090"
  - "bc30090"
helpviewer_keywords: 
  - "BC30090"
ms.assetid: 302b26b8-8fa4-4e49-86f0-d7c49fec485f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End While&#39;은 짝이 되는 &#39;While&#39; 뒤에 와야 합니다.
`End While` 문이 해당 `While` 문 없이 발생합니다.`End While`은 해당 `While` 문 뒤에 와야 합니다.  
  
 **오류 ID:** BC30090  
  
### 이 오류를 해결하려면  
  
1.  이 `While` 블록이 중첩된 `While` 블록 집합의 일부인 경우 각 블록이 올바르게 종료되었는지 확인합니다.  
  
2.  `While` 블록 내의 다른 컨트롤 구조체가 올바르게 종료되었는지 확인합니다.  
  
3.  이 `While` 블록의 형식이 올바르게 설정되었는지 확인합니다.  
  
## 참고 항목  
 [While...End While Statement](/dotnet/visual-basic/language-reference/statements/while-end-while-statement)