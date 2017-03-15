---
title: "&#39;Case&#39; 문에 지정한 범위가 잘못됨 | Microsoft Docs"
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
  - "vbc40052"
  - "bc40052"
helpviewer_keywords: 
  - "BC40052"
ms.assetid: a11d92f6-dc13-46a0-a8ca-5a962a0ed968
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Case&#39; 문에 지정한 범위가 잘못됨
`Case` 문에 대해 잘못된 범위를 지정했습니다.  
  
 동일한 식을 다양한 값과 비교하는 경우 `If...Then...Else` 문 대신 `Select...Case` 문을 사용할 수 있습니다.`If` 및 `ElseIf` 문은 각 문에서 다른 식을 계산할 수 있는 반면, `Select` 문은 단일 식을 한 번만 계산한 다음 모든 비교에 사용합니다. 각 `Case` 문에 둘 이상의 값, 값 범위 또는 값과 비교 연산자의 조합이 포함될 수 있습니다.  
  
 **오류 ID:** BC40052  
  
### 이 오류를 해결하려면  
  
-   모든 값을 포함하도록 범위를 수정하거나 `Case Else` 문을 사용하여 정의되지 않은 값을 catch합니다.  
  
## 참고 항목  
 [Select...Case Statement](/dotnet/visual-basic/language-reference/statements/select-case-statement)   
 [Decision Structures](/dotnet/visual-basic/programming-guide/language-features/control-flow/decision-structures)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)