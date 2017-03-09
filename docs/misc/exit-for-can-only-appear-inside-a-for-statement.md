---
title: "&#39;Exit For&#39;는 &#39;For&#39; 문 내부에만 사용할 수 있습니다. | Microsoft Docs"
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
  - "bc30096"
  - "vbc30096"
helpviewer_keywords: 
  - "BC30096"
ms.assetid: 1062a329-9364-4234-9175-4c70a51cb7ae
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Exit For&#39;는 &#39;For&#39; 문 내부에만 사용할 수 있습니다.
`Exit For` 문이 `For` 루프 외부에서 발생합니다.`Exit For`는 `For` 또는 `For Each` 문과 해당 `Next` 문 사이에서만 사용할 수 있습니다.  
  
 **오류 ID:** BC30096  
  
### 이 오류를 해결하려면  
  
1.  유효한 `For` 또는 `For Each` 문이 `Exit For` 앞에 있고 유효한 `Next` 문이 그 뒤에 있는지 확인합니다.  
  
2.  `For` 루프 내의 다른 컨트롤 구조가 올바르게 종료되었는지 확인합니다.  
  
## 참고 항목  
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)   
 [For Each...Next 문](/dotnet/visual-basic/language-reference/statements/for-each-next-statement)