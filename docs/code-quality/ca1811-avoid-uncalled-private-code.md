---
title: 'CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidUncalledPrivateCode
- CA1811
helpviewer_keywords:
- CA1811
- AvoidUncalledPrivateCode
ms.assetid: aadbba74-7821-475f-8980-34d17c0a0a8b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d7f31b27740b286065221838e733d99e94b3307d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1811-avoid-uncalled-private-code"></a>CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오.
|||
|-|-|
|TypeName|AvoidUncalledPrivateCode|
|CheckId|CA1811|
|범주|Microsoft.Performance|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 Private 또는 internal (어셈블리 수준) 멤버가 없는 호출자가 어셈블리, 공용 언어 런타임에 의해 호출 되지 않습니다 및 대리자에 의해 호출 되지 않습니다. 다음 멤버는이 규칙으로 선택 되지 않습니다.

-   명시적 인터페이스 멤버입니다.

-   정적 생성자입니다.

-   Serialization 생성자입니다.

-   로 표시 된 메서드 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 또는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>합니다.

-   재정의 되는 멤버입니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 규칙 논리에 따라 거짓 긍정 진입점 발생 하는 경우 현재 식별 되지 않은 보고할 수 있습니다. 또한 컴파일러를 어셈블리로 호출 되지 않는 코드를 생성할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하 고, 호출 되지 않는 코드를 제거 하 고 또는 호출 하는 코드를 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="related-rules"></a>관련된 규칙
 [CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마십시오.](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: 사용되지 않은 매개 변수를 검토하십시오.](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: 사용되지 않는 로컬 항목을 제거하십시오.](../code-quality/ca1804-remove-unused-locals.md)