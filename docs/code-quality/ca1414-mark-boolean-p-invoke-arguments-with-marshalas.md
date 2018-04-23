---
title: 'CA1414: 부울 P Invoke 인수를 MarshalAs로 표시'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
helpviewer_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
ms.assetid: c0c84cf5-7701-4897-9114-66fc4b895699
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eb956c4a5c19441aaa85539909fca3cc7446fd97
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1414-mark-boolean-pinvoke-arguments-with-marshalas"></a>CA1414: 부울 P/Invoke 인수를 MarshalAs로 표시하십시오.
|||
|-|-|
|TypeName|MarkBooleanPInvokeArgumentsWithMarshalAs|
|CheckId|CA1414|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 플랫폼 호출 메서드 선언을 포함는 <xref:System.Boolean?displayProperty=fullName> 매개 변수 또는 반환 값 이지만 <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName> 특성 매개 변수 또는 반환 값에 적용 되지 않습니다.

## <a name="rule-description"></a>규칙 설명
 플랫폼 비관리 코드에 액세스 메서드를 호출 하 고 사용 하 여 정의 된 `Declare` 키워드 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 또는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>합니다. <xref:System.Runtime.InteropServices.MarshalAsAttribute> 관리 코드와 비관리 코드 간에 데이터 형식을 변환 하는 데 사용 되는 마샬링 동작을 지정 합니다. 와 같은 대부분의 간단한 데이터 형식은 <xref:System.Byte?displayProperty=fullName> 및 <xref:System.Int32?displayProperty=fullName>; 공용 언어 런타임에 올바른 동작을 자동으로 제공, 비관리 코드에서 단일 표현이 및 마샬링 동작을 지정할 필요가 없습니다.

 <xref:System.Boolean> 데이터 형식은 비관리 코드에서 여러 표현이 가지입니다. 경우는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 기본 마샬링 동작을 지정 하지 않으면는 <xref:System.Boolean> 데이터 형식이 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>합니다. 모든 경우에 적합 하지 않는 32 비트 정수입니다. 관리 되지 않는 메서드가에 필요한 부울 표현을 결정 하 고 적절 한 일치 해야 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>합니다. UnmanagedType.Bool는은 항상 4 바이트 Win32 BOOL 형식. C + +에 사용할 UnmanagedType.U1 `bool` 또는 기타 1 바이트 형식입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 적용 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 에 <xref:System.Boolean> 매개 변수 또는 반환 값입니다. 특성의 값을 적절 한 설정 <xref:System.Runtime.InteropServices.UnmanagedType>합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다. 적절 한 기본 마샬링 동작 경우 동작을 명시적으로 지정 하는 코드 보다 쉽게 유지 됩니다.

## <a name="example"></a>예제
 다음 예제에서는 적절 한 것으로 표시 된 메서드를 호출 하는 두 개의 플랫폼 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성입니다.

 [!code-csharp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CSharp/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cs)]
 [!code-vb[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/VisualBasic/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.vb)]
 [!code-cpp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CPP/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cpp)]

## <a name="related-rules"></a>관련된 규칙
 [CA1901: P/Invoke 선언은 이식 가능 해야 합니다.](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)

 [CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정 하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

## <a name="see-also"></a>참고 항목
 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName> [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)