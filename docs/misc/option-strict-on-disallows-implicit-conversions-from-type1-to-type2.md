---
title: "Option Strict On에서는 &#39;&lt;type1&gt;&#39;에서 &#39;&lt;type2&gt;&#39;로 암시적으로 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc30512"
  - "vbc30512"
helpviewer_keywords: 
  - "BC30512"
ms.assetid: b9756d48-05fa-4027-8a80-b4a0ef92099d
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 &#39;&lt;type1&gt;&#39;에서 &#39;&lt;type2&gt;&#39;로 암시적으로 변환할 수 없습니다.
형식 검사 스위치\([Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)\)가 `On`으로 설정되어 있는 상태에서 형식을 값을 포함하지 못할 수 있는 다른 형식으로 변환하려고 했습니다\(예: `Long`에서 `Integer`로\).  
  
 이 유형의 변환을 *축소 변환*이라고 하며 런타임에 실패할 수 있습니다. 이러한 이유로 `Option Strict On`에서는 암시적 축소 변환을 허용하지 않습니다.  
  
 **오류 ID:** BC30512  
  
### 이 오류를 해결하려면  
  
1.  `<type1>`에서 `<type2>`로 변환된 형식이 있는지 여부를 확인합니다. 둘 다 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 기본 형식이거나 둘 다 클래스의 인스턴스인 경우 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)의 표를 참조하여 일반적으로 이러한 결정을 할 수 있습니다.  
  
2.  `<type1>`에서 `<type2>`로의 축소 변환만 있는 경우 명시적 캐스팅을 사용해야 합니다. 변환에 실패하는 경우 [CType 함수](/dotnet/visual-basic/language-reference/functions/ctype-function) 및 [DirectCast Operator](/dotnet/visual-basic/language-reference/operators/directcast-operator) 키워드가 런타임 예외를 throw합니다. 변환에 실패하는 경우 [TryCast Operator](/dotnet/visual-basic/language-reference/operators/trycast-operator) 키워드는 참조 형식에만 적용되고 [Nothing](/dotnet/visual-basic/language-reference/nothing)을 반환합니다.  
  
3.  축소 변환이 있고 프로그램에서 런타임 오류를 허용할 수 있거나 런타임 오류가 가능하지 않다고 확신하는 경우 소스 코드의 시작 부분에서 `Option Strict Off`를 지정할 수 있습니다. 예기치 않은 결과 또는 프로그램의 조기 종료를 방지하려면 변환을 계속 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement) 블록으로 묶어야 합니다.  
  
4.  `<type1>`에서 `<type2>`로의 변환이 없는 경우 프로그램 논리를 다시 평가해야 합니다. 값을 `<type1>`의 예상한 값에 해당하는 `<type2>`에 할당할 수 있는 코드를 작성할 수도 있습니다.  
  
5.  `<type1>`에서 `<type2>`로 변환된 항목이 없고 형식 중 하나가 정의한 클래스 또는 구조체인 경우 해당 형식 또는 다른 형식에서 변환 연산자를 정의할 수도 있습니다. 자세한 내용은 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)을 참조하세요.  
  
6.  모든 경우 및 일반적인 지침으로 오류를 `Catch` 블록으로 트랩하여 효과적으로 처리할 수 없는 경우 축소 변환을 사용하지 않아야 합니다.  
  
## 참고 항목  
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [CType 함수](/dotnet/visual-basic/language-reference/functions/ctype-function)   
 [DirectCast Operator](/dotnet/visual-basic/language-reference/operators/directcast-operator)   
 [TryCast Operator](/dotnet/visual-basic/language-reference/operators/trycast-operator)   
 [Nothing](/dotnet/visual-basic/language-reference/nothing)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)