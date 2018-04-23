---
title: 'CA2117: APTCA 형식은 APTCA 기본 형식만 확장해야 합니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2117
- AptcaTypesShouldOnlyExtendAptcaBaseTypes
helpviewer_keywords:
- AptcaTypesShouldOnlyExtendAptcaBaseTypes
- CA2117
ms.assetid: c505b586-2f1e-47cb-98ee-a5afcbeda70f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5d8b313f0e1c33eb5c17a291995956e62d8c597e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2117-aptca-types-should-only-extend-aptca-base-types"></a>CA2117: APTCA 형식은 APTCA 기본 형식만 확장해야 합니다.

|||
|-|-|
|TypeName|AptcaTypesShouldOnlyExtendAptcaBaseTypes|
|CheckId|CA2117|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

가진 어셈블리의 public 또는 protected 형식이 고 <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> 특성은 특성이 없는 어셈블리에 선언 된 형식에서 상속 합니다.

## <a name="rule-description"></a>규칙 설명

기본적으로 강력한 이름의 어셈블리에서 public 또는 protected 형식이 암시적으로 보호는 [InheritanceDemand](xref:System.Security.Permissions.SecurityAction#System_Security_Permissions_SecurityAction_InheritanceDemand) 완전 신뢰에 대 한 합니다. 강력한 이름의 어셈블리는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성 (APTCA)이이 보호 필요가 없습니다. 특성 상속 요청을 해제합니다. 노출 된 형식이 상속 요청 없이 어셈블리에 선언 된 완전 신뢰 되지 않은 형식에서 상속 되지 않습니다.

완전히 신뢰할 수 있는 어셈블리에 APTCA 특성이 있으면 어셈블리의 형식이 부분적으로 신뢰할 수 있는 호출자를 허용 하지 않는 형식에서 상속 하는 경우 보안 허점이 불가능 합니다. 두 개의 입력 된 경우 `T1` 및 `T2` 다음 조건을 충족, 악의적인 호출자가 형식을 사용할 수 `T1` 를 보호 하는 암시적 완전 신뢰 상속 요청을 사용 하지 않을 `T2`:

- `T1` APTCA 특성이 있는 완전히 신뢰할 수 있는 어셈블리에서 공용 형식 선언 되었습니다.

- `T1` 형식에서 상속 `T2` 어셈블리 외부에 있습니다.

- `T2`어셈블리에 APTCA 특성이 없고, 따라서 부분적으로 신뢰할 수 있는 어셈블리의 형식에서에서 상속 될 수 없습니다.

부분적으로 신뢰할 수 있는 형식 `X` 에서 상속할 수 `T1`, 해당 액세스 권한을 제공에 선언 된 상속 된 멤버에 `T2`합니다. 때문에 `T2` APTCA 특성이, 직접 파생된 형식 (`T1`) 완전 신뢰에 대 한 상속 요청을 충족 해야 합니다 `T1` 완전 신뢰를 포함 하 고 따라서이 검사를 충족 합니다. 보안 위험 때문에 `X` 보호 하는 상속 요청을 만족 하는에 참여 하지 않는 `T2` 에서 신뢰할 수 없는 서브클래싱 합니다. 이러한 이유로 APTCA 특성이 포함 된 형식에 특성을 하지 않은 형식에 확장 하지 해야 합니다.

다른 보안 문제 및 아마도 일반적인 하나는 파생된 형식 (`T1`), 프로그래머 오류를 통해 보호 된 멤버를 노출할 수 완전 신뢰가 필요한 형식에서 (`T2`). 이 노출 되는 경우 신뢰할 수 없는 호출자 완전히 신뢰할 수 있는 형식에만 사용할 수 있는 정보에 액세스할을 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

APTCA 특성이 필요 하지 않은 어셈블리에 위반에 의해 보고 형식이 있는 경우이 제거 합니다.

APTCA 특성이 필요한 경우 완전 신뢰에 대 한 상속 요청 형식에 추가 합니다. 신뢰할 수 없는 형식에 의해 상속 상속 요청을 방지합니다.

위반 위반에 의해 보고 된 기본 형식의 어셈블리에 APTCA 특성을 추가 하 여 문제를 해결 하는 것이 불가능 합니다. 이렇게 하지 않으면 첫 번째는 어셈블리의 모든 코드 및 어셈블리에 종속 되는 모든 코드는 많은 보안 검토를 수행 하지 않고 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우

이 규칙에서는 경고를에서 표시 하지 않으려면,는 해당 형식에서 노출 하는 보호 된 멤버 직접 또는 간접적으로 불가 신뢰할 수 없는 호출자가 중요 한 정보, 작업 또는 악용에서 사용할 수 있는 리소스에 액세스할 수를 확인 해야 합니다.

## <a name="example"></a>예제

다음 예제에서는 두 어셈블리와 테스트 응용 프로그램을 사용 하 여이 규칙으로 검색 하는 보안 문제를 나타냅니다. 첫 번째 어셈블리에 APTCA 특성이 없고 부분적으로 신뢰할 수 있는 형식 상속 되지 않습니다 (나타내는 `T2` 이전 설명의).

[!code-csharp[FxCop.Security.NoAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_1.cs)]

나타내는 두 번째 어셈블리는 `T1` 이전 설명의 되므로 완전히 신뢰할 수 있는 부분적으로 신뢰할 수 있는 호출자를 허용 합니다.

[!code-csharp[FxCop.Security.YesAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_2.cs)]

에 표시 된 테스트 형식을 `X` 부분적으로 신뢰할 수 있는 어셈블리에는 이전 설명 합니다.

[!code-csharp[FxCop.Security.TestAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_3.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

**그늘진 협곡에서 2003 년 2 월 22 일 오전 12시: 00!**

**Sunny 목초지 테스트:**

**Sunny 목초지에서 2003 년 2 월 22 일 오전 12시: 00!**

## <a name="related-rules"></a>관련된 규칙

[CA2116: APTCA 메서드는 APTCA 메서드만 호출해야 합니다.](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)

## <a name="see-also"></a>참고자료

- [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)
- [부분적으로 신뢰할 수 있는 코드에서 라이브러리 사용](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)
