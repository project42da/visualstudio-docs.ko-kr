---
title: "Option Strict On에서는 람다 식과 &#39;&lt;delegatename&gt;&#39; 대리자 사이의 암시적 형식 변환에 축소 변환을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc36662"
  - "vbc36662"
helpviewer_keywords: 
  - "BC36662"
ms.assetid: 4504497b-56ba-4631-ad7b-59975f7fee04
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 람다 식과 &#39;&lt;delegatename&gt;&#39; 대리자 사이의 암시적 형식 변환에 축소 변환을 사용할 수 없습니다.
`Option Strict`이 설정되면 대리자에서 매개 변수의 데이터 형식과 해당 대리자 형식의 변수에 할당된 람다 식의 해당 매개 변수 간에 축소 변환을 사용할 수 없습니다. 예를 들어 다음 코드에서 `Del` 대리자에는 `Integer` 형식의 매개 변수 한 개가 있습니다.  
  
```vb#  
Delegate Function Del(ByVal p As Integer) As String  
```  
  
 따라서 `Del` 형식의 변수에 할당된 람다 식의 해당 매개 변수는 `Integer` 또는 `Integer`에서의 확대 변환이 있는 임의 데이터 형식일 수 있습니다.  
  
```vb#  
' Valid. Dim example1 As Del = Function(n As Integer) "Valid" Dim example2 As Del = Function(n As Long) "Valid" ' Not valid. Dim example3 As Del = Function(n As Short) "Not Valid"  
```  
  
 **오류 ID:** BC36662  
  
### 이 오류를 해결하려면  
  
-   필요한 확대 관계가 존재하도록 대리자 또는 람다 식에서 매개 변수의 데이터 형식을 변경합니다.  
  
-   람다 식에서 매개 변수 데이터 형식을 지정하지 마세요. 형식은 대리자의 해당 매개 변수에서 유추됩니다.  
  
    ```vb#  
    Dim example4 As Del = Function(n) "Valid"  
    ```  
  
## 참고 항목  
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)   
 [Delegates](/dotnet/visual-basic/programming-guide/language-features/delegates/delegates)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [Relaxed Delegate Conversion](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)