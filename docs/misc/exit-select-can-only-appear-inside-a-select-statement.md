---
title: "&#39;Exit Select&#39;는 &#39;Select&#39; 문 내부에만 사용할 수 있습니다. | Microsoft Docs"
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
  - "vbc30099"
  - "bc30099"
helpviewer_keywords: 
  - "BC30099"
ms.assetid: 37c65fc8-6ad9-456a-80b8-66288c62ef24
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Exit Select&#39;는 &#39;Select&#39; 문 내부에만 사용할 수 있습니다.
`Exit Select` 문이 `Select` 블록 외부에서 발생합니다.`Exit Select`는 `Select` 또는 `Select Case` 문과 해당 `End Select` 문 사이에서만 사용할 수 있습니다.  
  
 **오류 ID:** BC30099  
  
### 이 오류를 해결하려면  
  
1.  유효한 `Select` 또는 `Select Case` 문이 `Exit Select` 앞에 있고 유효한 `End Select` 문이 그 뒤에 있는지 확인합니다.  
  
2.  `Select` 블록 내의 다른 컨트롤 구조체가 올바르게 종료되었는지 확인합니다.  
  
## 참고 항목  
 [Select...Case Statement](/dotnet/visual-basic/language-reference/statements/select-case-statement)