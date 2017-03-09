---
title: "&#39;&lt;methodname&gt;&#39; 메서드에 &#39;&lt;delegatename&gt;&#39; 대리자와 호환되는 서명이 없습니다. | Microsoft Docs"
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
  - "vbc31143"
  - "bc31143"
helpviewer_keywords: 
  - "BC31143"
ms.assetid: 88990637-7c92-467e-a3d3-db5498dc1dce
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;methodname&gt;&#39; 메서드에 &#39;&lt;delegatename&gt;&#39; 대리자와 호환되는 서명이 없습니다.
이 오류는 대리자와 메서드 간에 불가능한 변환이 필요한 경우 발생합니다. 오류의 원인은 매개 변수 간의 변환이거나, 메서드와 대리자가 함수일 때 반환 값의 변환일 수 있습니다.  
  
 다음 코드에서는 실패한 변환을 보여 줍니다. 대리자는 `FunDel`입니다.  
  
```vb#  
Delegate Function FunDel(ByVal i As Integer, ByVal d As Double) As Integer  
```  
  
 다음 함수는 이 오류를 발생시키는 방법 면에서 각각 `FunDel`과 다릅니다.  
  
```vb#  
Function ExampleMethod1(ByVal m As Integer, ByVal aDate As Date) As Integer End Function Function ExampleMethod2(ByVal m As Integer, ByVal aDouble As Double) As Date End Function  
```  
  
 다음 각 대입문은 오류를 발생시킵니다.  
  
```vb#  
Sub Main() ' The second parameters of FunDel and ExampleMethod1, Double and Date, ' are not compatible. 'Dim d1 As FunDel = AddressOf ExampleMethod1 ' The return types of FunDel and ExampleMethod2, Integer and Date, ' are not compatible. 'Dim d2 As FunDel = AddressOf ExampleMethod2 End Sub  
```  
  
 **오류 ID:** BC31143  
  
### 이 오류를 해결하려면  
  
-   해당 매개 변수 및 반환 형식\(있는 경우\)을 검사하여 호환되지 않는 쌍을 확인합니다.  
  
## 참고 항목  
 [Relaxed Delegate Conversion](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)   
 [빌드에 없음: 대리자 및 AddressOf 연산자](http://msdn.microsoft.com/ko-kr/7b2ed932-8598-4355-b2f7-5cedb23ee86f)