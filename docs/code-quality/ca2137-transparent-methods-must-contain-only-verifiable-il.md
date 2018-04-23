---
title: 'CA2137: 투명한 메서드는 안정형 IL만 포함해야 합니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 647240903ab2ada2e8fb319dca967a346a84b4cb
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2137-transparent-methods-must-contain-only-verifiable-il"></a>CA2137: 투명한 메서드는 안정형 IL만 포함해야 합니다.
|||
|-|-|
|TypeName|TransparentMethodsMustBeVerifiable|
|CheckId|CA2137|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 메서드가 확인할 수 없는 코드를 포함하거나 형식을 참조로 반환합니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 보안 투명 코드에서 확인할 수 없는 MSIL(Microsoft Intermediate Language)을 실행하려고 할 때 적용됩니다. 그러나 이 규칙은 완전한 IL 검증 도구를 포함하지 않으며 대신 추론을 사용하여 MSIL 확인 시 대부분의 위반을 catch합니다.

 실행 코드에만 확인할 수 있는 MSIL이 포함 되어 있음을 있으려면 [Peverify.exe (PEVerify 도구)](/dotnet/framework/tools/peverify-exe-peverify-tool) 어셈블리에 있습니다. 사용 하 여 PEVerify 실행의 **투명 /** 만 확인할 수 없는 투명 한 메서드에 오류가 발생 하는 출력을 제한 하는 옵션입니다. 경우는 투명 옵션 사용 하지 않으면 /, PEVerify도 확인할 수 없는 코드를 포함할 수 있는 중요 한 메서드를 확인 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 사용 하 여 메서드를 표시는 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성 또는 확인할 수 없는 코드를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 이 예에서 메서드 비안정형 코드를 사용 하 고로 표시 해야는 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성입니다.

 [!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../code-quality/codesnippet/CSharp/ca2137-transparent-methods-must-contain-only-verifiable-il_1.cs)]