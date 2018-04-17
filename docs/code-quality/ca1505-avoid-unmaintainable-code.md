---
title: ': Ca1505 유지 관리할 수 없는 코드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4338b73aab38b1d63f4d4015c3a1fe1e1d292932
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: 유지 관리할 수 없는 코드는 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidUnmantainableCode|  
|CheckId|CA1505|  
|범주|Microsoft.Maintainability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 형식 또는 메서드에 낮은 유지 관리 인덱스 값이 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 유지 관리 인덱스는 다음 메트릭을 사용 하 여 계산 됩니다: 코드 줄, 프로그램 볼륨 및 순환 복잡성. 프로그램 볼륨에는 형식 또는 연산자와 피연산자의 코드에서의 수를 기반으로 하는 방법에 대 한 이해 하기 어려운 측정값입니다. 순환 복잡성은 구조적 형식 또는 메서드의 복잡성을 측정 합니다. 코드 메트릭에 대해 자세히 알아볼 수 있습니다 [측정 복잡성 및 관리 코드 유지 관리 용이성](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)합니다.  
  
 낮은 유지 관리 인덱스는 형식 또는 메서드가 유지 관리 하기 어렵고 및 적절 한 후 다시 디자인 하는 것을 나타냅니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 위반으로이 인해를 해결 하려면 형식 또는 메서드를 다시 디자인 작고 더욱 중점을 둔 형식 또는 메서드의으로 분할 하려고 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 형식 또는 메서드의 크더라도 아직 크기가 또는 형식 또는 메서드를 분할할 수 없는 경우이 경고를 제외 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [유지 관리 경고](../code-quality/maintainability-warnings.md)   
 [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)