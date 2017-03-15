---
title: "&#39;Loop&#39;는 짝이 맞는 &#39;Do&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "vbc30091"
  - "bc30091"
helpviewer_keywords: 
  - "BC30091"
ms.assetid: 05f47b2f-4eaa-4911-981e-3fce737d249f
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Loop&#39;는 짝이 맞는 &#39;Do&#39; 뒤에 와야 합니다.
`Loop` 문이 해당 `Do` 문 없이 발생합니다.`Loop`는 해당 `Do` 문 뒤에 와야 합니다.  
  
 **오류 ID:** BC30091  
  
### 이 오류를 해결하려면  
  
1.  이 `Do` 루프가 중첩된 `Do` 루프 집합의 일부인 경우 각 루프가 제대로 종료되어야 합니다.  
  
2.  `Do` 루프 내의 다른 컨트롤 구조가 올바르게 종료되었는지 확인합니다.  
  
3.  이 `Do` 루프의 형식이 올바르게 설정되었는지 확인합니다.  
  
## 참고 항목  
 [Do...Loop Statement](/dotnet/visual-basic/language-reference/statements/do-loop-statement)