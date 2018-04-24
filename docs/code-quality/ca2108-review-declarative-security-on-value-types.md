---
title: 'CA2108: 값 형식에서 선언적 보안을 검토하십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ReviewDeclarativeSecurityOnValueTypes
- CA2108
helpviewer_keywords:
- ReviewDeclarativeSecurityOnValueTypes
- CA2108
ms.assetid: d62bffdd-3826-4d52-a708-1c646c5d48c2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d07245724d70b5bc6ba69deae4311dcb2a10056
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2108-review-declarative-security-on-value-types"></a>CA2108: 값 형식에서 선언적 보안을 검토하십시오.
|||
|-|-|
|TypeName|ReviewDeclarativeSecurityOnValueTypes|
|CheckId|CA2108|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 Public 또는 protected 값 형식이에 의해 보안 됩니다는 [데이터 및 모델링](/dotnet/framework/data/index) 또는 [링크 요청](/dotnet/framework/misc/link-demands)합니다.

## <a name="rule-description"></a>규칙 설명
 값 형식은 할당 되 고 다른 생성자를 실행 하기 전에 해당 기본 생성자에서 초기화 됩니다. 값 형식이 요청 또는 LinkDemand를 보호 하는 호출자에 게 권한이 아닌 다른 생성자와 보안 검사를 충족 하는 경우 기본값은 실패 하 고 보안 예외가 throw 됩니다. 값 형식 할당이 해제 되지 않습니다. 기본 생성자에서 설정 된 상태에서 제외 됩니다. 값 형식의 인스턴스를 전달 하는 호출자가 만들거나 인스턴스에 액세스할 수 있는 권한이 가정 하지 마십시오.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 형식에서 보안 검사를 제거 하 고 사용 하 여 메서드 수준의 보안 그 자리에 검사 하지 않는 한이 규칙 위반을 수정할 수 없습니다. 위반 이런이 방식으로 수정 값 형식의 인스턴스를 얻는 부적절 한 권한 있는 호출자를 주지 않는 것을 참고 합니다. 해당 기본 상태인 값 형식의 인스턴스로 중요 한 정보를 노출 하지 및 유해한 방식으로 사용할 수 없습니다 확인 해야 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 모든 호출자가 보안 위협을 하지 않고 기본 상태로에서 값 형식의 인스턴스를 얻을 수 있는 경우이 규칙에서는 경고를에서 표시 하지 않을 수 있습니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 값 형식을 포함 하는 라이브러리를 보여 줍니다. `StructureManager` 유형 값 형식의 인스턴스를 전달 하는 호출자가 만들거나 인스턴스에 액세스할 수 있는 권한이 있다고 가정 합니다.

 [!code-csharp[FxCop.Security.DemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_1.cs)]

## <a name="example"></a>예제
 다음 응용 프로그램 라이브러리의 약점을 보여 줍니다.

 [!code-csharp[FxCop.Security.TestDemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_2.cs)]

 이 예제의 결과는 다음과 같습니다.

 **구조 사용자 지정 생성자: 요청에 실패 했습니다. ** 
 **새 값 SecuredTypeStructure 100 100**
**SecuredTypeStructure 200 200 새 값**
## <a name="see-also"></a>참고 항목
 [링크 요구](/dotnet/framework/misc/link-demands) [데이터 및 모델링](/dotnet/framework/data/index)