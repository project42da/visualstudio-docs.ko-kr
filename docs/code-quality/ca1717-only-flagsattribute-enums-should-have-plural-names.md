---
title: 'CA1717: FlagsAttribute 열거형에만 복수형 이름을 사용해야 합니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1717
- OnlyFlagsEnumsShouldHavePluralNames
helpviewer_keywords:
- OnlyFlagsEnumsShouldHavePluralNames
- CA1717
ms.assetid: a6855d8b-d78a-42c1-834e-61c31f5572ed
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eddcdd47a79b925bf6601c25cf1343eacfa60aa0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717: FlagsAttribute 열거형에만 복수형 이름을 사용해야 합니다.
|||
|-|-|
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|
|CheckId|CA1717|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 외부에서 볼 수는 열거형의 이름을 복수 단어 끝나고 열거형으로 표시 되지 않은 <xref:System.FlagsAttribute?displayProperty=fullName> 특성입니다.

## <a name="rule-description"></a>규칙 설명
 명명 규칙에 따라 열거형에는 복수형 이름의 있음을 나타내도록 열거형의 값을 둘 이상 동시에 지정할 수 있습니다. <xref:System.FlagsAttribute> 열거형에 대 한 비트 연산 수 있도록 하는 비트 필드로 열거형을 처리 해야 함을 컴파일러에 지시 합니다.

 한 번에 열거형의 값 중 하나를 지정할 수만 열거형의 이름 단수형 단어로 이어야 합니다. 예를 들어 해당 주의 일을 정의 하는 열거형 수 사용 하려는 응용 프로그램에서 여러 날짜를 지정할 수 있습니다. 이 열거형 있어야는 <xref:System.FlagsAttribute> '일' 호출 될 수 없습니다. 하루를 지정할 수 있는 유사한 열거형에는 특성이 없으며 수 'Day'를 호출 합니다.

 명명 규칙은 공통 된 모양을 라이브러리에 대 한 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리를 익히는 데 필요한 라이브러리를 관리 되는 코드를 개발에 대 한 전문 지식이 있는 사용자가 개발 하는 신뢰성이 향상 하는 시간과 줄어듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 열거형의 이름을 단 수 단어 만들거나 추가 <xref:System.FlagsAttribute>합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이름이 단수형 단어로 끝나는 경우 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="related-rules"></a>관련된 규칙
 [CA1714: 플래그 열거형에는 복수형 이름을 사용해야 합니다.](../code-quality/ca1714-flags-enums-should-have-plural-names.md)

 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>참고 항목
 <xref:System.FlagsAttribute?displayProperty=fullName> [Enum 디자인](/dotnet/standard/design-guidelines/enum)