---
title: 'CA1405: COM 노출 형식의 기본 형식은 COM 노출이어야 합니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
helpviewer_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ac8412e242f7d69ea657d5b7f74fa83ffbff5acc
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405: COM 노출 형식의 기본 형식은 COM 노출이어야 합니다.
|||
|-|-|
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|
|CheckId|CA1405|
|범주|Microsoft.Interoperability|
|변경 수준|DependsOnFix|

## <a name="cause"></a>원인
 구성 요소 개체 모델 (COM) 표시 유형 COM 노출 되지 않은 형식에서 파생 됩니다.

## <a name="rule-description"></a>규칙 설명
 COM 노출 형식이 새 버전의 구성원을 추가 하면 현재 버전에 바인딩되는 COM 클라이언트가 중단을 방지 하기 위해 엄격한 지침 준수 해야 합니다. COM에 표시 되는 형식의 새 멤버를 추가할 때 이러한 COM 버전 관리 규칙을 준수 하지 않아도 가정 합니다. 하는 경우 COM 노출 형식 없는 형식에서 파생 되 고의 클래스 인터페이스를 노출 <xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName> 또는 <xref:System.Runtime.InteropServices.ClassInterfaceType> (기본값), 기본 형식의 모든 public 멤버 (표시 되어 있지 않다면 특히 com 보이지 않는는 중복 됩니다) COM에 노출 됩니다. 이후 버전에서 새 멤버를 추가 하는 기본 형식, 파생 된 형식의 클래스 인터페이스에 바인딩되는 모든 COM 클라이언트가 손상 될 수 있습니다. COM 노출 형식을 줄이기 위해 COM 클라이언트의 COM 노출 형식에서 파생 되어야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 COM 노출 기본 형식 또는 파생된 형식인 COM 보이지 않는 이어야 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]

## <a name="see-also"></a>참고 항목
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName> [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)