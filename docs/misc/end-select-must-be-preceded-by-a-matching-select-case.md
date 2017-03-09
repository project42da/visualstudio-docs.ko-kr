---
title: "&#39;End Select&#39;는 짝이 되는 &#39;Select Case&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "bc30088"
  - "vbc30088"
helpviewer_keywords: 
  - "BC30088"
ms.assetid: 9de8c0d4-4ce9-45cf-98d6-8f68bba507a5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End Select&#39;는 짝이 되는 &#39;Select Case&#39; 뒤에 와야 합니다.
`End Select` 문이 해당 `Select` 또는 `Select Case` 문 없이 발생합니다.`End Select`는 `Select` 또는 `Select Case` 문 뒤에 와야 합니다.  
  
 **오류 ID:** BC30088  
  
### 이 오류를 해결하려면  
  
1.  이 `Select` 블록이 중첩된 `Select` 블록 집합의 일부인 경우 각 블록이 올바르게 종료되었는지 확인합니다.  
  
2.  `Select` 블록 내의 다른 컨트롤 구조체가 올바르게 종료되었는지 확인합니다.  
  
3.  이 `Select` 블록의 형식이 올바르게 설정되었는지 확인합니다.  
  
## 참고 항목  
 [Select...Case Statement](/dotnet/visual-basic/language-reference/statements/select-case-statement)