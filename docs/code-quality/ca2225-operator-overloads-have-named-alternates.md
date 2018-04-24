---
title: 'CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
helpviewer_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
ms.assetid: af8f7ab1-63ad-4861-afb9-b7a7a2be15e1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1b6e95f73fbb037041aadcc95eb7336a5744ee2d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2225-operator-overloads-have-named-alternates"></a>CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.
|||
|-|-|
|TypeName|OperatorOverloadsHaveNamedAlternates|
|CheckId|CA2225|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 연산자 오버로드가 감지되었으며 예상되는 이름의 대체 메서드를 찾을 수 없습니다.

## <a name="rule-description"></a>규칙 설명
 연산자 오버 로드에 기호는 형식에 대 한 계산을 나타내는 데 사용할 수 있습니다. 예를 들어 더하기 기호 (+)에 추가 하는 오버 로드 하는 형식 이름이 'Add' 인 대체 멤버가 일반적으로 것입니다. 명명 된 대체 멤버는 연산자와 동일한 기능에 대 한 액세스를 제공 하 고 오버 로드 된 연산자를 지원 하지 않는 언어로 프로그래밍의 개발자를 위해 제공 됩니다.

 이 규칙은 다음 표에 나와 있는 연산자를 검사 합니다.

|C#|Visual Basic|C++|대체 이름|
|---------|------------------|-----------|--------------------|
|+ (이진)|+|+ (이진)|추가|
|+=|+=|+=|추가|
|&|그리고|&|BitwiseAnd|
|&=|=|&=|BitwiseAnd|
|&#124;|또는|&#124;|BitwiseOr|
|&#124;=|또는 =|&#124;=|BitwiseOr|
|--|N/A|--|감소|
|/|/|/|나누기|
|/=|/=|/=|나누기|
|==|=|==|같음|
|^|Xor|^|Xor|
|^=|Xor =|^=|Xor|
|>|>|>|비교|
|>=|>=|>=|비교|
|++|N/A|++|증가|
|<>|!=|같음|
|<<|<<|<<|으로 읽기 순서|
|<<=|<<=|<<=|으로 읽기 순서|
|<|<|<|비교|
|<=|<=|\<=|비교|
|&&|N/A|&&|LogicalAnd|
|&#124;&#124;|N/A|&#124;&#124;|LogicalOr|
|!|N/A|!|LogicalNot|
|%|Mod|%|나머지 또는 mod|
|%=|N/A|%=|Mod|
|* (이진)|*|*|곱하기|
|*=|N/A|*=|곱하기|
|~|not|~|OnesComplement|
|>>|>>|>>|속성|
=|N/A|>>=|속성|
|-(이진)|-(이진)|-(이진)|빼기|
|-=|N/A|-=|빼기|
|true|IsTrue|N/A|IsTrue (속성)|
|-(단항)|N/A|-|Negate|
|+ (단항)|N/A|+|더하기|
|false|IsFalse|False|IsTrue (속성)|

 해당 없음 = = 선택한 언어로 오버 로드할 수 없습니다.

 규칙 형식에 암시적 및 명시적 캐스트 연산자는 또한 확인 (`SomeType`) 라는 메서드를 확인 하 여 `ToSomeType` 및 `FromSomeType`합니다.

 C#의 이항 연산자가 오버 로드 해당 대입 연산자, 있는 경우 이기도 암시적으로 오버 로드 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 현재 연산자에 대 한 대체 메서드를 구현 권장 되는 대체 이름을 사용 하 여 이름을 지정 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 공유 라이브러리를 구현 하는 경우에이 규칙에서는 경고를에서 표시 하지 마십시오. 응용 프로그램에는이 규칙에서는 경고를에서 무시 해도 됩니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 구조를 정의 합니다. 이 예제를 수정 하려면 추가 공용 `Add(int x, int y)` 구조에 메서드.

 [!code-csharp[FxCop.Usage.OperatorOverloadsHaveNamedAlternates#1](../code-quality/codesnippet/CSharp/ca2225-operator-overloads-have-named-alternates_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오.](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)