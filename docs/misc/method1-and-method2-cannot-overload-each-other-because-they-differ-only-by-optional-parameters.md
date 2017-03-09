---
title: "&#39;&lt;method1&gt;&#39;과 &#39;&lt;method2&gt;&#39;는 선택적 매개 변수만 다르므로 서로 오버로드할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30300"
  - "bc30300"
helpviewer_keywords: 
  - "BC30300"
ms.assetid: adb44ceb-57a0-4123-8fd8-7eb83c3f601f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;method1&gt;&#39;과 &#39;&lt;method2&gt;&#39;는 선택적 매개 변수만 다르므로 서로 오버로드할 수 없습니다.
선택적 매개 변수에서만 첫 번째 메서드와 차이가 나는 다른 메서드를 사용하여 메서드를 오버로드하려고 했습니다. 선택적 매개 변수가 있는 메서드는 두 개의 오버로드된 메서드와 같다고 할 수 있는데 하나는 선택적 매개 변수를 사용하는 메서드이고 다른 하나는 사용하지 않는 메서드입니다. 그러므로 이중 하나에 해당하는 인수 목록을 사용하여 메서드를 오버로드할 수 없습니다.  
  
 **오류 ID:** BC30300  
  
### 이 오류를 해결하려면  
  
-   메서드가 선택적 매개 변수 이외에 다른 차별점이 있는지 확인합니다.  
  
## 참고 항목  
 [Procedure Overloading](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)   
 [Considerations in Overloading Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures)