---
title: "형식 매개 변수 &#39;&lt;typeparametername2&gt;&#39;에 대한 &#39;New&#39; 제약 조건을 만족하려면 형식 매개 변수 &#39;&lt;typeparametername1&gt;&#39;에 &#39;New&#39; 제약 조건 또는 &#39;Structure&#39; 제약 조건이 있어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32084"
  - "BC32084"
helpviewer_keywords: 
  - "BC32084"
ms.assetid: a7ff58d3-8c67-40e4-9fd8-92cc00524c22
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 매개 변수 &#39;&lt;typeparametername2&gt;&#39;에 대한 &#39;New&#39; 제약 조건을 만족하려면 형식 매개 변수 &#39;&lt;typeparametername1&gt;&#39;에 &#39;New&#39; 제약 조건 또는 &#39;Structure&#39; 제약 조건이 있어야 합니다.
문이 `New` 제약 조건을 충족하기 위해 제한되지 않은 형식 매개 변수를 전달하는 제네릭 형식을 생성합니다.  
  
 `New` 제약 조건은 해당 형식 매개 변수에 제공된 형식 인수에서 개체를 만드는 코드에 액세스할 수 있는, 매개 변수 없는 생성자를 노출해야 한다는 의미입니다. 모든 값 형식에는 매개 변수가 없는 생성자가 있지만 참조 형식은 그렇지 않습니다. 따라서 `Structure` 제약 조건은 `New` 제약 조건을 충족하지만 `Class` 제약 조건 또는 클래스나 인터페이스 이름은 그렇지 않습니다.  
  
 다음 문은 이 오류를 생성할 수 있습니다.  
  
```  
Public Class c1(Of t As New) End Class Public Class c2(Of u) Public testObject As New c1(Of u) End Class  
```  
  
 `c2` 클래스가 `c1`에서 개체를 만들 때 형식 매개 변수 `u`에서 형식 매개 변수 `t`의 `New` 제약 조건을 충족하지 않습니다.  
  
 **오류 ID:** BC32084  
  
### 이 오류를 해결하려면  
  
-   제네릭 형식으로 전달할 형식 매개 변수가 `Structure` 또는 `New` 제약 조건을 충족할 수 있는 경우 적절한 제약 조건을 해당 정의에 추가합니다.  
  
    ```  
    Public Class c2(Of u As Structure)  
    ```  
  
-   형식 매개 변수에서 `Structure` 또는 `New` 제약 조건을 충족할 수 없는 경우 제네릭 형식으로 전달하지 마세요. 다른 형식 매개 변수를 형식 인수로 전달해야 합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator)   
 [구조체\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/263ce115-ac36-4c05-8cb7-0e0eead5c6d0)   
 [클래스\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/0777c6e6-46bc-451b-ad70-57b49d4ef4f7)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)