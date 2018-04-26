---
title: 'CA1406: Visual Basic 6 클라이언트에서 Int64 인수를 사용하지 않습니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
helpviewer_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
ms.assetid: d5d0d3fc-f105-43da-be5b-923ab023309c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e4455373338cda463623c75ff099a1c706f589dc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1406-avoid-int64-arguments-for-visual-basic-6-clients"></a>CA1406: Visual Basic 6 클라이언트에서 Int64 인수를 사용하지 않습니다.
|||
|-|-|
|TypeName|AvoidInt64ArgumentsForVB6Clients|
|CheckId|CA1406|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 특히 표시 유형 구성 요소 개체 모델 (COM)에 표시 된 형식이 선언 멤버 해당 하나는 <xref:System.Int64?displayProperty=fullName> 인수입니다.

## <a name="rule-description"></a>규칙 설명
 Visual Basic 6 COM 클라이언트는 64 비트 정수를 액세스할 수 없습니다.

 기본적으로 다음 COM에 표시 되지만: 어셈블리, public 형식, public 인스턴스 멤버를 공용 형식 및 공용 값 형식의 모든 멤버입니다. 그러나 거짓 긍정을 줄이기 위해이 규칙을 사용 하려면 명시적으로 지정 되어야; 형식의 COM 노출 여부 포함 하는 어셈블리 표시 되어야 합니다는 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 로 설정 `false` 형식으로 표시 해야 하 고는 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 로 설정 `true`합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 매개 변수 형식을 변경 하는 매개 변수 값을 32 비트 정수 계열로 항상 표현할 수에 대 한이 규칙 위반 문제를 해결 하려면 <xref:System.Int32?displayProperty=fullName>합니다. 매개 변수 형식을 변경 하는 매개 변수 값으로는 32 비트 정수 표현할 수 있는 보다 큰 경우 <xref:System.Decimal?displayProperty=fullName>합니다. 둘 다 <xref:System.Single?displayProperty=fullName> 및 <xref:System.Double?displayProperty=fullName> 상위 범위의 정밀도 떨어질는 <xref:System.Int64> 데이터 형식입니다. 멤버를 COM에 표시 되도록 아니며 경우으로 표시 된 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 로 설정 `false`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서 경고를 표시 하지 않는 것이 확실 한 경우 Visual Basic 6 COM 클라이언트 형식을 액세스 하지 않음을 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-csharp[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/CSharp/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.cs)]
 [!code-vb[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/VisualBasic/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA1413: Com 노출 값 형식에 public이 아닌 필드를 사용하지 마십시오.](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

 [CA1407: COM 노출 형식에 정적 멤버를 사용하지 마십시오.](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017: 어셈블리를 ComVisibleAttribute로 표시하십시오.](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>참고 항목
 [비관리 코드와의 상호 운용](/dotnet/framework/interop/index) [Long 데이터 형식](/dotnet/visual-basic/language-reference/data-types/long-data-type)