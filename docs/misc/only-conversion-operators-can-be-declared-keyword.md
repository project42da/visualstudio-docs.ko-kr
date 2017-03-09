---
title: "변환 연산자만 &#39;&lt;keyword&gt;&#39;로 선언할 수 있습니다. | Microsoft Docs"
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
  - "bc33019"
  - "vbc33019"
helpviewer_keywords: 
  - "BC33019"
ms.assetid: 946266fe-a909-41b1-aad4-f85dc8050b88
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 변환 연산자만 &#39;&lt;keyword&gt;&#39;로 선언할 수 있습니다.
연산자가 변환 연산자가 아닌 경우 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)에서 [Widening](/dotnet/visual-basic/language-reference/modifiers/widening) 또는 [Narrowing](/dotnet/visual-basic/language-reference/modifiers/narrowing)를 지정합니다.  
  
 모든 연산자는 [Public](/dotnet/visual-basic/language-reference/modifiers/public)과 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)로 선언되어야 합니다. 그러나 변환 연산자만 [Widening](/dotnet/visual-basic/language-reference/modifiers/widening) 또는 [Narrowing](/dotnet/visual-basic/language-reference/modifiers/narrowing)으로 선언될 수 있습니다\(둘 다 함께는 불가능\).  
  
 연산자 정의는 선택적으로 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads) 및 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows) 키워드를 포함할 수 있습니다.[Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)에 다른 모든 키워드는 허용되지 않습니다.  
  
 **오류 ID:** BC33019  
  
### 이 오류를 해결하려면  
  
1.  연산자 정의에서 `Widening` 또는 `Narrowing` 키워드를 제거합니다. 형식 변환이 일어나지 않기 때문에 이들은 적용되지 않습니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Type Conversions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/type-conversions)