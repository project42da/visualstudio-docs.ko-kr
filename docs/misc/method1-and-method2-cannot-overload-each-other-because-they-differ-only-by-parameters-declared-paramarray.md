---
title: "&#39;&lt;method1&gt;&#39;과 &#39;&lt;method2&gt;&#39;는 &#39;ParamArray&#39;로 선언된 매개 변수만 다르므로 서로 오버로드할 수 없습니다. | Microsoft Docs"
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
  - "bc30368"
  - "vbc30368"
helpviewer_keywords: 
  - "BC30368"
ms.assetid: 6111df0c-fc3e-40b2-b536-effbd132ef72
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;method1&gt;&#39;과 &#39;&lt;method2&gt;&#39;는 &#39;ParamArray&#39;로 선언된 매개 변수만 다르므로 서로 오버로드할 수 없습니다.
서로 다른 두 개의 메서드를 `ParamArray` 매개 변수에서만 오버로드하려고 했습니다. 컴파일러는 `ParamArray` 매개 변수를 사용하는 프로시저가 해당 매개 변수 배열에 전달되었다는 점에서 서로 다른 무한 개의 오버로드를 가진 것으로 간주합니다.  
  
 **오류 ID:** BC30368  
  
### 이 오류를 해결하려면  
  
-   메서드가 `ParamArray` 매개 변수 이외에 다른 차별점이 있는지 확인합니다.  
  
## 참고 항목  
 [Considerations in Overloading Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures)   
 [Parameter Arrays](/dotnet/visual-basic/programming-guide/language-features/procedures/parameter-arrays)