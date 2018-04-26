---
title: 'CA2002: 약한 ID를 가진 개체를 잠그지 마십시오.'
ms.date: 01/31/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotLockOnObjectsWithWeakIdentity
- CA2002
helpviewer_keywords:
- CA2002
- DoNotLockOnObjectsWithWeakIdentity
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 7708f5e968fed8765ca27bff99d479957927440b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2002-do-not-lock-on-objects-with-weak-identity"></a>CA2002: 약한 ID를 가진 개체를 잠그지 마십시오.

|||
|-|-|
|TypeName|DoNotLockOnObjectsWithWeakIdentity|
|CheckId|CA2002|
|범주|Microsoft.Reliability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

스레드를 약한 id를 가진 개체에 대 한 잠금을 획득 하려고 시도 합니다.

## <a name="rule-description"></a>규칙 설명

응용 프로그램 도메인 경계를 가로질러 직접 액세스할 수 있는 개체를 약한 ID를 가진 개체라고 합니다. 약한 ID를 가진 개체에 대해 잠금을 가져오려고 시도하는 스레드는 같은 개체에 대해 잠금을 가진 다른 응용 프로그램 도메인의 스레드에 의해 차단될 수 있습니다.

형식은 약한 id를가지고 있으며 규칙에서 플래그가 지정:

- <xref:System.String>

- 포함 하 여 값 형식의 배열 [정수 계열 형식](/dotnet/csharp/language-reference/keywords/integral-types-table), [부동 소수점 형식](/dotnet/csharp/language-reference/keywords/floating-point-types-table), 및 <xref:System.Boolean>합니다.

- <xref:System.MarshalByRefObject>

- <xref:System.ExecutionEngineException>

- <xref:System.OutOfMemoryException>

- <xref:System.StackOverflowException>

- <xref:System.Reflection.MemberInfo>

- <xref:System.Reflection.ParameterInfo>

- <xref:System.Threading.Thread>

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 설명 섹션의 목록에 포함 되지 않은 형식에서 개체를 사용 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="related-rules"></a>관련된 규칙

[CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

## <a name="example"></a>예제

다음 예제에서는 규칙을 위반 하는 몇 개의 개체 잠금을 보여 줍니다.

[!code-vb[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/VisualBasic/ca2002-do-not-lock-on-objects-with-weak-identity_1.vb)]
[!code-csharp[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/CSharp/ca2002-do-not-lock-on-objects-with-weak-identity_1.cs)]

## <a name="see-also"></a>참고자료

<xref:System.Threading.Monitor>
<xref:System.AppDomain>
[lock 문 (C#)](/dotnet/csharp/language-reference/keywords/lock-statement)
[SyncLock 문 (Visual Basic)](/dotnet/visual-basic/language-reference/statements/synclock-statement)