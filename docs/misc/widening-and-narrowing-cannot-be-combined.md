---
title: "&#39;Widening&#39;과 &#39;Narrowing&#39;은 함께 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc33001"
  - "vbc33001"
helpviewer_keywords: 
  - "BC33001"
ms.assetid: 1c576344-083c-45ad-bc71-0489bd3976be
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Widening&#39;과 &#39;Narrowing&#39;은 함께 사용할 수 없습니다.
[Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)이 [Widening](/dotnet/visual-basic/language-reference/modifiers/widening)과 [Narrowing](/dotnet/visual-basic/language-reference/modifiers/narrowing)를 둘 다 지정합니다.  
  
 변환 연산자를 정의할 때 `Widening` 또는 `Narrowing`로 선언해야 합니다. 이들은 함께 사용할 수 없는 특성이므로 둘 다 지정할 수는 없습니다.  
  
 **오류 ID:** BC33001  
  
### 이 오류를 해결하려면  
  
-   `Operator` 문에서 `Widening` 또는 `Narrowing` 키워드를 제거합니다. 둘 중 하나를 지정해야 합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)