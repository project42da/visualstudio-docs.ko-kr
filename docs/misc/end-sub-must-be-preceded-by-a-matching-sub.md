---
title: "&#39;End Sub&#39;는 짝이 되는 &#39;Sub&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "vbc30429"
  - "bc30429"
helpviewer_keywords: 
  - "BC30429"
ms.assetid: cf9d0cfe-5dfa-4f6d-9d10-69eb16e413e1
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End Sub&#39;는 짝이 되는 &#39;Sub&#39; 뒤에 와야 합니다.
`End Sub` 문이 앞에서 일치하는 `Sub` 프로시저 정의 없이 코드에 나타납니다.  
  
 **오류 ID:** BC30429  
  
### 이 오류를 해결하려면  
  
-   `End Sub` 문이 중복되는 경우 제거합니다.  
  
-   `Sub` 프로시저가 누락된 경우 제공합니다.  
  
-   `End Sub`를 코드의 적절한 위치로 이동합니다.  
  
## 참고 항목  
 [Sub Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/sub-procedures)   
 [End \<keyword\> Statement](../Topic/End%20%3Ckeyword%3E%20Statement%20\(Visual%20Basic\).md)