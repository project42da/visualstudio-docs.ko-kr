---
title: "이 인수에서 &#39;&lt;methodname&gt;&#39; 메서드에 있는 형식 매개 변수의 데이터 형식을 유추할 수 없습니다. | Microsoft Docs"
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
  - "vbc36648"
  - "bc36645"
  - "bc36648"
  - "vbc36645"
helpviewer_keywords: 
  - "BC36648"
  - "BC36645"
ms.assetid: cc8c67bb-6cbb-4d7c-ba26-fe1d38908434
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 인수에서 &#39;&lt;methodname&gt;&#39; 메서드에 있는 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.
이 인수에서 '\<methodname\>' 메서드에 있는 형식 매개 변수의 데이터 형식을 유추할 수 없습니다. 데이터 형식을 명시적으로 지정하면 이 오류를 해결할 수 있습니다.  
  
 제네릭 프로시저에 대한 호출을 계산할 때 데이터 형식이나 형식 매개 변수의 형식을 결정하는 데 형식 유추를 사용하려고 했습니다. 그러나 이 메서드에서 형식 매개 변수에 대한 데이터 형식을 찾을 수 없어 오류가 보고되었습니다.  
  
> [!NOTE]
>  인수 지정이 옵션이 아닌 경우\(예: 쿼리 식의 쿼리 연산자\) 두 번째 문장 없이 오류 메시지가 나타납니다.  
  
 예를 들어 다음 코드에서는 오류를 보여 줍니다.  
  
```vb#  
Module Module1 Sub Main() '' Not valid. 'GenericMethod("Hello", "World") End Sub Sub GenericMethod(Of T)(ByVal x As String, ByVal y As _ InterfaceExample(Of T)) End Sub End Module Interface InterfaceExample(Of T) End Interface  
```  
  
 **오류 ID:** BC36648 및 BC36645  
  
### 이 오류를 해결하려면  
  
-   형식 유추를 사용하지 않고 형식 매개 변수에 대한 데이터 형식을 지정할 수 있습니다.  
  
## 참고 항목  
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Type Conversions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/type-conversions)