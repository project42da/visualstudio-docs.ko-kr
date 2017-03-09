---
title: "동일한 초기화 목록 내의 람다 식 정의에는 무명 형식 속성 &#39;&lt;propertyname&gt;&#39;을 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc36549"
  - "bc36549"
helpviewer_keywords: 
  - "BC36549"
ms.assetid: 6d04692a-957a-41ce-a19c-fcb06a186d1a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 동일한 초기화 목록 내의 람다 식 정의에는 무명 형식 속성 &#39;&lt;propertyname&gt;&#39;을 사용할 수 없습니다.
무명 형식의 초기화 목록에 정의된 속성은 동일한 목록의 람다 식 정의에 사용할 수 없습니다. 예를 들어 다음 코드에서 `Num` 속성은 `LambdaFun`의 정의에 포함될 수 없습니다.  
  
```vb#  
' Not valid.  
'Dim anon = New With {.Num = 4, .LambdaFun = Function() .Num > 0}  
```  
  
 **오류 ID:** BC36549  
  
### 이 오류를 해결하려면  
  
1.  무명 형식을 두 부분으로 분할하는 것이 좋습니다.  
  
    ```vb#  
    Dim anon1 = New With {.Num = 4}  
    Dim anon2 = New With {.LambdaFun = Function() anon1.Num > 0}  
    ' - or -  
    Dim anon3 = New With {.lambdaFun = Function(n As Integer) n > 0}  
    Console.WriteLine((anon2.LambdaFun)())  
    Console.WriteLine(anon3.lambdaFun(anon1.Num))  
    anon1.Num = -5  
    Console.WriteLine((anon2.LambdaFun)())  
    Console.WriteLine(anon3.lambdaFun(anon1.Num))  
    ```  
  
     `anon1.Num`을 `Key` 속성으로 선언하면 해당 값을 변경할 수 없습니다.  
  
2.  대신, 일반 함수 문을 사용하여 무명 형식 속성에 액세스해야 합니다.  
  
    ```vb#  
    Function testNum(ByVal n As Integer) As Boolean  
        Return n > 0  
    End Function  
    Console.WriteLine(testNum(anon1.Num))  
    ```  
  
3.  마찬가지로, 무명 형식 외부에 정의된 람다 함수를 사용할 수 있습니다.  
  
    ```vb#  
    Dim lambdaFun1 = Function() anon1.Num > 0  
    Dim lambdaFun2 = Function(n As Integer) n > 0  
    ```  
  
## 참고 항목  
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)   
 [Anonymous Types](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types)