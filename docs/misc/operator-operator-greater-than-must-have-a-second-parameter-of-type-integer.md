---
title: "&#39;&lt;operator&gt;&#39; 연산자의 두 번째 매개 변수 형식은 &#39;Integer&#39;여야 합니다. | Microsoft Docs"
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
  - "BC33041"
  - "vbc33041"
helpviewer_keywords: 
  - "BC33041"
ms.assetid: 5cd56f6d-2f0f-49de-a8e6-59bdb57bdb1d
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;operator&gt;&#39; 연산자의 두 번째 매개 변수 형식은 &#39;Integer&#39;여야 합니다.
비트 시프트 연산자가 `Integer`가 아닌 형식의 두 번째 매개 변수를 사용하여 선언되었습니다.  
  
 식에서 오른쪽 시프트\(`>>`\) 또는 왼쪽 시프트\(`<<`\) 연산자를 사용하는 경우 두 번째 피연산자에서 시프트 횟수를 지정합니다. 이 피연산자의 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]을 통해 `Integer`로 확대되는 데이터 형식을 제공할 수 있습니다. 그러나 두 번째 피연산자의 정의는 엄격하게 `Integer`입니다. 해당 클래스 또는 구조체에서 비트 시프트 연산자를 사용하는 클래스 또는 구조체를 정의하는 경우 정의에서 두 번째 피연산자에 대해 `Integer`를 지정해야 합니다.  
  
 **오류 ID:** BC33041  
  
### 이 오류를 해결하려면  
  
-   `Integer` 값을 반환하도록 비트 시프트 연산자의 정의를 변경합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Bit Shift Operators](/dotnet/visual-basic/language-reference/operators/bit-shift-operators)