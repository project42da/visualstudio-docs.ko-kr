---
title: "&#39;Enum&#39;은 짝이 되는 &#39;End Enum&#39;으로 끝나야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30185"
  - "bc30185"
helpviewer_keywords: 
  - "BC30185"
ms.assetid: 43dd759c-1207-4dcc-b2e2-478d91e6f2f8
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Enum&#39;은 짝이 되는 &#39;End Enum&#39;으로 끝나야 합니다.
`Enum` 문이 해당 `End Enum` 문 없이 발생합니다.`End Enum` 문은 열거형을 종료하는 데 사용되어야 합니다.  
  
 **오류 ID:** BC30185  
  
### 이 오류를 해결하려면  
  
1.  `Enum` 멤버의 형식이 올바르게 지정되었는지 확인합니다.  
  
2.  열거형의 끝에 `End Enum` 문을 추가합니다.  
  
## 참고 항목  
 [Enum Statement](/dotnet/visual-basic/language-reference/statements/enum-statement)