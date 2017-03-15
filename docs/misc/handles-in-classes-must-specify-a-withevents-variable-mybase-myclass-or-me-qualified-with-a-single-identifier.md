---
title: "클래스의 &#39;Handles&#39;는 단일 식별자로 한정된 &#39;WithEvents&#39; 변수, &#39;MyBase&#39;, &#39;MyClass&#39; 또는 &#39;Me&#39;를 지정해야 합니다. | Microsoft Docs"
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
  - "bc31412"
  - "vbc31412"
helpviewer_keywords: 
  - "BC31412"
ms.assetid: acbefc38-448a-4afa-90c2-77389415d618
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 클래스의 &#39;Handles&#39;는 단일 식별자로 한정된 &#39;WithEvents&#39; 변수, &#39;MyBase&#39;, &#39;MyClass&#39; 또는 &#39;Me&#39;를 지정해야 합니다.
이벤트 처리기를 지정하려면 `Handles` 문이 `WithEvents` 키워드를 사용하여 선언된 개체 변수를 지정하거나 `MyBase` 키워드로 한정된 멤버를 지정해야 합니다.  
  
 **오류 ID:** BC31412  
  
### 이 오류를 해결하려면  
  
1.  `WithEvents` 한정자를 사용하여 `Handles` 문에서 사용할 변수를 선언합니다.  
  
2.  기본 클래스의 현재 클래스에 대한 이벤트의 이름을 지정합니다.  
  
## 참고 항목  
 [Handles](/dotnet/visual-basic/language-reference/statements/handles-clause)   
 [WithEvents](/dotnet/visual-basic/language-reference/modifiers/withevents)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)