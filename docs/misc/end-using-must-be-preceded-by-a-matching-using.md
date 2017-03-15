---
title: "&#39;End Using&#39;은 짝이 되는 &#39;Using&#39; 뒤에 와야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36007"
  - "vbc36007"
helpviewer_keywords: 
  - "BC36007"
ms.assetid: 10fb31ba-9b6c-403f-bacc-c7b5df14f1dd
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End Using&#39;은 짝이 되는 &#39;Using&#39; 뒤에 와야 합니다.
`End Using` 문이 앞에서 일치하는 `Using` 선언 없이 나타납니다.  
  
 **오류 ID:** BC36007  
  
### 이 오류를 해결하려면  
  
-   `End Using` 문이 중복되는 경우 제거합니다.  
  
-   [Using Statement](/dotnet/visual-basic/language-reference/statements/using-statement)이 누락된 경우 제공합니다.  
  
-   `End Using` 문을 코드의 적절한 위치로 이동합니다.  
  
## 참고 항목  
 [End \<keyword\> Statement](../Topic/End%20%3Ckeyword%3E%20Statement%20\(Visual%20Basic\).md)