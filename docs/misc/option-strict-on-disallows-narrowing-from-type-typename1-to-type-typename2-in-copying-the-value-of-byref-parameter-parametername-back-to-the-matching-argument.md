---
title: "Option Strict On에서는  ByRef 매개 변수 ‘&lt;parametername&gt;&#39;의 값을 해당 인수에 다시 복사하는 동안 &#39;&lt;typename1&gt;&#39; 형식에서 &#39;&lt;typename2&gt;&#39; 형식으로 축소 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc32029"
  - "vbc32029"
helpviewer_keywords: 
  - "BC32029"
ms.assetid: fc9ae5d2-b506-47cf-a50c-116fda5ed206
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는  ByRef 매개 변수 ‘&lt;parametername&gt;&#39;의 값을 해당 인수에 다시 복사하는 동안 &#39;&lt;typename1&gt;&#39; 형식에서 &#39;&lt;typename2&gt;&#39; 형식으로 축소 변환할 수 없습니다.
프로시저 호출은 인수의 선언한 형식으로 확대되는 데이터 형식으로 `ByRef` 인수를 제공하며 `Option Strict`는 `On`입니다. 인수가 프로시저로 전달될 때는 확대 변환을 사용할 수 있지만 프로시저에서 호출 코드의 가변 인수 내용을 수정하는 경우 역방향으로 축소 변환됩니다.`Option Strict On`에는 축소 변환을 사용할 수 없습니다.  
  
 **오류 ID:** BC32029  
  
### 이 오류를 해결하려면  
  
-   프로시저를 호출 시 선언된 형식과 같은 데이터 형식으로 각 `ByRef` 인수를 제공하거나 `Option Strict Off`로 설정 변경합니다.  
  
## 참고 항목  
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Passing Arguments by Value and by Reference](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [Implicit and Explicit Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions)