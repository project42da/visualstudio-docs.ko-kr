---
title: "람다 식에는 &#39;ByRef&#39; 매개 변수 &#39;&lt;parametername&gt;&#39;을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc36639"
  - "vbc36639"
helpviewer_keywords: 
  - "BC36639"
ms.assetid: 5913f9b6-2929-4c05-8dd1-00b10fcd5a83
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 람다 식에는 &#39;ByRef&#39; 매개 변수 &#39;&lt;parametername&gt;&#39;을 사용할 수 없습니다.
`Sub` 또는 함수에서 선언된 람다 식이 해당 `Sub` 또는 함수의 `ByRef` 매개 변수를 사용할 수 없습니다. 예를 들어 다음 코드는 `ByRef` 매개 변수 `n`이 람다 식에 사용되기 때문에 이 오류가 발생합니다.  
  
```  
'' Not valid.   
'Sub ExampleSub(ByRef n As Integer)  
  
'    Dim lambda = Function(p As Integer) p + n  
  
'End Sub  
```  
  
 **오류 ID:** BC36639  
  
### 이 오류를 해결하려면  
  
-   다음 코드와 같이 `ByRef` 매개 변수를 지역 변수에 할당하고 람다 식에서 지역 변수를 사용합니다.  
  
    ```  
    Sub ExampleSub(ByRef n As Integer)  
  
        Dim temp = n  
        Dim lambda = Function(p As Integer) p + temp  
  
    End Sub  
    ```  
  
## 참고 항목  
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)