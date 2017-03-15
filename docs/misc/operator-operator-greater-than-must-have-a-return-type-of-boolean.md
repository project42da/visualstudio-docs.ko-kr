---
title: "&#39;&lt;operator&gt;&#39; 연산자의 반환 형식은 Boolean이어야 합니다. | Microsoft Docs"
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
  - "vbc33023"
  - "bc33023"
helpviewer_keywords: 
  - "BC33023"
ms.assetid: 18e066f4-d71e-4e38-b0bc-8af9145f6015
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;operator&gt;&#39; 연산자의 반환 형식은 Boolean이어야 합니다.
비교 연산자나 논리 연산자는 [Boolean Data Type](/dotnet/visual-basic/language-reference/data-types/boolean-data-type) 이외의 반환 형식으로 선언됩니다.  
  
 비교 연산자의 결과\(`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `IsFalse`, `IsTrue`, `Like`, `TypeOf`\)는 `True` 또는 `False`만 가능합니다. 자세한 내용은 [Comparison Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators)을 참조하세요.  
  
 논리 연산자\(`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`\)는 부울 값의 도메인 내에서 작동합니다. 자세한 내용은 [Logical and Bitwise Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators)을 참조하세요.  
  
 **오류 ID:** BC33023  
  
### 이 오류를 해결하려면  
  
-   이 비교 연산자나 논리 연산자의 반환 형식을 `Boolean`으로 바꿉니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)