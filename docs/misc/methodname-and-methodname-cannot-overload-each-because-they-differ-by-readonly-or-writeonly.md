---
title: "&#39;&lt;methodname&gt;&#39;과 &#39;&lt;methodname&gt;&#39;은 &#39;ReadOnly&#39; 또는 &#39;WriteOnly&#39;가 다르므로 서로 오버로드할 수 없습니다. | Microsoft Docs"
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
  - "vbc30366"
  - "BC30366"
helpviewer_keywords: 
  - "BC30366"
ms.assetid: 2440fd29-e205-4004-b2ee-9d954d17b8d3
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;methodname&gt;&#39;과 &#39;&lt;methodname&gt;&#39;은 &#39;ReadOnly&#39; 또는 &#39;WriteOnly&#39;가 다르므로 서로 오버로드할 수 없습니다.
해당 `ReadOnly` 및 `WriteOnly` 선언에서만 서로 다른 두 메서드를 오버로드하려 했습니다. 인수 목록 외에 다른 항목을 사용하여 버전을 구분할 수 없습니다.  
  
 **오류 ID:** BC30366  
  
### 이 오류를 해결하려면  
  
-   메서드에 `ReadOnly` 및 `WriteOnly` 이외에 다른 차별점이 있는지 확인합니다.  
  
## 참고 항목  
 [Considerations in Overloading Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures)