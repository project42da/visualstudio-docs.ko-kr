---
title: "&#39;For&#39;는 짝이 되는 &#39;Next&#39;로 끝나야 합니다. | Microsoft Docs"
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
  - "vbc30084"
  - "bc30084"
helpviewer_keywords: 
  - "BC30084"
ms.assetid: 4c5e49c2-7343-4487-b5f8-a38c97ba895b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;For&#39;는 짝이 되는 &#39;Next&#39;로 끝나야 합니다.
`For` 문이 해당 `Next` 문 없이 발생합니다.`Next` 문은 `For` 루프를 종료하는 데 사용되어야 합니다.  
  
 **오류 ID:** BC30084  
  
### 이 오류를 해결하려면  
  
-   이 `For` 루프가 중첩된 루프 집합의 일부인 경우 각 루프가 제대로 종료되어야 합니다.  
  
-   `For` 루프 끝에 `Next` 문을 추가합니다.  
  
## 참고 항목  
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)