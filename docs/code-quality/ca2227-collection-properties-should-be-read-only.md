---
title: 'CA2227: 컬렉션 속성은 읽기 전용이어야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: aa1d8644049f78eccfda7402360bdbc930b61601
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: 컬렉션 속성은 읽기 전용이어야 합니다.

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|범주|Microsoft.Usage|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

외부에서 볼 수, 쓰기 가능한 속성은 구현 하는 형식의 <xref:System.Collections.ICollection?displayProperty=fullName>합니다. 이 규칙은 배열, 인덱서 (속성 이름 'Item'으로) 및 사용 권한 집합을 무시합니다.

## <a name="rule-description"></a>규칙 설명

쓰기 가능한 컬렉션 속성을 사용 하면 완전히 다른 컬렉션으로 바꿀 수 있습니다. 읽기 전용 속성에서 대체 되 고 수집을 중지 하지만 여전히 개별 멤버를 설정 하는 가능 합니다. 이면 컬렉션 교체 목표를 선호 하는 디자인 패턴은 컬렉션에서 모든 요소를 제거 하는 메서드 및 컬렉션을 다시 채우십시오. 메서드가 포함입니다. 참조는 <xref:System.Collections.ArrayList.Clear%2A> 및 <xref:System.Collections.ArrayList.AddRange%2A> 의 메서드는 <xref:System.Collections.ArrayList?displayProperty=fullName> 이 패턴의 예에 대 한 클래스입니다.

이진 및 XML serialization 모두 읽기 전용 컬렉션 속성을 지원 합니다. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 클래스에 구현 하는 형식에 대 한 특정 요구 사항이 <xref:System.Collections.ICollection> 및 <xref:System.Collections.IEnumerable?displayProperty=fullName> 직렬화 할 수 있도록 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결 하는 방법

이 규칙 위반 문제를 해결 하려면 읽기 전용 속성을 확인 합니다. 디자인에 필요한 경우 선택을 취소 하 고 컬렉션을 다시 채워야 하는 메서드를 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서 경고를 표시 하지 마십시오.

## <a name="example"></a>예제

다음 예에서는 쓰기 가능한 컬렉션 속성을 갖는 형식을 보여 줍니다 및 컬렉션을 직접 바꿀 수 있습니다 방법을 보여 줍니다. 또한 방법도 사용 하 여 읽기 전용 컬렉션 속성이 바꾸기 `Clear` 및 `AddRange` 메서드가 표시 됩니다.

[!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
[!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
[!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]

## <a name="related-rules"></a>관련된 규칙

[CA1819: 속성은 배열을 반환해서는 안 됩니다.](../code-quality/ca1819-properties-should-not-return-arrays.md)