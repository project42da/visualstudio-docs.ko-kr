---
title: "&lt;variable&gt; 범위 변수가 바깥쪽 블록의 변수를 숨기거나 이전에 쿼리 식에 정의한 범위 변수를 숨깁니다. | Microsoft Docs"
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
  - "bc30978"
  - "vbc30978"
helpviewer_keywords: 
  - "BC30978"
ms.assetid: 806d94c1-653f-40c0-b1c4-95661c76a392
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;variable&gt; 범위 변수가 바깥쪽 블록의 변수를 숨기거나 이전에 쿼리 식에 정의한 범위 변수를 숨깁니다.
쿼리의 범위 변수가 동일한 범위 내에서 이전에 정의된 변수 또는 쿼리 내에서 이전에 정의된 범위 변수와 이름이 같습니다.  
  
 **오류 ID:** BC30978  
  
### 이 오류를 해결하려면  
  
-   쿼리의 모든 범위 변수가 동일한 범위에 있는 기존 변수 이름과 중복되지 않는 고유한 이름을 가졌는지 확인합니다.  
  
-   중복된 제어 변수 이름을 가진 중첩된 쿼리를 괄호로 묶어 각 범위 변수에 대한 범위를 구분합니다.  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)