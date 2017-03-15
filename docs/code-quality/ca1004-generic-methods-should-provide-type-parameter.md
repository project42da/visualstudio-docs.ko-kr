---
title: "CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1004"
  - "GenericMethodsShouldProvideTypeParameter"
helpviewer_keywords: 
  - "CA1004"
  - "GenericMethodsShouldProvideTypeParameter"
ms.assetid: 38755f6a-fb45-4bf2-932e-0354ad826499
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 17
---
# CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|GenericMethodsShouldProvideTypeParameter|  
|CheckId|CA1004|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 제네릭 메서드의 매개 변수 시그니처에 메서드의 모든 형식 매개 변수에 해당하는 형식이 포함되어 있지 않습니다.  
  
## 규칙 설명  
 제네릭 메서드의 형식 인수가 형식 인수를 명시적으로 지정하는 대신 메서드로 전달된 인수의 형식에 따라 결정되는 방식을 유추라고 합니다.  유추를 사용하려면 제네릭 메서드의 매개 변수 시그니처에 메서드에 대한 형식 매개 변수와 같은 형식의 매개 변수가 포함되어야 합니다.  이 경우 형식 인수는 지정할 필요가 없습니다.  모든 형식 매개 변수에 대해 유추를 사용하는 경우 제네릭과 제네릭이 아닌 인스턴스 메서드를 호출하는 구문은 동일합니다.  따라서 제네릭 메서드를 사용하기가 간편해집니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 매개 변수 시그니처에 메서드의 각 형식 매개 변수와 동일한 형식이 포함되도록 디자인을 변경하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  제네릭을 이해하고 사용하기 쉬운 구문으로 제공하면 학습에 걸리는 시간이 줄어들고 더 많은 사용자가 새로운 라이브러리를 선택하게 됩니다.  
  
## 예제  
 다음 예제에서는 두 개의 제네릭 메서드를 호출하는 구문을 보여 줍니다.  `InferredTypeArgument`의 형식 인수는 유추되며 `NotInferredTypeArgument`의 형식 인수는 명시적으로 지정해야 합니다.  
  
 [!code-vb[FxCop.Design.Inference#1](../code-quality/codesnippet/VisualBasic/ca1004-generic-methods-should-provide-type-parameter_1.vb)]
 [!code-cs[FxCop.Design.Inference#1](../code-quality/codesnippet/CSharp/ca1004-generic-methods-should-provide-type-parameter_1.cs)]  
  
## 관련 규칙  
 [CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: 제네릭 목록을 노출하지 마십시오.](../Topic/CA1002:%20Do%20not%20expose%20generic%20lists.md)  
  
 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../Topic/CA1003:%20Use%20generic%20event%20handler%20instances.md)  
  
 [CA1007: 적합한 제네릭을 사용하십시오.](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## 참고 항목  
 [제네릭](/dotnet/csharp/programming-guide/generics/index)