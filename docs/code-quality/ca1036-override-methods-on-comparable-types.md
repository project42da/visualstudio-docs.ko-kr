---
title: 'CA1036: 비교 가능한 형식에 메서드를 재정의하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1036
- OverrideMethodsOnComparableTypes
helpviewer_keywords:
- OverrideMethodsOnComparableTypes
- CA1036
ms.assetid: 2329f844-4cb8-426d-bee2-cd065d1346d0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: acd90414e101c03bae1d3d74f1be4f538cacfce2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036: 비교 가능한 형식에 메서드를 재정의하십시오.
|||
|-|-|
|TypeName|OverrideMethodsOnComparableTypes|
|CheckId|CA1036|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 Public 또는 protected 형식이 구현 하는 <xref:System.IComparable?displayProperty=fullName> 인터페이스를 재정의 하지 않는 <xref:System.Object.Equals%2A?displayProperty=fullName> 또는 같음, 같지 않음, 보다 작음 또는 보다 큼에 대 한 언어별 연산자를 오버 로드 하지 않습니다. 인터페이스의 구현을 상속 하는 경우 규칙 위반을 보고 하지 않습니다.

## <a name="rule-description"></a>규칙 설명
 사용자 지정 정렬 순서를 정의 하는 형식은 구현에서 <xref:System.IComparable> 인터페이스입니다. <xref:System.IComparable.CompareTo%2A> 메서드 형식의 두 인스턴스에 대 한 적절 한 정렬 순서를 나타내는 정수 값을 반환 합니다. 이 규칙; 정렬 순서를 설정 하는 형식을 식별합니다 이 일반 의미 같음, 같지 않음, 보다 작음 및 보다 큰 적용 되지 않습니다 것을 의미 합니다. 구현을 제공 하는 경우 <xref:System.IComparable>, 일반적으로 수행 해야 재정의할 수도 <xref:System.Object.Equals%2A> 와 일치 하는 값을 반환할 수 있도록 <xref:System.IComparable.CompareTo%2A>합니다. 재정의 하는 경우 <xref:System.Object.Equals%2A> 및 코딩 하는 연산자 오버 로드를 지 원하는 언어로 제공 해야와 일치 하는 연산자 <xref:System.Object.Equals%2A>합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 재정의 <xref:System.Object.Equals%2A>합니다. 선택한 프로그래밍 언어 연산자 오버 로드를 지 원하는 경우에 다음 연산자를 제공 합니다.

-   op_Equality

-   op_Inequality

-   op_LessThan

-   op_GreaterThan

 C#에서는 이러한 연산자를 나타내는 데 사용 되는 토큰은 다음과 같습니다: = =,! =, \<, 및 >입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 누락 된 연산자에 의해 위반이 발생 하 고 선택한 프로그래밍 언어는 Visual Basic의 경우와 연산자 오버 로드를 지원 하지 하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다. Op_Equality 연산자를 구현 하는 경우 의미가 없으며 응용 프로그램 컨텍스트에 이외의 같음 연산자에서 발생할 경우이 규칙에 대 한 경고를 표시 하지 않아도 안전 이기도 합니다. 그러나 해야 항상 op_Equality 통해 및 Object.Equals를 재정의 하는 경우 연산자 = = 합니다.

## <a name="example"></a>예제
 다음 예제에는 올바르게 구현 하는 형식이 포함 되어 <xref:System.IComparable>합니다. 관련 된 다양 한 규칙을 만족 하는 메서드를 식별 하는 코드 주석을 <xref:System.Object.Equals%2A> 및 <xref:System.IComparable> 인터페이스입니다.

 [!code-csharp[FxCop.Design.IComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_1.cs)]

## <a name="example"></a>예제
 다음 응용 프로그램의 동작을 테스트는 <xref:System.IComparable> 앞에 나온 구현 합니다.

 [!code-csharp[FxCop.Design.TestIComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_2.cs)]

## <a name="see-also"></a>참고 항목
 <xref:System.IComparable?displayProperty=fullName> <xref:System.Object.Equals%2A?displayProperty=fullName> [같음 연산자](/dotnet/standard/design-guidelines/equality-operators)