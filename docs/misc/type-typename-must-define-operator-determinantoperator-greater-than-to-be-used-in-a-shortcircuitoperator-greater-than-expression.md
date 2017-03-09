---
title: "&#39;&lt;typename&gt;&#39; 형식은 &#39;&lt;shortcircuitoperator&gt;&#39; 식에서 사용할 &#39;&lt;determinantoperator&gt;&#39; 연산자를 정의해야 합니다. | Microsoft Docs"
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
  - "bc33035"
  - "vbc33035"
helpviewer_keywords: 
  - "BC33035"
ms.assetid: 50a0a39f-63cd-4100-aea9-91b5b6ab5bbf
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식은 &#39;&lt;shortcircuitoperator&gt;&#39; 식에서 사용할 &#39;&lt;determinantoperator&gt;&#39; 연산자를 정의해야 합니다.
[AndAlso Operator](/dotnet/visual-basic/language-reference/operators/andalso-operator) 또는 [OrElse Operator](/dotnet/visual-basic/language-reference/operators/orelse-operator)는 해당 클래스 또는 구조체에서 필요한 연산자를 정의하지 않을 경우 클래스 또는 구조체 형식의 피연산자를 사용합니다.  
  
 단락 연산자\(`AndAlso` 또는 `OrElse`\)를 직접 정의하지 않기 때문에 해당 논리 및 결정 연산자를 정의해야 합니다. 다음 표에서는 필요한 연산자를 보여 줍니다.  
  
|단락 연산자|논리 연산자|결정 연산자|  
|------------|------------|------------|  
|`AndAlso`|[And Operator](/dotnet/visual-basic/language-reference/operators/and-operator)|[IsFalse Operator](/dotnet/visual-basic/language-reference/operators/isfalse-operator)|  
|`OrElse`|[Or Operator](/dotnet/visual-basic/language-reference/operators/or-operator)|[IsTrue Operator](/dotnet/visual-basic/language-reference/operators/istrue-operator)|  
  
 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]는 이러한 논리 연산자와 결정 연산자를 사용하여 `AndAlso` 또는 `OrElse`에 대한 단락 논리를 생성합니다. 이 방법이 올바르게 수행되려면 피연산자와 `And` 또는 `Or` 정의의 반환 값 모두 포함하는 형식 즉, `And` 또는 `Or`를 정의 중인 구조체 또는 클래스 형식이어야 합니다.  
  
 **오류 ID:** BC33035  
  
### 이 오류를 해결하려면  
  
-   `AndAlso` 또는 `OrElse` 연산자의 피연산자 형식에 사용되는 클래스 또는 구조체에서 `And` 및 `IsFalse` 연산자 또는 `Or` 및 `IsTrue` 연산자를 정의합니다.`And` 또는 `Or`의 피연산자가 이를 정의하는 클래스 또는 구조체 형식인지 확인합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Logical and Bitwise Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators)