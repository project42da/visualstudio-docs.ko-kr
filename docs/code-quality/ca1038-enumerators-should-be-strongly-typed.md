---
title: 'CA1038: 열거자는 강력한 형식이어야 합니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
helpviewer_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
ms.assetid: 8919f526-d487-42a4-87dc-2b2ee25260c4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0cd45f3d601b3bba1bdda795ff098b72e241ca28
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1038-enumerators-should-be-strongly-typed"></a>CA1038: 열거자는 강력한 형식이어야 합니다.
|||
|-|-|
|TypeName|EnumeratorsShouldBeStronglyTyped|
|CheckId|CA1038|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 형식이 <xref:System.Collections.IEnumerator?displayProperty=fullName> 하지만의 강력한 형식의 버전을 제공 하지 않습니다는 <xref:System.Collections.IEnumerator.Current%2A?displayProperty=fullName> 속성입니다. 다음 형식에서 파생 된 형식은이 규칙에서 예외입니다.

-   <xref:System.Collections.CollectionBase?displayProperty=fullName>

-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>

-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

## <a name="rule-description"></a>규칙 설명
 이 규칙에 따라 <xref:System.Collections.IEnumerator> 구현도의 강력한 형식의 버전을 제공할는 <xref:System.Collections.IEnumerator.Current%2A> 속성을 사용자가 인터페이스에서 제공 하는 기능을 사용할 때 반환 값을 강력한 형식으로 캐스팅할 필요가 없습니다. 이 규칙에서는 구현 하는 형식이 가정 <xref:System.Collections.IEnumerator> 보다 강력한 형식의 인스턴스 컬렉션을 포함 <xref:System.Object>합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 인터페이스 속성을 명시적으로 구현 (로 선언 `IEnumerator.Current`). 로 선언 된 속성의 public 강력한 형식의 버전에 추가할 `Current`, 고 강력한 형식의 개체를 반환 하도록 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이진 트리 같은 개체 기반 컬렉션에서 사용 하기 위해 개체 기반 열거자를 구현 하는 경우에이 규칙에서 경고를 표시 합니다. 새 컬렉션을 확장 하는 형식은 강력한 형식의 열거자를 정의 하 고 강력한 형식의 속성을 노출 합니다.

## <a name="example"></a>예제
 다음 예제에서는 강력한 형식의 구현 하는 올바른 방법은 <xref:System.Collections.IEnumerator> 유형입니다.

 [!code-csharp[FxCop.Design.IEnumeratorStrongTypes#1](../code-quality/codesnippet/CSharp/ca1038-enumerators-should-be-strongly-typed_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1035: ICollection 구현에 강력한 형식의 멤버가 있습니다.](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)

 [CA1039: 목록은 강력한 형식이어야 합니다.](../code-quality/ca1039-lists-are-strongly-typed.md)

## <a name="see-also"></a>참고 항목
 <xref:System.Collections.IEnumerator?displayProperty=fullName> <xref:System.Collections.CollectionBase?displayProperty=fullName> <xref:System.Collections.DictionaryBase?displayProperty=fullName> <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>