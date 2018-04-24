---
title: 'CA2105: 배열 필드는 읽기 전용이면 안 됩니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2105
- ArrayFieldsShouldNotBeReadOnly
helpviewer_keywords:
- ArrayFieldsShouldNotBeReadOnly
- CA2105
ms.assetid: 0bdc3421-3ceb-4182-b30c-a992fbfcc35d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 57b652247ea727c59a9e0d0d0c6850039be52634
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2105-array-fields-should-not-be-read-only"></a>CA2105: 배열 필드는 읽기 전용이면 안 됩니다.
|||
|-|-|
|TypeName|ArrayFieldsShouldNotBeReadOnly|
|CheckId|CA2105|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 배열을 포함 하는 공용 또는 보호 된 필드는 읽기 전용으로 선언 됩니다.

## <a name="rule-description"></a>규칙 설명
 적용 하는 경우는 `readonly` (`ReadOnly` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 하 여 다른 배열을 참조할 한정자는 배열에 필드를 포함 하는 필드를 변경할 수 없습니다. 그러나 읽기 전용 필드에 저장된 배열의 요소는 변경할 수 있습니다. 의사 결정 하거나 공개적으로 액세스할 수 있는 읽기 전용 배열 요소를 기반으로 하는 작업을 수행 하는 코드는 보안상 취약 한 부분이 포함 될 수 있습니다.

 디자인 규칙을 위반도 공용 필드 참고 [CA1051: 표시 되는 인스턴스 필드를 선언 하지 마십시오](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙에 의해 식별 되는 보안 취약점으로 인해를 해결 하려면 공개적으로 액세스할 수 있는 읽기 전용 배열 내용에 되지는지 않습니다. 다음 절차 중 하나를 사용 하는 것이 좋습니다.

-   강력한 형식의 컬렉션 변경할 수 없는 배열을 대체 합니다. 자세한 내용은 <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>을 참조하십시오.

-   Public 필드를 private 배열의 복제본을 반환 하는 메서드로 대체 합니다. 없기 때문에 코드를 복제에 사용 하지 않는 않습니다 위험은 없습니다 요소가 수정 하는 경우.

 두 번째 방법을 선택한 경우 바꾸지 마세요 필드 속성. 좋지 않은 배열을 반환 하는 속성에는 성능에 영향을 합니다. 자세한 내용은 참조 [CA1819: 속성은 배열을 반환 해서는](../code-quality/ca1819-properties-should-not-return-arrays.md)합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서 경고를 제외 하는 것이 좋습니다. 필드는 읽기 전용 필드의 내용을 중요 하지 않은 발생 하는 시나리오는 거의 없습니다. 시나리오의 경우 이것이 제거는 `readonly` 메시지를 제외 하는 대신 한정자입니다.

## <a name="example"></a>예제
 이 예제에서는이 규칙을 위반의 위험성을 보여 줍니다. 첫 번째 부분에는 나와 형식이 있는 예제 라이브러리 `MyClassWithReadOnlyArrayField`, 두 개의 필드가 포함 된 (`grades` 및 `privateGrades`) 보호 되지 않습니다. 필드 `grades` public 및 따라서 모든 호출자에 게 노출 됩니다. 필드 `privateGrades` 개인 이지만 호출자에 게 반환 되기 때문에 여전히 취약가 `GetPrivateGrades` 메서드. `securePrivateGrades` 필드 안전 하 게에서 노출 되는 `GetSecurePrivateGrades` 메서드. 좋은 디자인 방법을 따르도록 private으로 선언 됩니다. 두 번째 부분에 저장 된 값을 변경 하는 코드를 보여 줍니다.는 `grades` 및 `privateGrades` 멤버입니다.

 예제 클래스 라이브러리는 다음 예제에 표시 됩니다.

 [!code-csharp[FxCop.Security.ArrayFieldsNotReadOnly#1](../code-quality/codesnippet/CSharp/ca2105-array-fields-should-not-be-read-only_1.cs)]

## <a name="example"></a>예제
 다음 코드 예제 클래스 라이브러리를 사용 하 여 읽기 전용 배열 보안 문제를 보여 줍니다.

 [!code-csharp[FxCop.Security.TestArrayFieldsRead#1](../code-quality/codesnippet/CSharp/ca2105-array-fields-should-not-be-read-only_2.cs)]

 이 예제에서 출력이 생성 됩니다.

 **변조 하기 전에: 등급: 90, 90, 90 개인 등급: 90, 90, 90 보안 등급, 90, 90, 90**
**무단 변경 후: 등급: 90, 555, 90 개인 등급: 90, 555, 90 보안 등급, 90, 90, 90**
## <a name="see-also"></a>참고 항목
 <xref:System.Array?displayProperty=fullName> <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>