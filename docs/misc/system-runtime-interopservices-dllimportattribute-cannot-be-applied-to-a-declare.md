---
title: "&#39;System.Runtime.InteropServices.DllImportAttribute&#39;는 &#39;Declare&#39;에 적용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31523"
  - "vbc31523"
helpviewer_keywords: 
  - "BC31523"
ms.assetid: 04c8a14f-9286-4f9a-aad5-a0555e5f09f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;System.Runtime.InteropServices.DllImportAttribute&#39;는 &#39;Declare&#39;에 적용할 수 없습니다.
`DllImportAttribute` 특성을 `Declare` 함수에 적용했습니다. 이 특성은 빈 `Function` 또는 `Sub`에서만 사용할 수 있습니다.  
  
 **오류 ID:** BC31523  
  
### 이 오류를 해결하려면  
  
1.  `Declare` 문에서 `DllImportAttribute` 특성을 제거합니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Declare Statement](/dotnet/visual-basic/language-reference/statements/declare-statement)