---
title: "Function 또는 Property에서는 &#39;Exit Sub&#39;를 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30065"
  - "vbc30065"
helpviewer_keywords: 
  - "BC30065"
ms.assetid: d6426861-ba64-4dca-9100-262c6c058bd9
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Function 또는 Property에서는 &#39;Exit Sub&#39;를 사용할 수 없습니다.
`Exit Sub`는 `Function` 프로시저 또는 `Property` 프로시저에 나타납니다.`Exit` 문은 해당 문이 발생한 블록과 일치해야 합니다.  
  
 **오류 ID:** BC30065  
  
### 이 오류를 해결하려면  
  
-   `Exit Sub`를 `Exit Function` 또는 `Exit Property` 문으로 적절하게 바꿉니다.  
  
## 참고 항목  
 [Sub Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/sub-procedures)   
 [Function 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/function-procedures)   
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)