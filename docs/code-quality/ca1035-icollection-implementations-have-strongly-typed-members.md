---
title: 'CA1035: ICollection 구현에 강력한 형식의 멤버가 있습니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ICollectionImplementationsHaveStronglyTypedMembers
- CA1035
helpviewer_keywords:
- CA1035
- ICollectionImplementationsHaveStronglyTypedMembers
ms.assetid: ad404eb5-cf6a-44b7-b78a-8ebfb654bc7f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 40a81ea09c672728445ee4e25f82adecaa42ae79
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1035-icollection-implementations-have-strongly-typed-members"></a>CA1035: ICollection 구현에 강력한 형식의 멤버가 있습니다.
|||
|-|-|
|TypeName|ICollectionImplementationsHaveStronglyTypedMembers|
|CheckId|CA1035|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 형식이 <xref:System.Collections.ICollection?displayProperty=fullName> 하지만 대 한 강력한 형식의 메서드를 제공 하지 않습니다 <xref:System.Collections.ICollection.CopyTo%2A?displayProperty=fullName>합니다. 강력한 형식의 버전 <xref:System.Collections.ICollection.CopyTo%2A> 두 개의 매개 변수를 받아들여야 하 고 사용할 수 없습니다는 <xref:System.Array?displayProperty=fullName> 또는 배열을 <xref:System.Object?displayProperty=fullName> 첫 번째 매개 변수로 합니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙에 따라 <xref:System.Collections.ICollection> 사용자가 인수를 캐스팅할 필요가 있도록 구현 제공할 강력한 형식의 멤버가 <xref:System.Object> 인터페이스에서 제공 되는 기능을 사용할 때를 입력 합니다. 이 규칙에서는 구현 하는 형식이 가정 <xref:System.Collections.ICollection> 보다 강력한 형식의 인스턴스 컬렉션을 관리 하기 위해 지금 수행 <xref:System.Object>합니다.

 <xref:System.Collections.ICollection>는 <xref:System.Collections.IEnumerable?displayProperty=fullName> 인터페이스를 구현합니다. 컬렉션의 개체를 확장할 경우 <xref:System.ValueType?displayProperty=fullName>에 대 한 강력한 형식의 멤버를 제공 해야 <xref:System.Collections.IEnumerable.GetEnumerator%2A> boxing 하 여 발생 하는 성능 저하를 방지 하기 위해. 이 컬렉션의 개체는 참조 형식이 필요 하지 않습니다.

 인터페이스 멤버의 강력한 형식의 버전을 구현 하려면 인터페이스 멤버를 명시적으로 구현 형식에서 이름을 사용 하 여 `InterfaceName.InterfaceMemberName`와 같은 <xref:System.Collections.ICollection.CopyTo%2A>합니다. 명시적 인터페이스 멤버는 인터페이스에서 선언 된 데이터 형식을 사용 합니다. 와 같은 인터페이스 멤버 이름을 사용 하 여 강력한 형식의 멤버를 구현 <xref:System.Collections.ICollection.CopyTo%2A>합니다. Public으로 강력한 형식의 멤버를 선언 하 고 매개 변수를 선언 컬렉션에 의해 관리 되는 강력한 형식의 값을 반환 합니다. 강력한 형식 보다 약한 종류를 같은 바꿉니다 <xref:System.Object> 및 <xref:System.Array> 인터페이스에 선언 된 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 인터페이스 멤버를 명시적으로 구현 (로 선언 <xref:System.Collections.ICollection.CopyTo%2A>). 로 선언 된 강력한 형식의 public 멤버를 추가 `CopyTo`, 강력한 형식의 배열을 첫 번째 매개 변수로 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 새 컬렉션을 확장 하는 형식이 강력한 형식을 결정 하는 이진 트리 같은 새 개체 기반 컬렉션을 구현 하는 경우에이 규칙에서 경고를 표시 합니다. 이러한 형식은이 규칙을 준수 하 고 강력한 형식의 멤버를 노출 해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 구현 하는 올바른 방법은 <xref:System.Collections.ICollection>합니다.

 [!code-csharp[FxCop.Design.ICollectionStrongTypes#1](../code-quality/codesnippet/CSharp/ca1035-icollection-implementations-have-strongly-typed-members_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1038: 열거자는 강력한 형식이어야 합니다.](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

 [CA1039: 목록은 강력한 형식이어야 합니다.](../code-quality/ca1039-lists-are-strongly-typed.md)

## <a name="see-also"></a>참고 항목
 <xref:System.Array?displayProperty=fullName> <xref:System.Collections.IEnumerable?displayProperty=fullName> <xref:System.Collections.ICollection?displayProperty=fullName> <xref:System.Object?displayProperty=fullName>