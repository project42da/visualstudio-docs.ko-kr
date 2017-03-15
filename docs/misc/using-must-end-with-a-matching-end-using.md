---
title: "&#39;Using&#39;은 짝이 되는 &#39;End Using&#39;으로 끝나야 합니다. | Microsoft Docs"
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
  - "vbc36008"
  - "bc36008"
helpviewer_keywords: 
  - "BC36008"
ms.assetid: 83269108-b169-40a6-bbcc-af1ac8fcfd67
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Using&#39;은 짝이 되는 &#39;End Using&#39;으로 끝나야 합니다.
`Using` 문이 해당 `End Using` 문 없이 발생합니다.  
  
 `End Using` 문은 `Using` 블록을 종료하는 데 사용되어야 합니다.  
  
 **오류 ID:** BC36008  
  
### 이 오류를 해결하려면  
  
1.  이 `Using` 블록이 중첩된 `Using` 블록 집합의 일부인 경우 각 블록이 올바르게 종료되었는지 확인합니다.  
  
2.  `Using` 블록 끝에 `End Using` 문을 추가합니다.  
  
## 참고 항목  
 [Using Statement](/dotnet/visual-basic/language-reference/statements/using-statement)   
 [How to: Dispose of a System Resource](../Topic/How%20to:%20Dispose%20of%20a%20System%20Resource%20\(Visual%20Basic\).md)