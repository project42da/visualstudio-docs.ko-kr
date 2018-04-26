---
title: 'CA2147: 투명 메서드는 보안 어설션을 사용할 수 없습니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SecurityTransparentCodeShouldNotAssert
- CA2147
- CA2128
helpviewer_keywords:
- CA2128
- SecurityTransparentCodeShouldNotAssert
ms.assetid: 5d31e940-e599-4b23-9b28-1c336f8d910e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f732e22d53b4d469f73c4ef3efc753240fa6841f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2147-transparent-methods-may-not-use-security-asserts"></a>CA2147: 투명 메서드는 보안 어설션을 사용할 수 없습니다.
|||
|-|-|
|TypeName|SecurityTransparentCodeShouldNotAssert|
|CheckId|CA2147|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 로 표시 된 코드 <xref:System.Security.SecurityTransparentAttribute> 어설션할 수 있는 충분 한 권한을 부여 하지 합니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 모든 메서드 및 형식 중 하나가 100% 투명 어셈블리나 투명/중요 혼합, 되 고 선언적 이거나 명령 사용 플래그를 지정 된 어셈블리의 분석 <xref:System.Security.CodeAccessPermission.Assert%2A>합니다.

 런타임에 모든 호출 <xref:System.Security.CodeAccessPermission.Assert%2A> 투명 코드에서 발생 합니다는 <xref:System.InvalidOperationException> throw 됩니다. 이 두 100% 투명 어셈블리 및 투명/중요 혼합된 어셈블리 여기서 메서드 또는 형식, 투명 하 게 선언 되지만 선언적 이거나 명령 Assert 포함 발생할 수 있습니다.

 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0 라는 기능을 도입 *투명도*합니다. 개별 메서드, 필드, 인터페이스, 클래스 및 형식 투명 하거나 중요할 수 있습니다.

 투명 코드는 보안 권한을 상승 시킬 수 없습니다. 따라서 어떠한 사용 권한도 부여 되거나 요청은 자동으로 호출자 또는 호스트 응용 프로그램 도메인에서 코드를 통해 전달 됩니다. 권한 상승의 예로 Assert, LinkDemands, SuppressUnmanagedCode, 및 `unsafe` 코드입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 와 Assert를 호출 하는 코드를 표시 하거나 문제를 해결 하려면는 <xref:System.Security.SecurityCriticalAttribute>, 어설션을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서 메시지를 표시 하지 마십시오.

## <a name="example"></a>예제
 이 코드는 경우 실패 `SecurityTestClass` 경우는 투명 하 고는 `Assert` 메서드가 throw 한 <xref:System.InvalidOperationException>합니다.

 [!code-csharp[FxCop.Security.CA2147.TransparentMethodsMustNotUseSecurityAsserts#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_1.cs)]

## <a name="example"></a>예제
 첫 번째 방법은 다음 예제에서 SecurityTransparentMethod 메서드 코드 검토 하 고 메서드가 권한 상승로 간주 되 면 표시 SecurityTransparentMethod with 보안에 중요 한이 있어야 하는 자세한, 완료 및 오류 없이 보안 함께 모든 설명선 Assert 메서드 내에서 발생 하는 방법에 감사를 수행 해야 합니다.

 [!code-csharp[FxCop.Security.SecurityTransparentCode2#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_2.cs)]

 두 번째 방법은 하는 코드에서 어설션을 제거 하 고 모든 후속 파일 호출자에 게 SecurityTransparentMethod 초과 되는 I/O 권한 요청 흐름을 사용 하는 것입니다. 보안 검사를 활성화 합니다. 이 경우 권한 요청 호출자 및/또는 응용 프로그램 도메인으로 이동 되므로 세 키워드가 없는 보안 감사는 필요 일반적으로 합니다. 권한 요청 호스팅 환경 및 원본 코드 권한 부여 하는 보안 정책을 통해 제어 밀접 하 게 됩니다.

## <a name="see-also"></a>참고 항목
 [보안 경고](../code-quality/security-warnings.md)