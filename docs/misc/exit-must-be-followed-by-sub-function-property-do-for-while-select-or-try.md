---
title: "&#39;Exit&#39; 뒤에는 &#39;Sub&#39;, &#39;Function&#39;, &#39;Property&#39;, &#39;Do&#39;, &#39;For&#39;, &#39;While&#39;, &#39;Select&#39; 또는 &#39;Try&#39;가 와야 합니다. | Microsoft Docs"
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
  - "bc30240"
  - "vbc30240"
helpviewer_keywords: 
  - "BC30240"
ms.assetid: 91078689-f4bf-4331-a475-10bc9fe7cd0c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Exit&#39; 뒤에는 &#39;Sub&#39;, &#39;Function&#39;, &#39;Property&#39;, &#39;Do&#39;, &#39;For&#39;, &#39;While&#39;, &#39;Select&#39; 또는 &#39;Try&#39;가 와야 합니다.
`Exit` 문에 잘못된 키워드가 포함되어 있습니다.`Exit`는 블록 뒤에 나오는 문에 제어가 전송될 블록을 지정해야 합니다. 예를 들어 `End While`입니다.  
  
 **오류 ID:** BC30240  
  
### 이 오류를 해결하려면  
  
-   `Exit` 다음에 유효한 키워드를 추가하거나 `Exit` 문을 제거합니다.  
  
## 참고 항목  
 [Exit Statement](/dotnet/visual-basic/language-reference/statements/exit-statement)