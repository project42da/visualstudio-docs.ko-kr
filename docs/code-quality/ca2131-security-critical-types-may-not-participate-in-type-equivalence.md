---
title: 'CA2131: 보안에 중요한 형식은 형식 등가에 참여할 수 없습니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2131
ms.assetid: 4170f3b1-6086-430d-8fba-837d5538c573
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a6689e6f0be6db4b14f03006d1aa784ae70642ef
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2131-security-critical-types-may-not-participate-in-type-equivalence"></a>CA2131: 보안에 중요한 형식은 형식 등가에 참여할 수 없습니다.
|||
|-|-|
|TypeName|CriticalTypesMustNotParticipateInTypeEquivalence|
|CheckId|CA2131|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 동일 형식 및 해당 형식 자체에 참가 하는 형식 또는 멤버 또는 필드 형식으로 표시 되어는 <xref:System.Security.SecurityCriticalAttribute> 특성입니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 중요한 형식 또는 중요한 메서드나 필드를 포함하는 형식이 형식 동등에 참여하는 경우에 적용됩니다. 과 함께 로드에 실패 하는 CLR에서 이러한 형식을 감지한 경우는 <xref:System.TypeLoadException> 런타임 시. 일반적으로 이 규칙은 사용자가 tlbimp와 컴파일러를 이용하여 형식 동등을 수행하지 않고 수동으로 형식 동등을 구현하는 경우에만 적용됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 SecurityCritical 특성을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 인터페이스, 메서드 및이 규칙을 실행 하는 필드를 보여 줍니다.

 [!code-csharp[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../code-quality/codesnippet/CSharp/ca2131-security-critical-types-may-not-participate-in-type-equivalence_1.cs)]

## <a name="see-also"></a>참고 항목
 [보안 투명 코드, 수준 2](/dotnet/framework/misc/security-transparent-code-level-2)