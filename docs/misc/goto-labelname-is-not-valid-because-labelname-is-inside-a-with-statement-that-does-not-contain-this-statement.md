---
title: "&#39;&lt;labelname&gt;&#39;이 이 문을 포함하지 않는 &#39;With&#39; 문 내부에 있으므로 &#39;GoTo &lt;labelname&gt;&#39;은 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30756"
  - "vbc30756"
helpviewer_keywords: 
  - "BC30756"
ms.assetid: 9c39d4ad-0b9b-45e9-b6c2-d983144b5b23
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;labelname&gt;&#39;이 이 문을 포함하지 않는 &#39;With&#39; 문 내부에 있으므로 &#39;GoTo &lt;labelname&gt;&#39;은 사용할 수 없습니다.
`GoTo` 문은 현재 코드 블록 내에서 점프하도록 제한됩니다.  
  
 **오류 ID:** BC30756  
  
### 이 오류를 해결하려면  
  
-   `GoTo` 문과 레이블이 모두 `With` 블록 내에 있도록 코드를 재구성합니다.  
  
## 참고 항목  
 [GoTo Statement](/dotnet/visual-basic/language-reference/statements/goto-statement)