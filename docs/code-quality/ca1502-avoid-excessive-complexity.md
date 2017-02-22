---
title: "CA1502: 지나치게 복잡하게 만들지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AvoidExcessiveComplexity"
  - "CA1502"
helpviewer_keywords: 
  - "CA1502"
  - "AvoidExcessiveComplexity"
ms.assetid: d735454b-2f8f-47ce-907d-f7a5a5391221
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1502: 지나치게 복잡하게 만들지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidExcessiveComplexity|  
|CheckId|CA1502|  
|범주|Microsoft.Maintainability|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드가 과도한 순환 복잡성을 갖습니다.  
  
## 규칙 설명  
 *순환 복잡성\(cyclomatic complexity\)*은 메서드를 통과하는 선형 독립 경로의 수를 측정하며 조건부 분기의 수와 복잡성에 의해 결정됩니다.  낮은 순환 복잡성은 대개 쉽게 이해하고 테스트하고 유지 관리할 수 있는 메서드를 나타냅니다.  순환 복잡성은 메서드의 제어 흐름 그래프에서 계산되며 다음과 같이 지정됩니다.  
  
 순환 복잡성 \= 에지\(edge\) 수 \- 노드 수 \+ 1  
  
 여기서 노드는 논리 분기점을 나타내고 에지\(edge\)는 노드 사이의 선을 나타냅니다.  
  
 순환 복잡성이 25를 넘으면 규칙이 위반을 보고합니다.  
  
 코드 메트릭에 대한 자세한내용은 [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)를 참조하십시오.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드를 리팩터링하여 순환 복잡성을 줄입니다.  
  
## 경고를 표시하지 않는 경우  
 복잡성을 쉽게 줄일 수 없고 메서드가 이해하고 테스트하고 유지 관리하기 쉬우면 이 규칙에서 경고를 표시하지 않아도 안전합니다.  특히 `switch`\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 `Select`\) 문이 많이 포함된 메서드는 제외할 수 있습니다.  코드 리팩터링으로 유지 관리의 이점을 얻는 것보다는 개발 주기의 뒷부분에서 코드 베이스가 불안정하게 되거나 이전에 제공된 코드에서 런타임 동작이 예기치 않게 변경되지 않도록 하는 것이 더 중요합니다.  
  
## 순환 복잡성을 계산하는 방법  
 순환 복잡성은 다음 항목에 1을 더하여 계산됩니다.  
  
-   분기 수\(`if`, `while` 및 `do` 등\)  
  
-   `switch`에서 `case` 문의 수  
  
 다음 예제에서는 다양한 순환 복잡성이 포함된 메서드를 보여 줍니다.  
  
## 예제  
 **순환 복잡성 1**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_1.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_1.vb)]
 [!code-cs[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_1.cs)]  
  
## 예제  
 **순환 복잡성 2**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_2.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_2.vb)]
 [!code-cs[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_2.cs)]  
  
## 예제  
 **순환 복잡성 3**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_3.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_3.vb)]
 [!code-cs[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_3.cs)]  
  
## 예제  
 **순환 복잡성 8**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_4.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_4.vb)]
 [!code-cs[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_4.cs)]  
  
## 관련 규칙  
 [CA1501: 상속성을 너무 많이 사용하지 마십시오.](../code-quality/ca1501-avoid-excessive-inheritance.md)  
  
## 참고 항목  
 [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)