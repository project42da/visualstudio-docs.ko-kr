---
title: 'CA2242: NaN에 대해 올바르게 테스트 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- TestForNaNCorrectly
- CA2242
helpviewer_keywords:
- CA2242
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a782c0b3f32c9733b47ded29852e006f8ba7c1aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2242-test-for-nan-correctly"></a>CA2242: NaN에 대해 정확하게 테스트하십시오.
|||  
|-|-|  
|TypeName|TestForNaNCorrectly|  
|CheckId|CA2242|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 에 대 한 값을 테스트 하는 식을 <xref:System.Single.NaN?displayProperty=fullName> 또는 <xref:System.Double.NaN?displayProperty=fullName>합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.Double.NaN?displayProperty=fullName>not a 번호를 나타내는, 산술 연산을 정의 되지 않습니다. 하면 결과입니다. 값 간의 일치 여부를 테스트 하는 모든 식 및 <xref:System.Double.NaN?displayProperty=fullName> 항상 반환 `false`합니다. 값을 다른 지 테스트 하는 모든 식 및 <xref:System.Double.NaN?displayProperty=fullName> 항상 반환 `true`합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하 고 정확 하 게 값을 나타내는지 여부를 결정 하려면 <xref:System.Double.NaN?displayProperty=fullName>를 사용 하 여 <xref:System.Single.IsNaN%2A?displayProperty=fullName> 또는 <xref:System.Double.IsNaN%2A?displayProperty=fullName> 값을 테스트 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 식에 대 한 값을 잘못 테스트 <xref:System.Double.NaN?displayProperty=fullName> 올바르게 사용 하는 식 및 <xref:System.Double.IsNaN%2A?displayProperty=fullName> 값을 테스트 합니다.  
  
 [!code-vb[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/VisualBasic/ca2242-test-for-nan-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/CSharp/ca2242-test-for-nan-correctly_1.cs)]