---
title: 'CA2141: 투명한 메서드는 LinkDemands를 충족해서는 안 됩니다'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6bb38d11ca7312a7eda2ec4b516ab384741f9ab7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>CA2141: 투명한 메서드는 LinkDemands를 충족해서는 안 됩니다
|||
|-|-|
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|
|CheckId|CA2141|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 로 표시 되지 않으면 어셈블리의 메서드를 호출 하는 보안 투명 메서드는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성 (APTCA) 또는 보안 투명 메서드가 충족는 <xref:System.Security.Permissions.SecurityAction> `.LinkDemand` 는 형식 또는 메서드에 대 한 합니다.

## <a name="rule-description"></a>규칙 설명
 LinkDemand 충족은 보안에 중요 한 작업 의도 하지 않은 권한 상승을 초래할 수 있습니다. 보안 중요 한 코드와 같은 보안 감사 요구 사항이 적용 되지 않기 때문에 보안 투명 코드, LinkDemands을 충족 해야 합니다. 보안 규칙 집합 수준 1 어셈블리의 투명 한 메서드는 성능 문제가 발생할 수 있으며 런타임 시 전체 요청으로 변환할 수를 만족 하는 모든 LinkDemands를 발생 합니다. 보안 규칙 집합 수준 2 어셈블리에서 투명 한 메서드에 LinkDemand를 충족 하려고 하면 적시에 (JIT) 컴파일러에서 컴파일하는 데 실패 합니다.

 어셈블리에서 해당 usee 수준 2 보안, 보안 투명 메서드가 LinkDemand를 만족 하거나 APTCA가 아닌 어셈블리의 메서드를 호출 하 여 시도 발생 한 <xref:System.MethodAccessException>; 수준 1 어셈블리에 LinkDemand가 한 완전 요청이 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 액세스 메서드를 표시는 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성 또는 액세스 되는 메서드의 LinkDemand를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 이 예제에서는 투명 메서드가 LinkDemand를 가진 메서드를 호출 하려고 합니다. 이 규칙은이 코드에 실행 됩니다.

 [!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../code-quality/codesnippet/CSharp/ca2141-transparent-methods-must-not-satisfy-linkdemands_1.cs)]