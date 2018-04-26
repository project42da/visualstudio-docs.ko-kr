---
title: 'CA1052: 정적 소유자 형식은 sealed여야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldBeSealed
- CA1052
helpviewer_keywords:
- CA1052
- StaticHolderTypesShouldBeSealed
ms.assetid: 51a3165d-781e-4a55-aa0d-ea25fee7d4f2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9d20ed9ab4ed7fc47d601fb6edd6d38675d0ccec
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1052-static-holder-types-should-be-sealed"></a>CA1052: 정적 소유자 형식은 sealed여야 합니다.
|||
|-|-|
|TypeName|StaticHolderTypesShouldBeSealed|
|CheckId|CA1052|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 형식이 정적 멤버만 포함 하 고로 선언 되지 않습니다는 [봉인](/dotnet/csharp/language-reference/keywords/sealed) ([NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)) 한정자.

## <a name="rule-description"></a>규칙 설명
 이 규칙에서는 형식에서 파생된 된 형식에서 재정의할 수 있는 모든 기능을 제공 하지 않으므로 정적 멤버를 포함 하는 형식 상속 가능 하도록 설계 되지 않았습니다 가정 합니다. 상속되지 않는 형식은 기본 형식으로 사용되지 않도록 `sealed` 한정자로 표시해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 형식을로 표시 `sealed`합니다. 대상으로 하는 경우 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 형식을로 표시 하는 것이 더 나 것 2.0 이상 `static`합니다. 이러한 방식에 않아도 클래스 만들어지지 않도록 방지 하기 위해 private 생성자를 선언 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 상속 형식을 디자인 하는 경우에이 규칙에서 경고를 표시 합니다. 없는 경우는 `sealed` 한정자 제안 유형을 기본 유형으로 유용 합니다.

## <a name="example-of-a-violation"></a>위반의 예로

### <a name="description"></a>설명
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
 [!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
 [!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]

## <a name="fix-with-the-static-modifier"></a>Static 한정자로 수정

### <a name="description"></a>설명
 다음 예제를 사용 하 여 형식을 표시 하 여이 규칙 위반 문제를 해결 하는 방법을 보여 줍니다는 `static` 한정자입니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Design.StaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_2.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1053: 정적 소유자 형식에는 생성자를 사용하면 안 됩니다.](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)
