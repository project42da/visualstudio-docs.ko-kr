---
title: "&#39;&lt;attributename&gt;&#39; 특성을 모듈에 적용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30549"
  - "bc30549"
helpviewer_keywords: 
  - "BC30549"
ms.assetid: b38fea31-6b0b-4c54-9518-b59226505802
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;attributename&gt;&#39; 특성을 모듈에 적용할 수 없습니다.
`AttributeUsageAttribute`가 `AttributeTargets.Module`을 지정하지 않은 모듈에 특성을 적용하려고 했습니다. 특성이 선언되었을 때 모듈에 적용되도록 정의되지 않았습니다.  
  
 **오류 ID:** BC30549  
  
### 이 오류를 해결하려면  
  
1.  특성 선언을 확인하고 `AttributeTargets.Module`또는`AttributeTargets.All`을 지정합니다.  
  
## 참고 항목  
 <xref:System.AttributeUsageAttribute>   
 <xref:System.AttributeTargets>