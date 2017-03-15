---
title: "&#39;If&#39; 피연산자는 명명된 인수일 수 없습니다. | Microsoft Docs"
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
  - "bc33105"
  - "vbc33105"
helpviewer_keywords: 
  - "BC33105"
ms.assetid: 596baeb6-a44f-4d92-beb7-06624b60c00d
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;If&#39; 피연산자는 명명된 인수일 수 없습니다.
`If` 연산자의 피연산자에서 명명된 인수를 사용할 수 없습니다. 다음 예제는 이 오류를 생성합니다.  
  
```  
Dim i As Integer Dim result As String ' Not valid. ' result = (If(i > 0, TruePart:="positive", FalsePart:="not positive")  
```  
  
 이는 `IIf` 함수와 다르며 다음 코드와 같이 명명된 인수를 허용합니다.  
  
```  
' Valid. IIf(i > 0, TruePart:="positive", FalsePart:="not positive")  
```  
  
 **오류 ID:** BC33105  
  
### 이 오류를 해결하려면  
  
-   다음 코드와 같이 피연산자에서 이름 할당을 제거합니다.  
  
    ```  
    result = If(i > 0, "positive", "not positive")  
    ```  
  
## 참고 항목  
 [If Operator](/dotnet/visual-basic/language-reference/operators/if-operator)   
 [Passing Arguments by Position and by Name](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name)