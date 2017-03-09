---
title: "변환 연산자를 &#39;Widening&#39; 또는 &#39;Narrowing&#39;으로 선언해야 합니다. | Microsoft Docs"
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
  - "vbc33017"
  - "bc33017"
helpviewer_keywords: 
  - "BC33017"
ms.assetid: 5972d955-ce1d-4348-a021-167eecb3a507
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 변환 연산자를 &#39;Widening&#39; 또는 &#39;Narrowing&#39;으로 선언해야 합니다.
[Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)가 [Widening](/dotnet/visual-basic/language-reference/modifiers/widening) 또는 [Narrowing](/dotnet/visual-basic/language-reference/modifiers/narrowing)를 지정하지 않습니다.  
  
 변환 연산자를 정의할 때 `Widening` 또는 `Narrowing`로 선언해야 합니다. 이들은 함께 사용할 수 없는 특성이므로 둘 다 지정할 수는 없습니다.  
  
 **오류 ID:** BC33017  
  
### 이 오류를 해결하려면  
  
-   변환 연산자가 `Widening`이 되어야 하는지 아니면 `Narrowing`이 되어야 하는지 여부를 결정한 다음 `Operator` 문에 적절한 키워드를 포함합니다. 둘 중 하나를 지정해야 합니다.  
  
## 참고 항목  
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)