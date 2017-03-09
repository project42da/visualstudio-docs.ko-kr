---
title: "&#39;ReadOnly&#39; 변수는 생성자 내부의 람다 식에서 할당 대상일 수 없습니다. | Microsoft Docs"
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
  - "bc36602"
  - "vbc36602"
helpviewer_keywords: 
  - "BC36602"
ms.assetid: f96f8c79-86df-4727-bc6d-f0844da21395
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReadOnly&#39; 변수는 생성자 내부의 람다 식에서 할당 대상일 수 없습니다.
람다 식에서 `ReadOnly` 변수를 참조했으며 이는 허용되지 않습니다. 다음 코드는 `ReadOnly` 변수 `m`를 `ByRef` 매개 변수에 대한 인수로 전송하여 이 오류를 발생시킵니다.  
  
```vb#  
Class Class1 ReadOnly m As Integer Sub New() ' The use of m triggers the error. Dim f = Function() Test(m) End Sub Function Test(ByRef n As Integer) As String End Function End Class  
```  
  
 **오류 ID:** BC36602  
  
### 이 오류를 해결하려면  
  
-   가능한 경우 다음 코드와 같이 함수 `Test`의 `n` 매개 변수를 `ByVal` 매개 변수로 변경합니다.  
  
    ```vb#  
    Class Class1Fix1 ReadOnly m As Integer Sub New() Dim f = Function() Test(m) End Sub Function Test(ByVal n As Integer) As String End Function End Class  
    ```  
  
### 이 오류를 해결하려면  
  
-   다음 코드와 같이 `ReadOnly` 변수 `m`을 생성자의 지역 변수에 할당하고 `m` 대신 이 지역 변수를 사용합니다.  
  
    ```vb#  
    Class Class1Fix2 ReadOnly m As Integer Sub New() Dim temp = m Dim f = Function() Test(temp) End Sub Function Test(ByRef n As Integer) As String End Function End Class  
    ```  
  
## 참고 항목  
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)   
 [ReadOnly](/dotnet/visual-basic/language-reference/modifiers/readonly)   
 [빌드에 없음: 생성자 및 소멸자 사용](http://msdn.microsoft.com/ko-kr/548eebe1-86c4-4377-b2f5-447cb8be3d90)