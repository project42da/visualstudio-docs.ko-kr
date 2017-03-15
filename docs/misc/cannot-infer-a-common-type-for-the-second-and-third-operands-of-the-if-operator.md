---
title: "&#39;If&#39; 연산자의 두 번째 및 세 번째 피연산자에 대한 공용 형식을 유추할 수 없습니다. | Microsoft Docs"
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
  - "vbc33106"
  - "bc33106"
helpviewer_keywords: 
  - "BC33106"
ms.assetid: 793eed88-a9f9-43e3-b657-c16795ecbbcc
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;If&#39; 연산자의 두 번째 및 세 번째 피연산자에 대한 공용 형식을 유추할 수 없습니다.
'If' 연산자의 두 번째 및 세 번째 피연산자에 대한 공용 형식을 유추할 수 없습니다. 두 인수 간에 확대 변환이 필요합니다.  
  
 세 개의 인수를 사용하여 `If` 연산자를 호출하는 경우 두 번째와 세 번째 인수 사이에 확대 변환이 있어야 합니다. 예를 들어 `Integer`와 `String` 사이에 어느 쪽으로도 확대 변환이 없기 때문에 다음 코드에서 이 오류가 발생합니다.  
  
```vb#  
Dim divisor = 3  
' Not valid.  
' Console.WriteLine(If(divisor <> 0, number \ divisor, "Division by zero"))  
```  
  
 **오류 ID:** BC33106  
  
### 이 오류를 해결하려면  
  
-   코드에서 가능한 경우 피연산자 중 하나에 대해 명시적 변환을 제공합니다.  
  
-   `If...Then...Else` 문 등의 다른 조건 생성을 사용합니다.  
  
## 참고 항목  
 [If Operator](/dotnet/visual-basic/language-reference/operators/if-operator)   
 [If...Then...Else Statement](/dotnet/visual-basic/language-reference/statements/if-then-else-statement)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)