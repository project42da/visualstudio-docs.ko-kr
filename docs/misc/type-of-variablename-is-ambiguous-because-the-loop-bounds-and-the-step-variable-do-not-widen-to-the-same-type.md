---
title: "루프 범위와 단계 변수가 같은 형식으로 확대되지 않으므로 &#39;&lt;variablename&gt;&#39; 형식이 모호합니다. | Microsoft Docs"
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
  - "vbc30983"
  - "bc30983"
helpviewer_keywords: 
  - "BC30983"
ms.assetid: 6b97153c-dee3-4429-b92a-2e5a212c864b
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 루프 범위와 단계 변수가 같은 형식으로 확대되지 않으므로 &#39;&lt;variablename&gt;&#39; 형식이 모호합니다.
다음 조건이 true이기 때문에 컴파일러가 루프 제어 변수의 데이터 형식을 유추할 수 없는 `For...Next` 루프가 코드에 포함되어 있습니다.  
  
-   `As` 절을 사용하여 루프 제어 변수의 데이터 형식을 지정하지 않았습니다.  
  
-   루프 범위와 단계 변수에 두 개 이상의 데이터 형식이 포함되어 있습니다.  
  
-   데이터 형식 간에 둘 이상의 가능한 변환이 있습니다.  
  
-   후보 중에 가장 적합한 형식이 없으므로 루프 제어 변수의 형식 선택이 모호합니다.  
  
 예를 들어 다음 루프에는 `Integer` 형식의 루프 범위 하나와 `UInteger` 형식의 루프 범위 하나가 있습니다.  
  
```vb#  
Dim m As Integer = 1 Dim n As UInteger = 10 ' Not valid. ' For i = m To n ' Loop processing. ' Next  
```  
  
 `Integer` 및 `UInteger` 간의 가능한 변환과 `UInteger` 및 `Integer` 간의 가능한 변환이 있지만 둘 다 축소 변환이므로 가장 적합한 선택은 아닙니다.  
  
 다음 예제에서는 `Double` 형식의 세 번째 변수가 추가됩니다.`Integer` 및 `UInteger` 둘 다에 `Double`로의 표준 확대 변환이 있으므로 `Double`로의 변환이 가장 적합한 선택입니다. 형식 유추에서 루프 제어 변수 `i`에 `Double` 데이터 형식을 할당합니다.  
  
```vb#  
Dim stepVar As Double = 1 ' Valid. For i = m To n Step stepVar ' Loop processing. Next  
```  
  
 **오류 ID:** BC30983  
  
### 이 오류를 해결하려면  
  
-   변수 중 하나를 다른 변수에 확대 변환이 있는 형식으로 명시적으로 변환합니다. 예:  
  
    ```  
    For i = m To CLng(n)  
    ```  
  
-   `As` 절을 사용하여 제어 변수의 형식을 지정합니다.  
  
    ```  
    For i As Double = m To n   
    ```  
  
## 참고 항목  
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)   
 [Implicit and Explicit Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions)   
 [Local Type Inference](/dotnet/visual-basic/programming-guide/language-features/variables/local-type-inference)   
 [Option Infer Statement](/dotnet/visual-basic/language-reference/statements/option-infer-statement)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)