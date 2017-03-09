---
title: "&#39;&lt;typename&gt;&#39;은 &#39;System.AttributeUsageAttribute&#39; 특성을 포함하지 않으므로 특성으로 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc31505"
  - "bc31505"
helpviewer_keywords: 
  - "BC31505"
ms.assetid: 7dd84c9d-6711-4dab-afc6-1fe4dee78051
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;은 &#39;System.AttributeUsageAttribute&#39; 특성을 포함하지 않으므로 특성으로 사용할 수 없습니다.
`System.AttributeUsageAttribute` 없이 선언된 특성을 사용하여 사용법을 정의하려고 했습니다.  
  
 **오류 ID:** BC31505  
  
### 이 오류를 해결하려면  
  
1.  사용자 지정 특성은 `AttributeUsageAttribute` 특성이 적용된 `System.Attribute`에서 파생된 클래스여야 합니다.  
  
## 참고 항목  
 <xref:System.AttributeUsageAttribute>   
 [빌드에 없음: Visual Basic의 사용자 지정 특성](http://msdn.microsoft.com/ko-kr/d72d8a5c-8f64-4614-b15b-cad66845d047)