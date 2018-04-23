---
title: 'CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
helpviewer_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
ms.assetid: c7d7126f-fa70-40be-8f93-3243e1760dc5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f588a1539e85ce9aa81a7d126decafba71f32462
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.
|||
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|CheckId|CA1010|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 외부에서 볼 수 있는 형식이 구현 하는 <xref:System.Collections.IEnumerable?displayProperty=fullName> 인터페이스 하지만 구현 하지 않습니다는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 인터페이스를 포함 하는 어셈블리 대상 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]합니다. 이 규칙을 구현 하는 형식을 무시 <xref:System.Collections.IDictionary?displayProperty=fullName>합니다.

## <a name="rule-description"></a>규칙 설명
 컬렉션의 유용성을 높이려면 제네릭 컬렉션 인터페이스 중 하나를 구현합니다. 그러면 컬렉션을 사용 하는 다음과 같은 제네릭 컬렉션 형식을 채울 수 있습니다.

-   <xref:System.Collections.Generic.List%601?displayProperty=fullName>

-   <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>

-   <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 다음 제네릭 컬렉션 인터페이스 중 하나를 구현 합니다.

-   <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>

-   <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>

-   <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙;에서 경고를 표시 하지 않아도 안전 합니다. 하지만, 컬렉션 사용이 더 제한 해야 합니다.

## <a name="example-violation"></a>예제 위반

### <a name="description"></a>설명
 다음 예제에서는 비 제네릭에서 파생 된 클래스 (참조 형식)를 보여 줍니다. `CollectionBase` 이 규칙을 위반 하는 클래스입니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]

### <a name="comments"></a>설명
 이 규칙 위반 문제를 해결 하려면 제네릭 인터페이스를 구현 하거나 이미와 같은 모두 제네릭 및 제네릭이 아닌 인터페이스를 구현 하는 형식에 기본 클래스를 변경는 `Collection<T>` 클래스입니다.

## <a name="fix-by-base-class-change"></a>기본 클래스를 변경 하 여 수정

### <a name="description"></a>설명
 다음 예제에서는 비 제네릭에서 컬렉션의 기본 클래스를 변경 하 여 위반을 해결 `CollectionBase` 클래스에서 제네릭 `Collection<T>` (`Collection(Of T)` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 클래스입니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]

### <a name="comments"></a>설명
 이미 발표 된 클래스의 기본 클래스를 변경 하면 기존 소비자에 게 주요 변경 내용으로 간주 됩니다.

## <a name="fix-by-interface-implementation"></a>인터페이스를 구현 하 여 수정

### <a name="description"></a>설명
 다음 예제에서는 이러한 제네릭 인터페이스를 구현 하 여 위반을 해결: `IEnumerable<T>`, `ICollection<T>`, 및 `IList<T>` (`IEnumerable(Of T)`, `ICollection(Of T)`, 및 `IList(Of T)` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

### <a name="code"></a>코드
 [!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: 제네릭 목록을 노출하지 마십시오.](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: 적합한 제네릭을 사용하십시오.](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>참고 항목
 [제네릭](/dotnet/csharp/programming-guide/generics/index)