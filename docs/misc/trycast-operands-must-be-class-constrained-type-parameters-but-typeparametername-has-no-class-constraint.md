---
title: "&#39;TryCast&#39; 피연산자는 클래스 제약 조건이 있는 형식 매개 변수여야 하는데 &#39;&lt;typeparametername&gt;&#39;에는 클래스 제약 조건이 없습니다. | Microsoft Docs"
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
  - "BC30793"
  - "vbc30793"
helpviewer_keywords: 
  - "BC30793"
ms.assetid: a38a1da9-4413-4a69-a2ce-0b6d51c2c4ef
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;TryCast&#39; 피연산자는 클래스 제약 조건이 있는 형식 매개 변수여야 하는데 &#39;&lt;typeparametername&gt;&#39;에는 클래스 제약 조건이 없습니다.
[TryCast Operator](/dotnet/visual-basic/language-reference/operators/trycast-operator) 연산자가 참조 형식이 보장되지 않는 형식 매개 변수 피연산자와 함께 사용되었습니다.  
  
 `TryCast`는 클래스 또는 인터페이스와 같은 참조 형식에만 적용됩니다. 형식 매개 변수를 `TryCast`에 인수로 전달하는 경우 해당 형식 매개 변수를 참조 형식으로 제한해야 합니다. 형식 매개 변수의 제약 조건 목록에 다음 중 하나 이상을 포함하면 됩니다.  
  
-   하나 이상의 인터페이스 이름\(형식 인수에서 모두 구현해야 함\)  
  
-   최대 하나의 클래스 이름\(형식 인수가 상속해야 함\)  
  
-   [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator) 제약 조건\(형식 인수가 만드는 코드에서 액세스할 수 있는, 매개 변수 없는 생성자를 노출해야 하므로 클래스여야 함\)  
  
-   [클래스\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/0777c6e6-46bc-451b-ad70-57b49d4ef4f7) 제약 조건\(형식 인수가 참조 형식이어야 함\)  
  
 **오류 ID:** BC30793  
  
### 이 오류를 해결하려면  
  
-   이 형식 매개 변수를 `TryCast`에 전달해야 하는 경우 앞의 목록에 있는 하나 이상의 제약 조건으로 제한합니다.  
  
-   형식 매개 변수가 참조 형식만 사용하도록 요구할 수 없는 경우에는 `TryCast`와 함께 사용할 수 없습니다. 대신 [CType 함수](/dotnet/visual-basic/language-reference/functions/ctype-function)를 사용할 수 있습니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [Implicit and Explicit Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions)