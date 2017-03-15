---
title: "동일한 형식으로 변환할 수 없으므로 이 인수에서 &#39;typename&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;의 형식 매개 변수에 대한 데이터 형식을 유추할 수 없습니다. | Microsoft Docs"
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
  - "vbc36658"
  - "bc36661"
  - "vbc36661"
  - "bc36658"
helpviewer_keywords: 
  - "BC36661"
  - "BC36658"
ms.assetid: 0bff97fd-cbe9-4433-8192-6498c6fb5d04
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 동일한 형식으로 변환할 수 없으므로 이 인수에서 &#39;typename&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;의 형식 매개 변수에 대한 데이터 형식을 유추할 수 없습니다.
동일한 형식으로 변환할 수 없으므로 이 인수에서 'typename'에 정의된 확장 메서드 '\<methodname\>'의 형식 매개 변수에 대한 데이터 형식을 유추할 수 없습니다. 데이터 형식을 명시적으로 지정하면 이 오류를 해결할 수 있습니다.  
  
 제네릭 확장 메서드에 대한 호출을 평가할 때 형식 유추를 사용하여 형식 매개 변수의 데이터 형식을 확인하려고 했습니다. 컴파일러에서 모든 인수의 제약 조건을 충족하는 데이터 형식을 찾을 수 없습니다. 따라서 이 오류가 보고되었습니다.  
  
> [!NOTE]
>  인수 지정이 옵션이 아닌 경우\(예: 쿼리 식의 쿼리 연산자\) 두 번째 문장 없이 오류 메시지가 나타납니다.  
  
 다음 코드에서는  오류를 보여 줍니다.  
  
```vb#  
Option Strict Off Module Module3 Sub Main() Dim c1 As New Class1 '' Not valid. Integer and Date do not convert to the same type. 'c1.targetMethod(19, #3/4/2007#) End Sub <System.Runtime.CompilerServices.Extension()> _ Sub targetMethod(Of T)(ByVal p0 As Class1, ByVal p1 As T, ByVal p2 As T) End Sub Class Class1 End Class End Module  
```  
  
 **오류 ID:** BC36661 및 BC36658  
  
### 이 오류를 해결하려면  
  
-   다음 코드와 같이 하나 이상의 인수를 호환되는 형식으로 명시적으로 변환할 수 있습니다.  
  
    ```  
    c1.targetMethod(19, #3/4/2007#.ToOADate)  
    ```  
  
-   다음 코드와 같이 인수가 변환하는 형식 매개 변수에 대한 데이터 형식을 지정할 수 있습니다.  
  
    ```  
    c1.targetMethod(Of String)(19, #3/4/2007#)  
    ```  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Relaxed Delegate Conversion](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Type Conversion Functions](/dotnet/visual-basic/language-reference/functions/type-conversion-functions)   
 [Implicit and Explicit Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions)   
 [Type Conversions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/type-conversions)