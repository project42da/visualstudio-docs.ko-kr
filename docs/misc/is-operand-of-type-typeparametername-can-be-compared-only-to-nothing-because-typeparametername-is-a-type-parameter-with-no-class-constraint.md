---
title: "&#39;&lt;typeparametername&gt;&#39;은 클래스 제약 조건이 없는 형식 매개 변수이므로 &#39;&lt;typeparametername&gt;&#39; 형식의 &#39;Is&#39; 피연산자는 &#39;Nothing&#39;과만 비교할 수 있습니다. | Microsoft Docs"
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
  - "vbc32052"
  - "bc32052"
helpviewer_keywords: 
  - "BC32052"
ms.assetid: 0bbf2249-eb0d-4b74-a555-8868c7ebe91d
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typeparametername&gt;&#39;은 클래스 제약 조건이 없는 형식 매개 변수이므로 &#39;&lt;typeparametername&gt;&#39; 형식의 &#39;Is&#39; 피연산자는 &#39;Nothing&#39;과만 비교할 수 있습니다.
[Class\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/0777c6e6-46bc-451b-ad70-57b49d4ef4f7) 키워드 또는 특정 클래스 이름을 해당 제약 조건 목록에 포함하지 않고 형식 매개 변수를 정의한 경우 형식 매개 변수는 [Is Operator](/dotnet/visual-basic/language-reference/operators/is-operator)에 대한 피연산자로 사용됩니다.  
  
 `Is`는 두 참조 형식을 비교하여 메모리에서 동일한 개체 인스턴스를 가리키는지 여부를 확인합니다. 다른 피연산자가 [Nothing](/dotnet/visual-basic/language-reference/nothing)이 아니면 참조 형식이 아닌 피연산자를 사용할 수 없습니다.  
  
 **오류 ID:** BC32052  
  
### 이 오류를 해결하려면  
  
-   이 형식 매개 변수에 제공된 형식 인수가 항상 참조 형식이 되도록 요구할 수 있는 경우, 형식 매개 변수에 대한 제약 조건 목록에 `Class` 키워드 또는 특정 클래스 이름을 추가합니다.  
  
-   이 형식 매개 변수에 제공된 형식 인수가 항상 참조 형식이도록 요구할 수 없는 경우 `Is` 식에서 제거합니다.`Is` 연산자를 사용하여 다른 참조 형식과 비교할 수 없습니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)   
 [Comparison Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators)