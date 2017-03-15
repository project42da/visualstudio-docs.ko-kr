---
title: "&#39;Next&#39;는 짝이 되는 &#39;For&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "vbc30092"
  - "bc30092"
helpviewer_keywords: 
  - "BC30092"
ms.assetid: 4bf49bb2-c69b-443d-aa58-cb40fcfb1370
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Next&#39;는 짝이 되는 &#39;For&#39; 뒤에 와야 합니다.
`Next` 문이 해당 `For` 또는 `For Each` 문 없이 발생합니다.`Next`는 해당 `For` 또는 `For Each` 문 뒤에 와야 합니다.  
  
 **오류 ID:** BC30092  
  
### 이 오류를 해결하려면  
  
1.  이 `For` 루프가 중첩된 `For` 루프 집합의 일부인 경우 각 루프가 제대로 종료되어야 합니다.  
  
2.  `For` 루프 내의 다른 컨트롤 구조가 올바르게 종료되었는지 확인합니다.  
  
3.  이 `For` 루프의 형식이 올바르게 설정되었는지 확인합니다.  
  
## 참고 항목  
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)   
 [For Each...Next 문](/dotnet/visual-basic/language-reference/statements/for-each-next-statement)