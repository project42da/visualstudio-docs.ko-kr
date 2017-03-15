---
title: "&#39;&lt;typename&gt;&#39;은 &#39;System.Attribute&#39;에서 상속하지 않으므로 특성으로 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc31504"
  - "bc31504"
helpviewer_keywords: 
  - "BC31504"
ms.assetid: 37517623-5099-4db9-a461-f2f5daa4957b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;은 &#39;System.Attribute&#39;에서 상속하지 않으므로 특성으로 사용할 수 없습니다.
`System.Attribute`에서 파생되지 않은 클래스를 사용하려고 했습니다.  
  
 **오류 ID:** BC31504  
  
### 이 오류를 해결하려면  
  
1.  클래스의 첫 번째 코드 줄에 `Imports` 문을 추가하여 사용자 지정 특성을 `System.Attribute`에서 파생되는 클래스로 정의합니다.  
  
## 참고 항목  
 <xref:System.AttributeUsageAttribute>   
 [빌드에 없음: Visual Basic의 사용자 지정 특성](http://msdn.microsoft.com/ko-kr/d72d8a5c-8f64-4614-b15b-cad66845d047)