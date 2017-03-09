---
title: "&#39;End With&#39;는 짝이 되는 &#39;With&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "bc30093"
  - "vbc30093"
helpviewer_keywords: 
  - "BC30093"
ms.assetid: b0f1f7d5-0c33-4b97-8043-f0f5b40ca5d7
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End With&#39;는 짝이 되는 &#39;With&#39; 뒤에 와야 합니다.
`End With` 문이 해당 `With` 문 없이 발생합니다.`End With`는 해당 `With` 문 뒤에 와야 합니다.  
  
 **오류 ID:** BC30093  
  
### 이 오류를 해결하려면  
  
1.  이 `With` 블록이 중첩된 `With` 블록 집합의 일부인 경우 각 블록이 올바르게 종료되었는지 확인합니다.  
  
2.  `With` 블록 내의 다른 컨트롤 구조체가 올바르게 종료되었는지 확인합니다.  
  
3.  이 `With` 블록의 형식이 올바르게 설정되었는지 확인합니다.  
  
## 참고 항목  
 [With...End With Statement](/dotnet/visual-basic/language-reference/statements/with-end-with-statement)