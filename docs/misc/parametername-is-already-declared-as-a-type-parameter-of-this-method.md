---
title: "&#39;&lt;parametername&gt;&#39;이 이미 이 메서드의 형식 매개 변수로 선언되어 있습니다. | Microsoft Docs"
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
  - "bc32089"
  - "vbc32089"
helpviewer_keywords: 
  - "BC32089"
ms.assetid: 5e440b4b-f62b-4ff5-9148-2372d4752bf6
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;parametername&gt;&#39;이 이미 이 메서드의 형식 매개 변수로 선언되어 있습니다.
제네릭 프로시저는 기본 매개 변수 또는 이름이 같은 지역 변수를 형식 매개 변수로 정의합니다.  
  
 제네릭 프로시저의 모든 형식 매개 변수를 포함하여 프로시저의 모든 매개 변수는 다른 모든 매개 변수와 구별되는 고유한 이름이 있어야 합니다. 프로시저 매개 변수는 지역 변수로 사용되므로 프로시저에서 선언한 지역 변수도 모든 매개 변수 및 형식 매개 변수와 구별되는 고유한 이름이 있어야 합니다.  
  
 **오류 ID:** BC32089  
  
### 이 오류를 해결하려면  
  
-   기본 매개 변수 또는 지역 변수의 이름을 변경합니다.  
  
## 참고 항목  
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Parameter List](/dotnet/visual-basic/language-reference/statements/parameter-list)