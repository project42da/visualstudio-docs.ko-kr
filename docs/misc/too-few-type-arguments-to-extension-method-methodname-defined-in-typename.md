---
title: "&#39;&lt;typename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;의 인수가 너무 적습니다. | Microsoft Docs"
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
  - "vbc36590"
  - "bc36590"
helpviewer_keywords: 
  - "BC36590"
ms.assetid: 8a9dd2d3-d8af-4ef5-8427-eb6e83d16230
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;의 인수가 너무 적습니다.
메서드 정의의 형식 매개 변수보다 적은 형식 인수로 제네릭 확장 메서드를 호출했습니다.  
  
 제네릭 메서드를 호출할 때 해당 메서드에서 정의한 각 형식 매개 변수에 대해 하나의 형식 인수를 제공해야 합니다.  
  
 **오류 ID:** BC36590  
  
### 이 오류를 해결하려면  
  
-   호출하는 확장 메서드에서 각 형식 매개 변수에 대해 하나씩 있도록 형식 인수 목록에 형식 인수를 추가합니다.  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)