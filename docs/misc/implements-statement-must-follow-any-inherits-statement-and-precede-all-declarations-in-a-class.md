---
title: "&#39;Implements&#39; 문은 모든 &#39;Inherits&#39; 문 다음에 와야 하고 클래스의 모든 선언 앞에 와야 합니다. | Microsoft Docs"
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
  - "bc31053"
  - "vbc31053"
helpviewer_keywords: 
  - "BC31053"
ms.assetid: 8036a1a1-7e31-4c49-b74b-01601a548f3e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Implements&#39; 문은 모든 &#39;Inherits&#39; 문 다음에 와야 하고 클래스의 모든 선언 앞에 와야 합니다.
잘못된 위치에서 `Implements` 문을 발견했습니다.  
  
 **오류 ID:** BC31053  
  
### 이 오류를 해결하려면  
  
-   `Implements` 문을 `Inherits` 문 바로 뒤, 선언 앞에 배치합니다. 예:  
  
    ```  
    Class Derived Inherits Base Implements One Sub SubOne() Implements One.Method1 ' Add code to implement the method. End Sub End Class  
    ```  
  
## 참고 항목  
 [Interfaces](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)   
 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause)