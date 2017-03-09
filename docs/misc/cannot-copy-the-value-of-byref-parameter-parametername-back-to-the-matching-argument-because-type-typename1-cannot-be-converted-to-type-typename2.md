---
title: "&#39;&lt;typename1&gt;&#39; 형식은 &#39;&lt;typename2&gt;&#39; 형식으로 변환할 수 없으므로 &#39;ByRef&#39; 매개 변수 &#39;&lt;parametername&gt;&#39;의 값을 해당 인수에 다시 복사할 수 없습니다. | Microsoft Docs"
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
  - "vbc33037"
  - "BC33037"
helpviewer_keywords: 
  - "BC33037"
ms.assetid: 3ff137e2-e062-4e54-abf5-e902e2d18968
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename1&gt;&#39; 형식은 &#39;&lt;typename2&gt;&#39; 형식으로 변환할 수 없으므로 &#39;ByRef&#39; 매개 변수 &#39;&lt;parametername&gt;&#39;의 값을 해당 인수에 다시 복사할 수 없습니다.
프로시저가 호출하는 인수 형식으로 다시 변환할 수 없는 매개 변수 형식으로 선언되었습니다.  
  
 클래스 또는 구조체를 정의하는 경우 해당 클래스 또는 구조체 형식을 다른 형식으로 변환하는 변환 연산자를 하나 이상 정의할 수 있습니다. 다른 형식을 클래스 또는 구조체 형식으로 다시 변환하는 역방향 변환 연산자를 정의할 수도 있습니다. 프로시저 호출에서 클래스 또는 구조체 형식을 사용하는 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]은 이러한 변환 연산자를 사용하여 인수 형식을 해당 매개 변수의 형식으로 변환할 수 있습니다.  
  
 [ByRef](/dotnet/visual-basic/language-reference/modifiers/byref) 인수를 전달하는 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 참조를 전달하는 대신 프로시저의 지역 변수에 인수 값을 복사하는 경우도 있습니다. 이 경우 프로시저가 반환되면 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 지역 변수 값을 호출 코드의 인수에 다시 복사해야 합니다.  
  
 `ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다. 그러나 형식이 서로 다르면 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 양방향으로 변환해야 합니다. 형식 중 하나가 클래스 또는 구조체 형식인 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 둘 다 다른 형식으로 변환해야 합니다. 즉, 양방향으로 변환 연산자를 정의해야 합니다.  
  
 **오류 ID:** BC33037  
  
### 이 오류를 해결하려면  
  
-   가능한 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 변환할 필요가 없도록 프로시저 매개 변수와 동일한 형식의 호출 인수를 사용합니다.  
  
-   매개 변수 형식과 다른 인수 형식을 사용하여 프로시저를 호출해야 하지만 호출 인수에 값을 반환할 필요가 없는 경우 매개 변수를 `ByRef`가 아니라 [ByVal](/dotnet/visual-basic/language-reference/modifiers/byval)로 정의합니다.  
  
-   호출 인수에 값을 반환해야 하는 경우에는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 호출 인수 형식으로 다시 변환할 수 있도록 역방향 변환 연산자를 정의합니다.  
  
## 참고 항목  
 [Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/index)   
 [Procedure Parameters and Arguments](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments)   
 [Passing Arguments by Value and by Reference](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference)   
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)