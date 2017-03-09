---
title: "&#39;ReadOnly&#39; 속성에는 &#39;Get&#39;을 지정해야 합니다. | Microsoft Docs"
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
  - "bc30126"
  - "vbc30126"
helpviewer_keywords: 
  - "BC30126"
ms.assetid: a522c39e-1f11-45c8-a00b-3546c842909a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReadOnly&#39; 속성에는 &#39;Get&#39;을 지정해야 합니다.
속성이 `ReadOnly`로 선언되면 해당 값을 읽기 위한 프로시저를 제공해야 합니다.  
  
 **오류 ID:** BC30126  
  
### 이 오류를 해결하려면  
  
1.  `Property` 문과 `End Property` 문 사이에 `Get` 프로시저를 포함해야 합니다.  
  
2.  `Property` 선언 내에서 다른 프로시저가 올바르게 종료되었는지 확인합니다.  
  
## 참고 항목  
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement)