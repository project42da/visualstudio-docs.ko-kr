---
title: 'CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dc08d39e842afa8bee9baa89f4c788f291d90ea2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오.
|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 외부에서 볼 수 있는 형식이 외부에서 표시 되는 인스턴스 필드를 있습니다.

## <a name="rule-description"></a>규칙 설명
 필드의 주된 용도는 구현을 세부적으로 설명하는 것입니다. 필드는 해야 `private` 또는 `internal` 및 속성을 사용 하 여 공개 해야 합니다. 속성에 액세스 하는 필드를 액세스 하는 것이 고 주요 변경 내용 없이 형식의 기능 확장 속성의 접근자의 코드를 변경할 수와 쉽습니다. 필드 액세스와 일치 하는 데 최적화 되어 방금 전용 또는 내부 필드의 값을 반환 하는 속성 속성에 대해 거의 성능 향상을 외부에서 볼 수 있는 필드를 사용 하 여 연결 됩니다.

 외부에서 볼 수 가리키는 `public`, `protected`, 및 `protected internal` (`Public`, `Protected`, 및 `Protected Friend` Visual Basic에서) 액세스 가능성 수준입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 필드를 확인 `private` 또는 `internal` 및 외부에서 볼 수 있는 속성을 사용 하 여 노출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다. 외부에서 표시 되는 필드 속성을 사용할 수 없는 모든 혜택을 제공 하지 않습니다. 또한 통해 public 필드를 보호할 수 없으므로 [링크 요청](/dotnet/framework/misc/link-demands)합니다. 참조 [CA2112: 보안된 형식은 필드를 노출 해야](../code-quality/ca2112-secured-types-should-not-expose-fields.md)합니다.

## <a name="example"></a>예제
 다음 예제에서는 형식을 보여 줍니다 (`BadPublicInstanceFields`)이이 규칙을 위반 하 합니다. `GoodPublicInstanceFields` 수정 된 코드를 보여 줍니다.

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA2112: 보안 형식은 필드를 노출하면 안 됩니다.](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>참고 항목
 [링크 요구](/dotnet/framework/misc/link-demands)