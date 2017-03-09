---
title: "&#39;WriteOnly&#39; 속성에는 &#39;Set&#39;을 지정해야 합니다. | Microsoft Docs"
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
  - "bc30125"
  - "vbc30125"
helpviewer_keywords: 
  - "BC30125"
ms.assetid: c2b18086-9cd9-4094-b9a9-491c8d617096
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;WriteOnly&#39; 속성에는 &#39;Set&#39;을 지정해야 합니다.
속성이 `WriteOnly`로 선언되면 해당 값을 쓰기 위한 프로시저를 제공해야 합니다.  
  
 **오류 ID:** BC30125  
  
### 이 오류를 해결하려면  
  
1.  `Property` 문과 `End Property` 문 사이에 `Set` 프로시저를 포함해야 합니다.  
  
2.  `Property` 선언 내에서 다른 프로시저가 올바르게 종료되었는지 확인합니다.  
  
## 참고 항목  
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)