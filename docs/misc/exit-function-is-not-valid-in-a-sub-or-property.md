---
title: "Sub 또는 Property에서는 &#39;Exit Function&#39;을 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30067"
  - "bc30067"
helpviewer_keywords: 
  - "BC30067"
ms.assetid: 207fef65-4383-4120-9e5a-e0e14d168a72
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Sub 또는 Property에서는 &#39;Exit Function&#39;을 사용할 수 없습니다.
`Exit Function`는 `Sub` 프로시저 또는 `Property` 프로시저에 나타납니다.`Exit` 문은 해당 문이 발생한 블록과 일치해야 합니다.  
  
 **오류 ID:** BC30067  
  
### 이 오류를 해결하려면  
  
-   `Exit Function`를 `Exit Sub` 또는 `Exit Property` 문으로 적절하게 바꿉니다.  
  
## 참고 항목  
 [Sub Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/sub-procedures)   
 [Function 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/function-procedures)   
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)