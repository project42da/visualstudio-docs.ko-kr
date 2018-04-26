---
title: 'CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1057
- StringUriOverloadsCallSystemUriOverloads
helpviewer_keywords:
- StringUriOverloadsCallSystemUriOverloads
- CA1057
ms.assetid: ef1e983e-9ca7-404b-82d7-65740ba0ce20
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 63386e73cee4d2e0c1c34f31f0042312fef4869f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1057-string-uri-overloads-call-systemuri-overloads"></a>CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다.
|||
|-|-|
|TypeName|StringUriOverloadsCallSystemUriOverloads|
|CheckId|CA1057|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 형식이 선언 된 문자열 매개 변수로 다른 메서드 오버 로드는 <xref:System.Uri?displayProperty=fullName> 매개 변수 및 문자열 매개 변수를 사용 하는 오버 로드는 오버 로드를 호출 하지 않습니다는 <xref:System.Uri> 매개 변수입니다.

## <a name="rule-description"></a>규칙 설명
 오버 로드만 다르므로 문자열 /<xref:System.Uri> 매개 변수를 문자열 uniform resource identifier (URI)를 나타내기 위해 간주 됩니다. URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다. <xref:System.Uri> 클래스 안전한 방식으로 이러한 서비스를 제공 합니다. 장점을 이용 하는 <xref:System.Uri> 클래스 문자열 오버 로드를 호출 해야는 <xref:System.Uri> 문자열 인수를 사용 하 여 오버 로드 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 인스턴스를 만들 수 있도록 URI의 문자열 표현을 사용 하는 메서드를 다시 구현는 <xref:System.Uri> 클래스 문자열 인수를 사용 하 고 다음 전달는 <xref:System.Uri> 개체를 포함 하는 오버 로드는 <xref:System.Uri> 매개 변수입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 문자열 매개 변수는 URI를 나타내지 않는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 오버 로드를 올바로 구현 된 문자열을 보여 줍니다.

 [!code-csharp[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/CSharp/ca1057-string-uri-overloads-call-system-uri-overloads_1.cs)]
 [!code-cpp[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/CPP/ca1057-string-uri-overloads-call-system-uri-overloads_1.cpp)]
 [!code-vb[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/VisualBasic/ca1057-string-uri-overloads-call-system-uri-overloads_1.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA2234: 문자열 대신 System.Uri 개체를 전달하십시오.](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1056: URI 속성은 문자열이면 안 됩니다.](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: URI 매개 변수는 문자열이면 안 됩니다.](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA1055: URI 반환 값은 문자열이면 안 됩니다.](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)