---
title: "Option Strict On에서는 &#39;&lt;methodname&gt;&#39; 메서드와 &#39;&lt;delegatename&gt;&#39; 대리자 사이의 암시적 형식 변환에 축소 변환을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc36663"
  - "vbc36663"
helpviewer_keywords: 
  - "BC36663"
ms.assetid: fefc7ab5-b587-4ff9-a6bc-4c4e5d4b6b29
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 &#39;&lt;methodname&gt;&#39; 메서드와 &#39;&lt;delegatename&gt;&#39; 대리자 사이의 암시적 형식 변환에 축소 변환을 사용할 수 없습니다.
`Option Strict`이 설정되면 대리자에서 매개 변수의 데이터 형식과 함수 또는 해당 대리자 형식의 변수에 할당된 `Sub`의 해당 매개 변수 간에 축소 변환을 사용할 수 없습니다. 예를 들어 함수 대리자 `Del`에 형식 `Integer`의 매개 변수 한 개가 있고 함수 `Conversion1`, `Conversion2` 및 `Conversion3`에 다른 숫자 형식의 매개 변수 한 개가 있습니다.  
  
```vb#  
Delegate Function Del(ByVal p As Integer) As String Function Conversion1(ByVal n As Integer) As String Return "Valid" End Function Function Conversion2(ByVal n As Long) As String Return "Valid" End Function Function Conversion3(ByVal n As Short) As String Return "Not valid" End Function  
```  
  
 `Integer`에서 `Integer`로 그리고 `Long`으로의 확대 변환이 있으므로 다음과 같은 대입이 유효합니다.  
  
```vb#  
' Valid. Dim funDel1 As Del = AddressOf Conversion1 Dim funDel2 As Del = AddressOf Conversion2  
```  
  
 `Integer`에서 `Short`로 변환하는 것이 축소 변환입니다. 따라서 다음 대입은 올바르지 않습니다.  
  
```vb#  
' Not valid. Dim funDel3 As Del = AddressOf Conversion3  
```  
  
 오류 ID: BC36663  
  
### 이 오류를 해결하려면  
  
-   필요한 확대 관계가 존재하도록 대리자 또는 메서드에서 매개 변수의 데이터 형식을 변경합니다.  
  
## 참고 항목  
 [Relaxed Delegate Conversion](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)   
 [Delegates](/dotnet/visual-basic/programming-guide/language-features/delegates/delegates)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [빌드에 없음: 대리자 및 AddressOf 연산자](http://msdn.microsoft.com/ko-kr/7b2ed932-8598-4355-b2f7-5cedb23ee86f)