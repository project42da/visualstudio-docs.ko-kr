---
title: 'CA1819: 속성은 배열을 반환해서는 안 됩니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8f98e92174d7f01c6adf174ef5ff27e68ca406ae
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: 속성은 배열을 반환해서는 안 됩니다.
|||
|-|-|
|TypeName|PropertiesShouldNotReturnArrays|
|CheckId|CA1819|
|범주|Microsoft.Performance|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 공용 형식에서 공용 또는 보호 된 속성을 반환합니다.

## <a name="rule-description"></a>규칙 설명
 속성에서 반환 된 배열은 하지 쓰기 가능한 속성은 읽기 전용으로 설정 하는 경우에 합니다. 배열을 무단으로 변경하지 못하도록 하려면 속성에서 배열의 복사본을 반환해야 합니다. 일반적으로 사용자는 이러한 속성을 호출할 경우 성능에 부정적인 영향을 준다는 것을 인식하지 못합니다. 특히, 인덱싱된 속성으로 속성을 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 메서드는 속성을 확인 하거나 컬렉션을 반환 하려면이 속성을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 특성은 배열을 반환 하는 속성을 포함할 수 있지만 컬렉션을 반환 하는 속성을 포함할 수 없습니다. 파생 된 특성의 속성에 대해 발생 하는 경고를 표시 하지 않을 수는 <xref:System.Attribute> 클래스입니다. 그렇지 않은 경우이 규칙에서는 경고를에서 표시 하지 마십시오.

## <a name="example-violation"></a>예제 위반

### <a name="description"></a>설명
 다음 예제에서는이 규칙을 위반 하는 속성을 보여 줍니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]

### <a name="comments"></a>설명
 이 규칙 위반 문제를 해결 하려면 메서드 속성을 설정 하거나 배열 대신 컬렉션을 반환 하려면이 속성을 변경 합니다.

## <a name="change-the-property-to-a-method-example"></a>속성 메서드 예제로 변경

### <a name="description"></a>설명
 다음 예제에서는 메서드에 속성을 변경 하 여 위반 문제를 해결 합니다.

### <a name="code"></a>코드
 [!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
 [!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]

## <a name="return-a-collection-example"></a>컬렉션 예제를 반환 합니다.

### <a name="description"></a>설명
 다음 예제에서는 반환 하려면이 속성을 변경 하 여 위반을 해결 한

 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]

## <a name="allowing-users-to-modify-a-property"></a>사용자 속성을 수정할 수 있도록 허용

### <a name="description"></a>설명
 변경할 수 있도록 클래스의 속성을 수정 수 있습니다. 다음 예제에서는이 규칙을 위반 하는 읽기/쓰기 속성을 보여 줍니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
 [!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]

### <a name="comments"></a>설명
 다음 예제에서는 반환 하려면이 속성을 변경 하 여 위반을 해결 한 <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>합니다.

### <a name="code"></a>코드
 [!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
 [!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1024: 적합한 속성을 사용하십시오.](../code-quality/ca1024-use-properties-where-appropriate.md)