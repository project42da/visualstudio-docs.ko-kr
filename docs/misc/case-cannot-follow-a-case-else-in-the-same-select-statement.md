---
title: "&#39;Case&#39;는 같은 &#39;Select&#39; 문에서 &#39;Case Else&#39; 뒤에 올 수 없습니다. | Microsoft Docs"
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
  - "bc30321"
  - "vbc30321"
helpviewer_keywords: 
  - "BC30321"
ms.assetid: eeedbceb-2c8d-4acb-b84c-8b42c058f083
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Case&#39;는 같은 &#39;Select&#39; 문에서 &#39;Case Else&#39; 뒤에 올 수 없습니다.
`Case Else` 문은 최초 `Case`와 일치하는 부분이 없는 경우 실행될 문을 지정합니다. 동일한 `Select` 블록에서 `Case` 문이 `Case Else` 다음에 있습니다.  
  
 **오류 ID:** BC30321  
  
### 이 오류를 해결하려면  
  
-   `Case Else`를 `Case` 문 다음에 적절한 위치로 이동합니다.  
  
## 참고 항목  
 [Select...Case Statement](/dotnet/visual-basic/language-reference/statements/select-case-statement)