---
title: "&#39;ReadOnly&#39;로 선언된 속성에는 &#39;Set&#39;을 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30022"
  - "bc30022"
helpviewer_keywords: 
  - "BC30022"
ms.assetid: a22eff96-8c18-47c4-9ef0-f98b2ab8a5d8
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReadOnly&#39;로 선언된 속성에는 &#39;Set&#39;을 사용할 수 없습니다.
`Set` 프로시저가 속성의 값을 씁니다.`ReadOnly` 속성은 쓸 수 없습니다.  
  
 **오류 ID:** BC30022  
  
### 이 오류를 해결하려면  
  
-   `Property` 문에서 `ReadOnly` 키워드를 제거하거나 속성 본문에서 `Set` 프로시저를 제거합니다.  
  
## 참고 항목  
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)   
 [ReadOnly](/dotnet/visual-basic/language-reference/modifiers/readonly)