---
title: "&#39;&lt;typename&gt;&#39;은 재정의되지 않은 &#39;MustOverride&#39; 메서드를 포함하므로 특성으로 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc31507"
  - "vbc31507"
helpviewer_keywords: 
  - "BC31507"
ms.assetid: 843643d3-3e81-4ce3-b4df-278882f3954d
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;은 재정의되지 않은 &#39;MustOverride&#39; 메서드를 포함하므로 특성으로 사용할 수 없습니다.
클래스와 `MustOverride` 메서드는 특성으로 사용할 수 없습니다.  
  
 특성 클래스의 `MustOverride` 멤버는 이러한 멤버를 재정의하는 파생된 클래스에서만 사용할 수 있습니다.  
  
 **오류 ID:** BC31507  
  
### 이 오류를 해결하려면  
  
1.  특성 클래스 멤버에서 `MustOverride` 한정자를 제거합니다.  
  
2.  파생 클래스의 `MustOverride` 멤버를 구현하고 해당 클래스를 특성으로 사용합니다.  
  
## 참고 항목  
 <xref:System.AttributeUsageAttribute>   
 [빌드에 없음: Visual Basic의 사용자 지정 특성](http://msdn.microsoft.com/ko-kr/d72d8a5c-8f64-4614-b15b-cad66845d047)