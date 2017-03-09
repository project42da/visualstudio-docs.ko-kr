---
title: "&#39;Sub New&#39;는 이벤트를 처리할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30497"
  - "bc30497"
helpviewer_keywords: 
  - "BC30497"
ms.assetid: b8a546c4-914e-49de-b553-9fc0f41424ed
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Sub New&#39;는 이벤트를 처리할 수 없습니다.
`Sub New`와 `Handles`를 결합하려고 했는데 이는 유효하지 않습니다. 프로시저 선언의 끝에서 `Handles` 키워드를 사용하여 `WithEvents` 키워드로 선언된 개체 변수에 의해 발생된 이벤트를 처리합니다.  
  
 **오류 ID:** BC30497  
  
### 이 오류를 해결하려면  
  
1.  `New`를 이 컨텍스트에서 사용하지 마세요.  
  
## 참고 항목  
 [Handles](/dotnet/visual-basic/language-reference/statements/handles-clause)   
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [WithEvents](/dotnet/visual-basic/language-reference/modifiers/withevents)