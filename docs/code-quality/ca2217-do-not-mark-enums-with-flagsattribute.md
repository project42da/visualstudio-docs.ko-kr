---
title: 'CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
helpviewer_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
ms.assetid: 1b6f626c-66bf-45b0-a3e2-7c41ee9ceda7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1aaa080aaa238f15cbcedefd9302d23758948d77
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2217-do-not-mark-enums-with-flagsattribute"></a>CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.
|||
|-|-|
|TypeName|DoNotMarkEnumsWithFlags|
|CheckId|CA2217|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 외부에서 볼 수는 열거형으로 표시 된 <xref:System.FlagsAttribute> 하나 있거나 열거형에 정의 된 값의 거듭제곱 두 또는 다른 조합 하지 않은 값을 더 합니다.

## <a name="rule-description"></a>규칙 설명
 열거형 있어야 <xref:System.FlagsAttribute> 열거형에 정의 된 각 값은 2의 거듭제곱 또는 정의 된 값의 조합 하는 경우에 표시 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 제거 <xref:System.FlagsAttribute> 열거형에서 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 열거형을 색 값 3을 포함 하는 2의 거듭제곱 아니고 정의 된 값의 조합을 보여 줍니다. Color 열거형으로 표시 되어야 합니다는 <xref:System.FlagsAttribute>합니다.

 [!code-cpp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_1.cpp)]
 [!code-csharp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_1.cs)]
 [!code-vb[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_1.vb)]

## <a name="example"></a>예제
 다음 예제에서는 열거형 일 전 부터는 표시는 System.FlagsAttribute로에 대 한 요구 사항에 맞는 보여 줍니다.

 [!code-cpp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_2.cpp)]
 [!code-csharp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_2.cs)]
 [!code-vb[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_2.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>참고 항목
 <xref:System.FlagsAttribute?displayProperty=fullName>