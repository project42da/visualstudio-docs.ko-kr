---
title: "짝이 되는 &#39;&lt;operatorsymbol1&gt;&#39; 연산자가 &#39;&lt;operatorsymbol2&gt;&#39;에 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc33033"
  - "vbc33033"
helpviewer_keywords: 
  - "BC33033"
ms.assetid: d2805e4f-08a8-4760-9539-565f51b88d13
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 짝이 되는 &#39;&lt;operatorsymbol1&gt;&#39; 연산자가 &#39;&lt;operatorsymbol2&gt;&#39;에 필요합니다.
짝이 되는 연산자가 정의되지 않았을 때 연산자가 정의되었습니다.  
  
 다음 연산자는 짝이 되는 쌍으로 정의해야 합니다.  
  
-   `=` 및 `<>`  
  
-   `>` 및 `<`  
  
-   `>=` 및 `<=`  
  
-   `IsTrue` 및 `IsFalse`  
  
 클래스 또는 구조체에서 이러한 연산자를 정의하는 경우 동일한 클래스 또는 구조체에서 짝이 되는 연산자도 정의해야 합니다.  
  
 짝이 되는 연산자를 명시적으로 사용하지 않는 경우에도 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 사용해야 할 수도 있습니다. 예를 들어 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)에서 카운터 변수로 사용하는 클래스 또는 구조체를 정의하는 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에 `+` 연산자뿐 아니라 `>=` 및 `<=` 연산자가 둘 다 필요합니다.  
  
 **오류 ID:** BC33033  
  
### 이 오류를 해결하려면  
  
-   동일한 클래스 또는 구조체에서 짝이 되는 연산자를 정의합니다.[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 예측하지 못한 상황에 사용될 수 있으므로 신중하게 정의합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Operators and Expressions](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/index)