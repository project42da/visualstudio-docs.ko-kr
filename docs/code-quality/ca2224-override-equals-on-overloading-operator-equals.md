---
title: 'CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2224
- OverrideEqualsOnOverloadingOperatorEquals
- OverrideEqualsOnOverridingOperatorEquals
helpviewer_keywords:
- OverrideEqualsOnOverloadingOperatorEquals
- CA2224
ms.assetid: 7312afd9-84ba-417f-923e-7a159b53bf70
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f8836644e109e37855aa79dc67b461591b273786
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2224-override-equals-on-overloading-operator-equals"></a>CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.
|||
|-|-|
|TypeName|OverrideEqualsOnOverloadingOperatorEquals|
|CheckId|CA2224|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 Public 형식이 같음 연산자를 구현 하지만 재정의 하지 않는 <xref:System.Object.Equals%2A?displayProperty=fullName>합니다.

## <a name="rule-description"></a>규칙 설명
 같음 연산자는 구문상 편리한 방법의 기능에 액세스 하기 위한 용도가 <xref:System.Object.Equals%2A> 메서드. 같음 연산자를 구현 하는 경우 해당 논리 같아야의 <xref:System.Object.Equals%2A>합니다.

 코드는이 규칙을 위반 하는 경우 C# 컴파일러는 경고가 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 같음 연산자의 구현 제거 하거나 재정의 <xref:System.Object.Equals%2A> 를 두 메서드에 동일한 값을 반환 합니다. 같음 연산자는 일관 되지 않은 동작이 발생 하지 않도록, 있으면의 구현을 제공 하 여 위반을 해결할 수 있습니다 <xref:System.Object.Equals%2A> 를 호출 하는 <xref:System.Object.Equals%2A> 기본 클래스의 메서드.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 같음 연산자의 상속 된 구현와 같은 값을 반환 하는 경우이 규칙에서는 경고를에서 표시 하지 않는를 안전 하 게 <xref:System.Object.Equals%2A>합니다. "예" 섹션에는이 규칙에서는 경고를에서 표시 하지 않으려면 수 하는 형식을 포함 합니다.

## <a name="examples-of-inconsistent-equality-definitions"></a>일관성 없는 같음 정의의 예

### <a name="description"></a>설명
 다음 예제와 일치 하지 않는 정의 같음 형식을 보여 줍니다. `BadPoint` 같음 연산자의 사용자 지정 구현을 제공 하 여 같음 의미를 변경 하지만 재정의 하지 않습니다 <xref:System.Object.Equals%2A> 동일 하 게 동작 하 게 합니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Usage.OperatorEqualsRequiresEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_1.cs)]

## <a name="example"></a>예제
 다음 코드의 동작을 테스트 `BadPoint`합니다.

 [!code-csharp[FxCop.Usage.TestOperatorEqualsRequiresEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_2.cs)]

 이 예제의 결과는 다음과 같습니다.

 **= (1, 1 [0])와 b ([1] 2, 2) = 같은지? 더**
**는 b = =? 더**
**a 1과 a가 같은? 예**
**a1 = =는? 예**
**b 주소와 복사? 더**
**b 복사 = =? 예**
## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 기술적으로 일관 된 방식에서으로 동작 하지 않는 하 형식을 보여 줍니다.

 [!code-csharp[FxCop.Usage.ValueTypeEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_3.cs)]

## <a name="example"></a>예제
 다음 코드의 동작을 테스트 `GoodPoint`합니다.

 [!code-csharp[FxCop.Usage.TestValueTypeEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_4.cs)]

 이 예제의 결과는 다음과 같습니다.

 **= (1, 1) 및 b = (2, 2) 같은지? 더**
**는 b = =? 더**
**a 1과 a가 같은? 예**
**a1 = =는? 예**
**b 주소와 복사? 예**
**b 복사 = =? 예**
## <a name="class-example"></a>클래스 예제

### <a name="description"></a>설명
 다음 예제에서는이 규칙을 위반 하는 클래스 (참조 형식)를 보여 줍니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Usage.OverrideEqualsClassViolation#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_5.cs)]

## <a name="example"></a>예제
 다음 예제에서는 재정의 하 여 위반을 해결 <xref:System.Object.Equals%2A?displayProperty=fullName>합니다.

 [!code-csharp[FxCop.Usage.OverrideEqualsClassFixed#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_6.cs)]

## <a name="structure-example"></a>구조 예제

### <a name="description"></a>설명
 다음 예제에서는이 규칙을 위반 하는 구조 (값 형식)를 보여 줍니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Usage.OverrideEqualsStructViolation#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_7.cs)]

## <a name="example"></a>예제
 다음 예제에서는 재정의 하 여 위반을 해결 <xref:System.ValueType.Equals%2A?displayProperty=fullName>합니다.

 [!code-csharp[FxCop.Usage.OverrideEqualsStructFixed#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_8.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오.](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)