---
title: 'CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
helpviewer_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
dev_langs:
- VB
- CSharp
- CPP
ms.assetid: 1b6f626c-66bf-45b0-a3e2-7c41ee9ceda7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 12cc5f9fc58ac533d118b693587cf807f44b288f
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="ca2217-do-not-mark-enums-with-flagsattribute"></a>CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.

|||
|-|-|
|TypeName|DoNotMarkEnumsWithFlags|
|CheckId|CA2217|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

외부에서 볼 수는 열거형으로 표시 된 <xref:System.FlagsAttribute>, 하나 있거나 열거형에 정의 된 값의 거듭제곱 두 또는 다른 조합 하지 않은 값을 더 합니다.

## <a name="rule-description"></a>규칙 설명

열거형 있어야 <xref:System.FlagsAttribute> present 열거형에 정의 된 각 값은 2 개 또는 조합의 거듭제곱이 하는 경우에 값을 정의 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결 하는 방법

이 규칙 위반 문제를 해결 하려면 제거 <xref:System.FlagsAttribute> 열거형에서 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="example-that-should-not-have-the-attribute"></a>특성이 없는 예제

다음 예제에서는 열거형 `Color`, 3 값이 들어 있는입니다. 두 자리 또는 정의 된 값의 조합을의 거듭제곱 3이 않습니다. `Color` 열거형으로 표시 해서는 안 <xref:System.FlagsAttribute>합니다.

[!code-cpp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_1.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_1.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_1.vb)]

## <a name="example-that-should-have-the-attribute"></a>특성을 가져야 하는 예제

다음 예제에서는 열거형 `Days`, 표시로 대 한 요구 사항에 맞는 <xref:System.FlagsAttribute>합니다.

[!code-cpp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_2.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_2.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_2.vb)]

## <a name="related-rules"></a>관련된 규칙

[CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>참고자료

- <xref:System.FlagsAttribute?displayProperty=fullName>
