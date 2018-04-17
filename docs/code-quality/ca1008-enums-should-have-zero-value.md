---
title: 'CA1008: 열거형 값이 있어야 0 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1008
- EnumsShouldHaveZeroValue
helpviewer_keywords:
- CA1008
- EnumsShouldHaveZeroValue
ms.assetid: 3503a73c-360c-416d-8ee4-c2aa44365a05
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af0b742c42dae829c0e066babf77494f612e8908
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1008-enums-should-have-zero-value"></a>CA1008: 열거형에는 0 값이 있어야 합니다.
|||  
|-|-|  
|TypeName|EnumsShouldHaveZeroValue|  
|CheckId|CA1008|  
|범주|Microsoft.Design|  
|변경 수준|아님-추가 메시지가 표시 되는 경우는 **None** 비 플래그 열거형에는 값입니다. 주요-이름 바꾸기 또는 열거형 값을 제거 하는 메시지가 있습니다.|  
  
## <a name="cause"></a>원인  
 적용 되지 않은 열거형 <xref:System.FlagsAttribute?displayProperty=fullName> 0입니다; 또는 적용 된 열거형의 값을 가진 멤버를 정의 하지 않습니다 <xref:System.FlagsAttribute> 멤버 정의 합니다. 0 값이 있지만 해당 이름을 'None', 되었거나 열거형은 다중 값이 0 인 정의 멤버입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 다른 값 형식과 마찬가지로 초기화 되지 않은 열거형의 기본값은 0입니다. 플래그 특성 사용 열거형 열거형의 유효한 값이 되도록 0 값을 가진 멤버를 정의 해야 합니다. 해당 하는 경우 멤버의 이름을 '없음'입니다. 그렇지 않은 경우 가장 자주 사용 되는 멤버에 0을 할당 합니다. 참고, 기본적으로 선언에서 첫 번째 열거형 멤버의 값이 설정 되지 않은 경우 해당 값은 0입니다.  
  
 경우에 열거형은 <xref:System.FlagsAttribute> 적용 값이 0 인 멤버를 정의 합니다. 해당 이름이 열거에 없는 값이 설정 되어 있는 것을 나타내려면 ' None' 이어야 합니다. 다른 용도로 사용 하는 것에 대 한 값이 0 인 멤버를 사용 하 여 <xref:System.FlagsAttribute> 한다는 점에서 AND 및 또는 비트 연산자는 멤버와 함께 사용할 수 없습니다. 이 의미 하나만 해당 멤버 값이 0 할당 해야 합니다. 하 멤버가 여러 개 있는 경우 값이 0 나타날 플래그 특성을 사용 하는 열거형에 `Enum.ToString()` 은 0이 아닌 멤버에 대 한 잘못 된 결과 반환 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 열거형 플래그 특성 사용에 대 한이 규칙 위반 문제를 해결 하려면 0입니다; 값을 가진 멤버를 정의 합니다. 이 사소한 변경 합니다. 플래그 특성을 사용 하는 열거형 값이 0 인 멤버를 정의 '없음'이 멤버의 이름을 하 고 값이 0입니다; 다른 모든 멤버 삭제 주요 변경 내용입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 에 이전에 제공 된 플래그 특성을 사용 하는 열거형 이외에이 규칙에서는 경고를에서 표시 하지 마십시오.  
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙을 충족 하는 두 개의 열거형 및 열거형 `BadTraceOptions`는 규칙을 위반 하 합니다.  
  
 [!code-cpp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CPP/ca1008-enums-should-have-zero-value_1.cpp)]
 [!code-csharp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CSharp/ca1008-enums-should-have-zero-value_1.cs)]
 [!code-vb[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/VisualBasic/ca1008-enums-should-have-zero-value_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
 [CA1700: 열거형 값의 이름을 'Reserved'로 지정하지 마십시오.](../code-quality/ca1700-do-not-name-enum-values-reserved.md)  
  
 [CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마십시오.](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)  
  
 [CA1028: 열거형 저장소는 Int32여야 합니다.](../code-quality/ca1028-enum-storage-should-be-int32.md)  
  
 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Enum?displayProperty=fullName>