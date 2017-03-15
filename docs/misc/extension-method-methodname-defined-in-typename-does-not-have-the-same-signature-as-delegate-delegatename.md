---
title: "&#39;&lt;typeName&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodName&gt;&#39;과 &#39;&lt;delegateName&gt;&#39; 대리자의 서명이 다릅니다. | Microsoft Docs"
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
  - "bc36580"
  - "vbc36580"
helpviewer_keywords: 
  - "BC36580"
ms.assetid: dc6b6a63-02b0-43d8-b6a7-c1cd397c6ee3
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typeName&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodName&gt;&#39;과 &#39;&lt;delegateName&gt;&#39; 대리자의 서명이 다릅니다.
사용하려는 확장 메서드 및 대리자의 서명이 서로 일치하지 않습니다.`Delegate` 문에서 대리자 클래스의 매개 변수 형식 및 반환 형식을 정의합니다. 매개 변수, 형식 및 반환 형식이 일치하는 프로시저는 이 대리자 형식의 인스턴스를 만드는 데 사용할 수 있습니다.`Example` 확장 메서드의 서명이 `Del` 대리자의 서명과 호환되지 않기 때문에 다음 예제에서 이 오류가 보고되었습니다.  
  
```vb#  
' Definition of the delegate, with two parameters. Delegate Sub Del(ByVal m As Integer, ByVal s As String)  
```  
  
```vb#  
' Definition of the extension method, with one parameter. <Extension()> _ Sub Example(ByVal s As String) ' Body of the Sub. End Sub  
```  
  
```vb#  
'' This assignment causes the error. ' Dim exampleDel As Del = AddressOf Example  
```  
  
 **오류 ID:** BC36580  
  
### 이 오류를 해결하려면  
  
-   대리자와 확장 메서드의 매개 변수 수가 같은지 확인합니다.  
  
-   매개 변수의 순서가 대리자와 확장 메서드에서 같은지 확인합니다.  
  
-   각 대리자 매개 변수의 데이터 형식을 해당 확장 메서드 매개 변수의 데이터 형식과 비교하여 서로 호환되는지 확인합니다.  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Delegate Statement](/dotnet/visual-basic/language-reference/statements/delegate-statement)   
 [Relaxed Delegate Conversion](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)