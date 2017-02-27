---
title: "CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DoNotNestGenericTypesInMemberSignatures"
  - "CA1006"
helpviewer_keywords: 
  - "CA1006"
  - "DoNotNestGenericTypesInMemberSignatures"
ms.assetid: dfc867bc-f4af-45d7-b071-db04a248f9fc
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 17
---
# CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotNestGenericTypesInMemberSignatures|  
|CheckId|CA1006|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 멤버에 중첩된 형식 인수가 포함된 시그너처가 있습니다.  
  
## 규칙 설명  
 중첩된 형식 인수는 제네릭 형식의 인수입니다.  시그너처에 중첩된 형식 인수가 포함되어 있는 멤버를 호출하려면 제네릭 형식 하나를 인스턴스화하고 이 형식을 두 번째 제네릭 형식의 생성자에 전달해야 합니다.  이 경우 복잡한 프로시저와 구문이 필요하므로 이 방법을 피해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 디자인을 변경하여 중첩된 형식 인수를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  제네릭을 이해하고 사용하기 쉬운 구문으로 제공하면 학습에 걸리는 시간이 줄어들고 더 많은 사용자가 새로운 라이브러리를 선택하게 됩니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 메서드와 위반 메서드를 호출하는 데 필요한 구문을 보여 줍니다.  
  
 [!code-vb[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/VisualBasic/ca1006-do-not-nest-generic-types-in-member-signatures_1.vb)]
 [!code-cs[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/CSharp/ca1006-do-not-nest-generic-types-in-member-signatures_1.cs)]  
  
## 관련 규칙  
 [CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: 제네릭 목록을 노출하지 마십시오.](../Topic/CA1002:%20Do%20not%20expose%20generic%20lists.md)  
  
 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../Topic/CA1003:%20Use%20generic%20event%20handler%20instances.md)  
  
 [CA1007: 적합한 제네릭을 사용하십시오.](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## 참고 항목  
 [제네릭](/dotnet/csharp/programming-guide/generics/index)