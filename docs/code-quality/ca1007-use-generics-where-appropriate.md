---
title: 'CA1007: 적합한 제네릭을 사용하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1007
- UseGenericsWhereAppropriate
helpviewer_keywords:
- CA1007
- UseGenericsWhereAppropriate
ms.assetid: eab780ea-3b1f-4d32-b15a-5d48da2df46b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6379a811da7c62be59a322ee68ad9f030d9693d9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1007-use-generics-where-appropriate"></a>CA1007: 적합한 제네릭을 사용하십시오.
|||
|-|-|
|TypeName|UseGenericsWhereAppropriate|
|CheckId|CA1007|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 형식의 참조 매개 변수를 포함 하는 외부에서 볼 수 메서드 <xref:System.Object?displayProperty=fullName>, 포함 된 어셈블리 대상을 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]합니다.

## <a name="rule-description"></a>규칙 설명
 참조 매개 변수는 매개 변수를 사용 하 여 한정 되는 `ref` (`ByRef` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 키워드입니다. 참조 매개 변수에 대해 제공 되는 인수 형식을 참조 매개 변수 형식과 일치 해야 합니다. 참조 매개 변수 형식에서 파생 된 형식을 사용 하려면 먼저 유형 캐스팅 하 고 참조 매개 변수 형식의 변수에 할당 해야 합니다. 제약 조건 형식을 참조 매개 변수 형식으로 먼저 캐스팅 하지 않고 메서드에 전달할 수에 따라 모든 형식을 허용 하는 제네릭 메서드를 사용 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 메서드 제네릭으로 찾아 바꿉니다는 <xref:System.Object> 형식 매개 변수를 사용 하 여 매개 변수입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 특수 및 제네릭 메서드로 구현 되는 범용 스왑 루틴을 보여 줍니다. Note 제네릭이 아닌 메서드에 비해 제네릭 메서드를 사용 하 여 문자열 얼마나 효율적으로 바뀝니다.

 [!code-vb[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/VisualBasic/ca1007-use-generics-where-appropriate_1.vb)]
 [!code-csharp[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/CSharp/ca1007-use-generics-where-appropriate_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: 제네릭 목록을 노출하지 마십시오.](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../code-quality/ca1003-use-generic-event-handler-instances.md)

## <a name="see-also"></a>참고 항목
 [제네릭](/dotnet/csharp/programming-guide/generics/index)