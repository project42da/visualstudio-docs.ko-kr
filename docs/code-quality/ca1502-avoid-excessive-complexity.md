---
title: ": Ca1502 지나치게 복잡 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidExcessiveComplexity
- CA1502
helpviewer_keywords:
- CA1502
- AvoidExcessiveComplexity
ms.assetid: d735454b-2f8f-47ce-907d-f7a5a5391221
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3c45ca232b555af1441502586a38c80f43c41edc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1502-avoid-excessive-complexity"></a>CA1502: 지나치게 복잡하게 만들지 마십시오.
|||  
|-|-|  
|TypeName|AvoidExcessiveComplexity|  
|CheckId|CA1502|  
|범주|Microsoft.Maintainability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 메서드에 과도 한 순환 복잡성 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 *순환 복잡성* 수와 조건부 분기의 복잡성에 의해 결정 되는 메서드를 통해 선형 독립 경로의 수를 측정 합니다. 일반적으로 낮은 순환 복잡성 쉽게 이해, 테스트 및 유지 관리할 수 있는 메서드를 나타냅니다. 순환 복잡성 방법의 제어 흐름 그래프에서 계산 되 고 다음과 같이 지정 됩니다.  
  
 순환 복잡성 = 가장자리-노드의 수 + 1의 수  
  
 노드 논리 분기 지점을 나타내고는 지 위치 노드 사이 선을 나타냅니다.  
  
 순환 복잡성은 25 개 이상의 규칙 위반을 보고 합니다.  
  
 코드 메트릭에 대해 자세히 알아볼 수 있습니다 [측정 복잡성 및 관리 코드 유지 관리 용이성](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md),  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 순환 복잡성을 줄이기 위해 메서드를 리팩터링 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 복잡성을 쉽게 줄일 수 없습니다 및 메서드 이해, 테스트 및 유지 관리 하기 쉽습니다. 경우에이 규칙에서 경고를 표시 하지 않으려면 안전 합니다. 특히, 많이 포함 하는 메서드 `switch` (`Select` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 문에 제외 적합 합니다. 코드 베이스 개발 주기 또는 예기치 않게 변경 이전에 제공 된 코드에서의 런타임 동작에서 런타임에 얻는 유지 관리 코드의 이점을 저해할 위험 합니다.  
  
## <a name="how-cyclomatic-complexity-is-calculated"></a>순환 복잡성 계산 되는 방법  
 순환 복잡성은 다음에 1을 추가 하 여 계산 됩니다.  
  
-   분기 수 (예: `if`, `while`, 및 `do`)  
  
-   개수 `case` 의 문에서`switch`  
  
 다음 예에서는 다양 한 순환 복잡성을 갖는 메서드를 보여 줍니다.  
  
## <a name="example"></a>예제  
 **1의 순환 복잡성**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_1.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_1.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_1.cs)]  
  
## <a name="example"></a>예제  
 **2의 순환 복잡성**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_2.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_2.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_2.cs)]  
  
## <a name="example"></a>예제  
 **3의 순환 복잡성**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_3.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_3.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_3.cs)]  
  
## <a name="example"></a>예제  
 **8의 순환 복잡성**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_4.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_4.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_4.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1501: 상속성을 너무 많이 사용하지 마십시오.](../code-quality/ca1501-avoid-excessive-inheritance.md)  
  
## <a name="see-also"></a>참고 항목  
 [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)