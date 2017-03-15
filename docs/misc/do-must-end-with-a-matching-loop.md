---
title: "&#39;Do&#39;는 짝이 되는 &#39;Loop&#39;로 끝나야 합니다. | Microsoft Docs"
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
  - "vbc30083"
  - "bc30083"
helpviewer_keywords: 
  - "BC30083"
ms.assetid: b157b9e3-57fa-4324-a13d-b37bcf0861e6
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Do&#39;는 짝이 되는 &#39;Loop&#39;로 끝나야 합니다.
`Do` 문이 해당 `Loop` 문 없이 발생합니다.`Loop` 문은 `Do` 루프를 종료하는 데 사용되어야 합니다.  
  
 **오류 ID:** BC30083  
  
### 이 오류를 해결하려면  
  
-   이 `Do` 루프가 중첩된 루프 집합의 일부인 경우 각 루프가 제대로 종료되어야 합니다.  
  
-   `Do` 루프 끝에 `Loop` 문을 추가합니다.  
  
## 참고 항목  
 [Do...Loop Statement](/dotnet/visual-basic/language-reference/statements/do-loop-statement)