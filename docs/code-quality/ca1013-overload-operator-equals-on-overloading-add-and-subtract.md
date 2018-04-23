---
title: 'CA1013: 더하기 및 빼기를 오버로드할 때 같음 연산자를 오버로드하십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
helpviewer_keywords:
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
ms.assetid: 5bd28d68-c179-49ff-af47-5250b8b18a10
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7fd43cc3077c037b70eaa8107563bd8f40b6a096
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1013-overload-operator-equals-on-overloading-add-and-subtract"></a>CA1013: 더하기 및 빼기를 오버로드할 때 같음 연산자를 오버로드하십시오.
|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverloadingAddAndSubtract|
|CheckId|CA1013|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 public 또는 protected 형식이 같음 연산자를 구현하지 않고 더하기 또는 빼기 연산자를 구현합니다.

## <a name="rule-description"></a>규칙 설명
 더하기 및 빼기와 같은 작업을 사용 하 여 형식의 인스턴스를 결합할 수 있습니다를 반환 하는 같음 정의 거의 항상 해야 `true` 구성 값이 같은 두 개의 인스턴스에 대해 합니다.

 같음 연산자의 오버 로드 된 구현에서 기본 같음 연산자를 사용할 수 없습니다. 이렇게 하면 스택 오버플로가 발생 합니다. 같음 연산자를 구현 하려면 구현에서 Object.Equals 메서드를 사용 합니다. 다음 예제를 참조하세요.

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 더하기 및 빼기 연산자가 포함 된 수학적으로 일관 되도록 같음 연산자를 구현 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 같음 연산자의 기본 구현에서 형식에 대 한 올바른 동작을 제공 하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 형식 정의 (`BadAddableType`)이이 규칙을 위반 하 합니다. 이 형식은 테스트 필드 값이 같은 두 인스턴스에 확인 하도록 같음 연산자를 구현 해야 `true` 같음에 대 한 합니다. 형식 `GoodAddableType` 수정 된 구현을 보여 줍니다. 이 형식은 또한 같지 않음 연산자를 구현 및 재정의 <xref:System.Object.Equals%2A> 다른 규칙을 충족 하기 위해 합니다. 완전 한 구현도 구현 <xref:System.Object.GetHashCode%2A>합니다.

 [!code-csharp[FxCop.Design.AddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_1.cs)]

## <a name="example"></a>예제
 다음 예제에서는 같음 연산자에 대 한 기본 및 올바른 동작을 설명 하기 위해이 항목에서 이전에 정의 된 형식의 인스턴스를 사용 하 여 같음을 테스트 합니다.

 [!code-csharp[FxCop.Design.TestAddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_2.cs)]

 이 예제의 결과는 다음과 같습니다.

 **잘못 된 유형: {2, 2} {2, 2} 같은지? 더**
**좋은 유형: {3, 3} {3, 3} 같은지? 예**
**좋은 유형: {3, 3} {3, 3}는 = =?   예**
**형식이 잘못 되었습니다: {2, 2} {9, 9} 같은지? 더**
**좋은 유형: {3, 3} {9, 9}는 = =?   아니요**
## <a name="see-also"></a>참고 항목
 [같음 연산자](/dotnet/standard/design-guidelines/equality-operators)