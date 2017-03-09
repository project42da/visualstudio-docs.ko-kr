---
title: "이진 &#39;If&#39; 연산자의 첫 번째 및 두 번째 피연산자에 대해 공용 형식을 유추할 수 없습니다. | Microsoft Docs"
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
  - "vbc33110"
  - "bc33110"
helpviewer_keywords: 
  - "BC33110"
ms.assetid: f46873aa-f6cd-4cc9-9e8e-e668bddf0980
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이진 &#39;If&#39; 연산자의 첫 번째 및 두 번째 피연산자에 대해 공용 형식을 유추할 수 없습니다.
이진 'If' 연산자의 첫 번째 및 두 번째 피연산자에 대한 공용 형식을 유추할 수 없습니다. 두 인수 간에 확대 변환이 필요합니다.  
  
 이진 `If` 연산자를 사용하려면 두 인수 간의 확대 변환이 있어야 합니다. 예를 들어 `Integer`와 `String` 사이에 어느 쪽으로도 확대 변환이 없기 때문에 다음 코드에서 이 오류가 발생합니다.  
  
```vb#  
Dim first? As Integer  
Dim second As String = "First is Nothing"  
'' Not valid.  
' Console.WriteLine(If(first, second))  
```  
  
 **오류 ID:** BC33110  
  
### 이 오류를 해결하려면  
  
-   코드에서 가능한 경우 피연산자 중 하나에 대해 명시적 변환을 제공합니다.  
  
    ```  
    Console.WriteLine(If(first, CInt(second)))   
    ```  
  
-   다른 조건부 생성을 사용하여 코드를 다시 작성합니다.  
  
    ```  
    If first IsNot Nothing Then  
        Console.WriteLine(first)  
    Else  
        Console.WriteLine(second)  
    End If  
    ```  
  
## 참고 항목  
 [If Operator](/dotnet/visual-basic/language-reference/operators/if-operator)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [If...Then...Else Statement](/dotnet/visual-basic/language-reference/statements/if-then-else-statement)