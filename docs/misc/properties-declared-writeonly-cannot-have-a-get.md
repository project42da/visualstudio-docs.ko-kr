---
title: "&#39;WriteOnly&#39;로 선언된 속성에는 &#39;Get&#39;을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30023"
  - "vbc30023"
helpviewer_keywords: 
  - "BC30023"
ms.assetid: ac290f7d-cbc3-4979-a5d9-1ae1bb26e79d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;WriteOnly&#39;로 선언된 속성에는 &#39;Get&#39;을 사용할 수 없습니다.
`Get` 프로시저가 속성의 값을 읽습니다.`WriteOnly` 속성은 읽을 수 없습니다.  
  
 **오류 ID:** BC30023  
  
### 이 오류를 해결하려면  
  
-   `Property` 문에서 `WriteOnly` 키워드를 제거하거나 속성 본문에서 `Get` 프로시저를 제거합니다.  
  
## 참고 항목  
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement)   
 [WriteOnly](/dotnet/visual-basic/language-reference/modifiers/writeonly)