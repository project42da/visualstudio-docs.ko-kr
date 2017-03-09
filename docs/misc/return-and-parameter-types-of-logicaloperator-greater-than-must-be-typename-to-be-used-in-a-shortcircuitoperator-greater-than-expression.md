---
title: "&#39;&lt;logicaloperator&gt;&#39;의 반환 및 매개 변수 형식은 &#39;&lt;shortcircuitoperator&gt;&#39; 식에 사용할 &#39;&lt;typename&gt;&#39;이어야 합니다. | Microsoft Docs"
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
  - "vbc33034"
  - "bc33034"
helpviewer_keywords: 
  - "BC33034"
ms.assetid: 94cd52dc-5d48-4673-b0b8-38a1954483c6
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;logicaloperator&gt;&#39;의 반환 및 매개 변수 형식은 &#39;&lt;shortcircuitoperator&gt;&#39; 식에 사용할 &#39;&lt;typename&gt;&#39;이어야 합니다.
`And` 연산자 또는 `Or` 연산자가 [AndAlso Operator](/dotnet/visual-basic/language-reference/operators/andalso-operator) 또는 [OrElse Operator](/dotnet/visual-basic/language-reference/operators/orelse-operator)에서 사용하기에 부적절한 매개 변수 또는 반환 형식으로 선언되었습니다.  
  
 단락 연산자\(`AndAlso` 또는 `OrElse`\)를 직접 정의하지 않기 때문에 해당 논리 및 결정 연산자를 정의해야 합니다. 다음 표에서는 필요한 연산자를 보여 줍니다.  
  
|단락 연산자|논리 연산자|결정 연산자|  
|------------|------------|------------|  
|`AndAlso`|[And Operator](/dotnet/visual-basic/language-reference/operators/and-operator)|[IsFalse Operator](/dotnet/visual-basic/language-reference/operators/isfalse-operator)|  
|`OrElse`|[Or Operator](/dotnet/visual-basic/language-reference/operators/or-operator)|[IsTrue Operator](/dotnet/visual-basic/language-reference/operators/istrue-operator)|  
  
 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]는 이러한 논리 연산자와 결정 연산자를 사용하여 `AndAlso` 또는 `OrElse`에 대한 단락 논리를 생성합니다. 이 방법이 올바르게 수행되려면 피연산자와 `And` 또는 `Or` 정의의 반환 값 모두 포함하는 형식 즉, `And` 또는 `Or`를 정의 중인 구조체 또는 클래스 형식이어야 합니다.  
  
 **오류 ID:** BC33034  
  
### 이 오류를 해결하려면  
  
-   연산자와 반환 값 형식을 모두 이 연산자를 정의하는 클래스 또는 구조체의 형식으로 변경합니다.  
  
     또는  
  
-   해당 단락 연산자\(`AndAlso` 또는 `OrElse`\)를 이 `And` 또는 `Or` 연산자를 정의하는 클래스 또는 구조체 형식의 피연산자와 함께 사용하지 마세요.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Logical and Bitwise Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators)