---
title: "ParamArray 매개 변수는 &#39;ByVal&#39;로 선언해야 합니다. | Microsoft Docs"
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
  - "vbc30667"
  - "bc30667"
helpviewer_keywords: 
  - "BC30667"
ms.assetid: 583e231f-a4c9-47aa-ae37-7bac43b0b318
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ParamArray 매개 변수는 &#39;ByVal&#39;로 선언해야 합니다.
`ParamArray` 매개 변수는 `ByRef` 한정자를 사용할 수 없습니다.  
  
 **오류 ID:** BC30667  
  
### 이 오류를 해결하려면  
  
-   `ByVal` 한정자를 사용하여 `ParamArray` 매개 변수를 선언합니다.  
  
## 참고 항목  
 [ParamArray](/dotnet/visual-basic/language-reference/modifiers/paramarray)   
 [ByRef](/dotnet/visual-basic/language-reference/modifiers/byref)   
 [ByVal](/dotnet/visual-basic/language-reference/modifiers/byval)