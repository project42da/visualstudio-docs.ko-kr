---
title: 'CA2208: 인수 예외를 올바르게 인스턴스화하십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2208
- InstantiateArgumentExceptionsCorrectly
helpviewer_keywords:
- InstantiateArgumentExceptionsCorrectly
- CA2208
ms.assetid: e2a48939-d9fa-478c-b2f9-3bdbce07dff7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ab379305eae593a1c2f14f5c2ec860d398af2eaf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2208-instantiate-argument-exceptions-correctly"></a>CA2208: 인수 예외를 올바르게 인스턴스화하십시오.
|||
|-|-|
|TypeName|InstantiateArgumentExceptionsCorrectly|
|CheckId|CA2208|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 가능한 원인은 다음과를 같습니다.

-   즉, 또는에서 파생 된 예외 형식의 기본 (매개 변수가 없는) 생성자 호출 <xref:System.ArgumentException>합니다.

-   즉, 또는에서 파생 된 예외 형식의 매개 변수가 있는 생성자에 잘못 된 문자열 인수가 전달 <xref:System.ArgumentException>합니다.

## <a name="rule-description"></a>규칙 설명
 기본 생성자를 호출 하는 대신 더 의미 있는 예외 메시지를 제공 해야 하는 생성자 오버 로드 중 하나를 호출 합니다. 예외 메시지는 개발자를 대상으로 하 고 수정 하거나 예외를 방지 하는 방법과 오류 조건을 명확 하 게 설명 해야 합니다.

 하나 및 두 개의 문자열 생성자의 시그니처에 <xref:System.ArgumentException> 파생된 형식을 기준으로 일치 하지 않는 `message` 및 `paramName` 매개 변수입니다. 이러한 생성자는 올바른 문자열 인수와 함께 호출 하 고 있는지 확인 합니다. 시그니처에 다음과 같습니다.

 <xref:System.ArgumentException>(문자열 `message`)

 <xref:System.ArgumentException>(문자열 `message`, 문자열 `paramName`)

 <xref:System.ArgumentNullException>(문자열 `paramName`)

 <xref:System.ArgumentNullException>(문자열 `paramName`, 문자열 `message`)

 <xref:System.ArgumentOutOfRangeException>(문자열 `paramName`)

 <xref:System.ArgumentOutOfRangeException>(문자열 `paramName`, 문자열 `message`)

 <xref:System.DuplicateWaitObjectException>(문자열 `parameterName`)

 <xref:System.DuplicateWaitObjectException>(문자열 `parameterName`, 문자열 `message`)

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 메시지, 매개 변수 이름 또는 둘 모두를 사용 하는 생성자를 호출 하 고 인수는 형식에 대해 적절 한 있는지 <xref:System.ArgumentException> 호출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 올바른 문자열 인수를 매개 변수화 된 생성자를 호출 하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 ArgumentNullException 형식의 인스턴스를 제대로 인스턴스화하는 생성자를 보여 줍니다.

 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_1.cpp)]
 [!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_1.cs)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_1.vb)]

## <a name="example"></a>예제
 다음 예제에서는 생성자 인수를 전환 하 여 위의 위반을 해결 합니다.

 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_2.cpp)]
 [!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_2.cs)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_2.vb)]