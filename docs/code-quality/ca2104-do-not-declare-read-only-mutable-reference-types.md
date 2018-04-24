---
title: 'CA2104: 변경 가능한 읽기 전용 참조 형식을 선언하지 마십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDeclareReadOnlyMutableReferenceTypes
- CA2104
helpviewer_keywords:
- CA2104
- DoNotDeclareReadOnlyMutableReferenceTypes
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fcf9379f9950264aca5c76355867ccb44ba40282
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104: 변경 가능한 읽기 전용 참조 형식을 선언하지 마십시오.
|||
|-|-|
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|
|CheckId|CA2104|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 외부에서 볼 수 있는 형식에 변경 가능한 참조 형식인, 외부에서 볼 수 있는 읽기 전용 필드가 포함되었습니다.

## <a name="rule-description"></a>규칙 설명
 변경 가능한 형식은 해당 인스턴스 데이터를 수정할 수 있는 형식을 말합니다. <xref:System.Text.StringBuilder?displayProperty=fullName> 클래스는 변경 가능한 참조 형식의 예입니다. 클래스의 인스턴스 값을 변경할 수 있는 멤버가 포함 됩니다. 변경할 수 없는 참조 형식으로 변경의 예로 <xref:System.String?displayProperty=fullName> 클래스입니다. 시작 된 후 해당 값 변경할 수 없습니다.

 읽기 전용 한정자 ([readonly](/dotnet/csharp/language-reference/keywords/readonly) C#에서는 [ReadOnly](/dotnet/visual-basic/language-reference/modifiers/readonly) 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], 및 [const](/cpp/cpp/const-cpp) c + +에서) 참조 형식에 필드 (c + +에서 포인터) 있는 필드 수 없게 되 참조 형식의 다른 인스턴스도 바뀝니다. 그러나 한정자는 참조 형식을 통해 수정 되지 않도록 필드의 인스턴스 데이터를 방해 되지는 않습니다.

 읽기 전용 배열 필드는이 규칙에서 제외 되지만 대신 위반 하는 [CA2105: 배열 필드는 읽기 전용 이면 안](../code-quality/ca2105-array-fields-should-not-be-read-only.md) 규칙입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 읽기 전용 한정자를 제거 하거나 주요 변경 내용을 적용할 수 있는 변경할 수 없는 형식이 있는 필드를 바꾸십시오.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 필드 형식을 변경할 수 없는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙의 위반을 발생 하는 필드 선언을 보여 줍니다.

 [!code-cpp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CPP/ca2104-do-not-declare-read-only-mutable-reference-types_1.cpp)]
 [!code-csharp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CSharp/ca2104-do-not-declare-read-only-mutable-reference-types_1.cs)]
 [!code-vb[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/VisualBasic/ca2104-do-not-declare-read-only-mutable-reference-types_1.vb)]