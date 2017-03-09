---
title: "&#39;&lt;genericprocedurename&gt;&#39;의 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;을 유추할 수 없습니다. | Microsoft Docs"
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
  - "vbc32050"
  - "bc32050"
helpviewer_keywords: 
  - "BC32050"
ms.assetid: e4a69ffb-0764-4e5a-8de1-40f881a3f4fb
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;genericprocedurename&gt;&#39;의 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;을 유추할 수 없습니다.
제네릭 프로시저가 형식 인수 목록을 제공하지 않고 호출되었으며 형식 인수 중 하나에 대한 형식 유추가 실패했습니다.  
  
 제네릭 프로시저를 호출하는 경우 일반적으로 프로시저에서 정의된 각 형식 매개 변수에 대한 형식 인수를 제공합니다. 그러나 형식 인수 목록을 완전히 생략하는 다른 방법도 있습니다. 이 작업을 수행할 때 컴파일러가 호출한 컨텍스트에서 각 형식 인수의 형식을 유추하려고 합니다. 자세한 내용은 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)의 "형식 유추"를 참조하세요.  
  
 형식 유추 실패는 형식 매개 변수와 호출 형식 간 순위의 불일치로 인해 발생할 수 있습니다. 다음 코드에서는 이를 보여 줍니다.  
  
```  
Public Sub displayLargest(Of t As IComparable)(ByVal arg() As t) ' Insert code to find and display the largest element of arg(). End Sub Public Sub callGenericSub() Dim testValue As Integer findLargest(testValue) Dim testMatrix(,) As Integer findLargest(testMatrix) End Sub  
```  
  
 위의 코드에서 `t` 형식 매개 변수는 1차원 배열에 대해 호출하는 반면 컴파일러가 호출에서 유추하는 형식 인수는 스칼라\(`testValue`\) 및 2차원 배열\(`testMatrix`\)이므로 `findLargest`에 대한 두 호출 모두 이 오류를 생성합니다.  
  
 **오류 ID:** BC32050  
  
### 이 오류를 해결하려면  
  
-   일반 인수의 형식은 형식 유추가 제네릭 프로시저에 대해 선언된 형식 매개 변수와 일치해야 합니다.  
  
     또는  
  
-   형식 유추가 필요하지 않도록 전체 형식 인수 목록이 있는 제네릭 프로시저를 호출합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)