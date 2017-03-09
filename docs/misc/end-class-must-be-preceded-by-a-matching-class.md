---
title: "&#39;End Class&#39;는 짝이 되는 &#39;Class&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "vbc30460"
  - "bc30460"
helpviewer_keywords: 
  - "BC30460"
ms.assetid: 0e6989da-f281-4ac4-8579-b6d627be8de8
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End Class&#39;는 짝이 되는 &#39;Class&#39; 뒤에 와야 합니다.
`End Class`는 `Class` 블록을 완료하는 데 사용되므로 블록의 끝에 한 번만 나타날 수 있습니다. 중복 `End Class`가 있거나 `End Class` 문이 해당 `Class` 블록의 경계 외부에 나타납니다.  
  
 **오류 ID:** BC30460  
  
### 이 오류를 해결하려면  
  
-   중복 `End Class` 문을 찾아서 제거합니다.  
  
-   `End Class` 문을 코드의 적절한 위치로 이동합니다.  
  
## 참고 항목  
 [End \<keyword\> Statement](../Topic/End%20%3Ckeyword%3E%20Statement%20\(Visual%20Basic\).md)