---
title: "&#39;&lt;attributename&gt;&#39;을 어셈블리에 두 번 이상 적용할 수 없습니다. | Microsoft Docs"
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
  - "bc31521"
  - "vbc31521"
helpviewer_keywords: 
  - "BC31521"
ms.assetid: 7312570f-8afb-4afe-992f-b6f7796f5f26
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;attributename&gt;&#39;을 어셈블리에 두 번 이상 적용할 수 없습니다.
지정된 특성은 특성에 한 번만 적용할 수 있습니다.  
  
 **오류 ID:** BC31521  
  
### 이 오류를 해결하려면  
  
1.  이 특성의 불필요한 적용을 제거합니다.  
  
2.  개발한 사용자 지정 특성을 사용하는 경우 `AttributeUsageAttribute`를 수정하고 `AllowMultiple` 속성을 `True`로 설정합니다.  
  
## 참고 항목  
 <xref:System.AttributeUsageAttribute>   
 <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=fullName>