---
title: "&#39;Finally&#39; 밖으로는 분기할 수 없습니다. | Microsoft Docs"
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
  - "bc30101"
  - "vbc30101"
helpviewer_keywords: 
  - "BC30101"
ms.assetid: 16a0dc29-3657-4373-b77f-38f3cb80e6c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Finally&#39; 밖으로는 분기할 수 없습니다.
`Finally` 블록 내의 `GoTo` 문이 블록 밖으로 분기합니다.`Catch` 또는 `Finally` 블록 안이나 밖으로 분기할 수 없습니다.  
  
 **오류 ID:** BC30101  
  
### 이 오류를 해결하려면  
  
-   `GoTo` 문을 제거하고 의사 결정 또는 루프 제어 구조를 통해 프로그램 논리를 구현합니다.  
  
## 참고 항목  
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [GoTo Statement](/dotnet/visual-basic/language-reference/statements/goto-statement)   
 [Control Flow](/dotnet/visual-basic/programming-guide/language-features/control-flow/index)