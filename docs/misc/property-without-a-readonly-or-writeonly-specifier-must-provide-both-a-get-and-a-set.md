---
title: "&#39;ReadOnly&#39; 또는 &#39;WriteOnly&#39; 지정자가 없는 속성에는 &#39;Get&#39;과 &#39;Set&#39;을 모두 지정해야 합니다. | Microsoft Docs"
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
  - "bc30124"
  - "vbc30124"
helpviewer_keywords: 
  - "BC30124"
ms.assetid: b24fc997-9a6b-44d1-b712-dab498a6fc72
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReadOnly&#39; 또는 &#39;WriteOnly&#39; 지정자가 없는 속성에는 &#39;Get&#39;과 &#39;Set&#39;을 모두 지정해야 합니다.
속성이 `ReadOnly` 또는 `WriteOnly`로 선언되지 않으면 해당 값을 읽거나 쓰기 위한 프로시저를 제공해야 합니다.  
  
 **오류 ID:** BC30124  
  
### 이 오류를 해결하려면  
  
1.  `Property` 문과 `End Property` 문 사이에 `Get` 프로시저와 `Set` 프로시저를 모두 포함해야 합니다.  
  
2.  `Property` 선언 내에서 다른 프로시저가 올바르게 종료되었는지 확인합니다.  
  
## 참고 항목  
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement)   
 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)