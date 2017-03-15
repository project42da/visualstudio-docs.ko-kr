---
title: "Option Strict On에서는 각 람다 식 매개 변수의 형식을 유추할 수 없을 경우 해당 매개 변수를 &#39;As&#39; 절로 선언해야 합니다. | Microsoft Docs"
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
  - "bc36642"
  - "vbc36642"
helpviewer_keywords: 
  - "BC36642"
ms.assetid: 2aaa62b8-49c9-4ae8-b0f5-08e3f0b5ad10
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 각 람다 식 매개 변수의 형식을 유추할 수 없을 경우 해당 매개 변수를 &#39;As&#39; 절로 선언해야 합니다.
`Option Strict`가 On인 상태에서 `As` 절을 사용하지 않고 람다 식의 매개 변수를 선언했습니다.  
  
```  
' Not valid when Option Strict is on. ' Dim increment1 = Function (n) n + 1  
```  
  
 앞의 선언은 `n`의 형식을 유추할 수 있을 때 사용할 수 있습니다. 예를 들어 앞의 람다 식을 함수 대리자, `Del`에 할당하는 경우:  
  
```  
Delegate Function Del(ByVal p As Integer) As Integer  
```  
  
 이제 `n`의 형식을 `p` 매개 변수에서 유추할 수 있습니다.  
  
```  
Dim increment2 as Del = Function(n) n + 1  
```  
  
 **오류 ID:** BC36642  
  
### 이 오류를 해결하려면  
  
-   `As` 절을 매개 변수 선언에 추가합니다.  
  
    ```  
    Dim increment3 = Function (n As Integer) n + 1  
    ```  
  
## 참고 항목  
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)