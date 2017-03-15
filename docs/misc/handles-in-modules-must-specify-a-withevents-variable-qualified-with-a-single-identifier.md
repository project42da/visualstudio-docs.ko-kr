---
title: "모듈의 &#39;Handles&#39;는 단일 식별자로 한정된 &#39;WithEvents&#39; 변수를 지정해야 합니다. | Microsoft Docs"
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
  - "bc31418"
  - "vbc31418"
helpviewer_keywords: 
  - "BC31418"
ms.assetid: 7d866577-1e42-43f1-85d1-5d7eeba881b2
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 모듈의 &#39;Handles&#39;는 단일 식별자로 한정된 &#39;WithEvents&#39; 변수를 지정해야 합니다.
이벤트 처리기를 지정하려면 `Handles` 문이 `WithEvents` 키워드를 사용하여 선언된 개체 변수를 지정해야 합니다.  
  
 **오류 ID:** BC31418  
  
### 이 오류를 해결하려면  
  
-   `WithEvents` 한정자를 사용하여 `Handles` 문에서 사용할 변수를 선언합니다.  
  
## 참고 항목  
 [Handles](/dotnet/visual-basic/language-reference/statements/handles-clause)   
 [WithEvents](/dotnet/visual-basic/language-reference/modifiers/withevents)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)