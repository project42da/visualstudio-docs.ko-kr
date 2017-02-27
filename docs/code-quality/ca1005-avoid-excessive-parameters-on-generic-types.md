---
title: "CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AvoidExcessiveParametersOnGenericTypes"
  - "CA1005"
helpviewer_keywords: 
  - "AvoidExcessiveParametersOnGenericTypes"
  - "CA1005"
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 18
---
# CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidExcessiveParametersOnGenericTypes|  
|CheckId|CA1005|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 제네릭 형식에 세 개 이상의 형식 매개 변수가 있습니다.  
  
## 규칙 설명  
 제네릭 형식에 포함된 형식 매개 변수가 많을수록 각 형식 매개 변수가 무엇을 나타내는지를 파악하거나 기억하기가 더 어렵습니다.  보통은 `List<T>`에서처럼 하나의 형식 매개 변수를 사용하고 특정한 경우에는 `Dictionary<TKey, TValue>`에서처럼 두 개의 형식 매개 변수를 사용하는 것이 좋습니다.  형식 매개 변수가 세 개 이상이면 대부분의 사용자가 사용하기에 너무 어렵습니다\(예를 들어, C\#의 경우 `TooManyTypeParameters<T, K, V>` 또는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `TooManyTypeParameters(Of T, K, V)`\).  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 디자인을 변경하여 세 개 이상의 형식 매개 변수를 사용하지 않도록 합니다.  
  
## 경고를 표시하지 않는 경우  
 디자인에 반드시 세 개 이상의 형식 매개 변수가 필요한 경우가 아니라면 경고를 표시하십시오.  제네릭을 이해하고 사용하기 쉬운 구문으로 제공하면 학습에 걸리는 시간이 줄어들고 더 많은 사용자가 새로운 라이브러리를 선택하게 됩니다.  
  
## 관련 규칙  
 [CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: 제네릭 목록을 노출하지 마십시오.](../Topic/CA1002:%20Do%20not%20expose%20generic%20lists.md)  
  
 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../Topic/CA1003:%20Use%20generic%20event%20handler%20instances.md)  
  
 [CA1007: 적합한 제네릭을 사용하십시오.](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## 참고 항목  
 [제네릭](/dotnet/csharp/programming-guide/generics/index)