---
title: "&#39;&lt;attributename&gt;&#39; 특성을 어셈블리에 적용할 수 없습니다. | Microsoft Docs"
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
  - "bc30548"
  - "vbc30548"
helpviewer_keywords: 
  - "BC30548"
ms.assetid: bc36f094-626a-4907-b80b-f195155fa5db
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;attributename&gt;&#39; 특성을 어셈블리에 적용할 수 없습니다.
`AttributeUsageAttribute`가 `AttributeTargets.Assembly`를 지정하지 않는 어셈블리에 특성을 적용하려고 했습니다. 특성을 선언할 때 어셈블리에 적용 가능하도록 정의되지 않았습니다.  
  
 **오류 ID:** BC30548  
  
### 이 오류를 해결하려면  
  
1.  특성 선언을 확인하고 `AttributeTargets.Assembly` 또는 `AttributeTargets.All`을 지정합니다.  
  
## 참고 항목  
 <xref:System.AttributeUsageAttribute>   
 <xref:System.AttributeTargets>