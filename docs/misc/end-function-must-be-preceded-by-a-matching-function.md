---
title: "&#39;End Function&#39;은 짝이 되는 &#39;Function&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "bc30430"
  - "vbc30430"
helpviewer_keywords: 
  - "BC30430"
ms.assetid: de66a6b4-0321-45c2-aca0-87d2b4244b31
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End Function&#39;은 짝이 되는 &#39;Function&#39; 뒤에 와야 합니다.
`End Function` 문이 앞에서 일치하는 `Function` 프로시저 정의 없이 코드에 나타납니다.  
  
 **오류 ID:** BC30430  
  
### 이 오류를 해결하려면  
  
1.  `End Function` 문이 중복되는 경우 제거합니다.  
  
2.  `Function` 프로시저가 누락된 경우 제공합니다.  
  
3.  `End Function`을 코드의 적절한 위치로 이동합니다.  
  
## 참고 항목  
 [Function 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/function-procedures)   
 [End \<keyword\> Statement](../Topic/End%20%3Ckeyword%3E%20Statement%20\(Visual%20Basic\).md)