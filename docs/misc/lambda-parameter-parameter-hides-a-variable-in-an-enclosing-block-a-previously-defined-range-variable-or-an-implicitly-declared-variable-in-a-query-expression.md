---
title: "람다 매개 변수 &#39;&lt;parameter&gt;&#39;가 바깥쪽 블록의 변수, 이전에 정의한 범위 변수 또는 쿼리 식에 암시적으로 선언한 변수를 숨깁니다. | Microsoft Docs"
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
  - "bc36641"
  - "vbc36641"
helpviewer_keywords: 
  - "BC36641"
ms.assetid: ee08c366-29d1-4abb-b14c-23ae2b9680e7
caps.latest.revision: 3
caps.handback.revision: 3
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 람다 매개 변수 &#39;&lt;parameter&gt;&#39;가 바깥쪽 블록의 변수, 이전에 정의한 범위 변수 또는 쿼리 식에 암시적으로 선언한 변수를 숨깁니다.
람다 식의 변수 이름이 동일한 범위 내에서 이전에 정의된 변수와 같은 이름을 가지고 있습니다. 이는 중첩된 람다 식에 대한 코드의 바깥쪽 블록에 있는 변수, LINQ 쿼리 내에서 이전에 정의된 범위 변수 또는 LINQ 쿼리에 대해 암시적으로 선언된 변수일 수 있습니다.  
  
 **오류 ID:** BC36641  
  
### 이 오류를 해결하려면  
  
-   람다 식의 모든 변수가 동일한 범위에 있는 기존 변수 이름과 중복되지 않는 고유한 이름을 가졌는지 확인합니다.  
  
## 참고 항목  
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)