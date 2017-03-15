---
title: "이 인수에서 &#39;&lt;typename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;의 형식 매개 변수에 대한 데이터 형식을 유추할 수 없습니다. | Microsoft Docs"
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
  - "bc36649"
  - "vbc36646"
  - "bc36646"
  - "vbc36649"
helpviewer_keywords: 
  - "BC36649"
  - "BC36646"
ms.assetid: 55274b01-6d78-4950-861e-07d9273ef76e
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 인수에서 &#39;&lt;typename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;의 형식 매개 변수에 대한 데이터 형식을 유추할 수 없습니다.
이 인수에서 '\<typename\>'에 정의된 확장 메서드 '\<methodname\>'의 형식 매개 변수에 대한 데이터 형식을 유추할 수 없습니다. 데이터 형식을 명시적으로 지정하면 이 오류를 해결할 수 있습니다.  
  
 제네릭 확장 메서드에 대한 호출을 평가할 때 형식 유추를 사용하여 형식 매개 변수의 데이터 형식을 확인하려고 했습니다. 그러나 이 메서드에서 형식 매개 변수에 대한 데이터 형식을 찾을 수 없어 오류가 보고되었습니다.  
  
> [!NOTE]
>  인수 지정이 옵션이 아닌 경우\(예: 쿼리 식의 쿼리 연산자\) 두 번째 문장 없이 오류 메시지가 나타납니다.  
  
 다음 코드에서는 오류를 보여 줍니다.  
  
```vb#  
Module Module1 Sub Main() Dim classInstance As ClassExample '' Not valid. 'classInstance.GenericExtensionMethod("Hello", "World") End Sub <System.Runtime.CompilerServices.Extension()> _ Sub GenericExtensionMethod(Of T)(ByVal classEx As ClassExample, _ ByVal x As String, ByVal y As _ InterfaceExample(Of T)) End Sub End Module Interface InterfaceExample(Of T) End Interface Class ClassExample End Class  
```  
  
 **오류 ID:** BC36649 및 BC36646  
  
### 이 오류를 해결하려면  
  
-   형식 유추를 사용하지 않고 형식 매개 변수에 대한 데이터 형식을 지정할 수 있습니다.  
  
## 참고 항목  
 [Relaxed Delegate Conversion](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)   
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Type Conversions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/type-conversions)