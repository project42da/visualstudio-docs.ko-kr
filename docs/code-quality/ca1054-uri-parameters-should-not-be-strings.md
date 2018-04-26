---
title: 'CA1054: URI 매개 변수는 문자열이면 안 됩니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1054
- UriParametersShouldNotBeStrings
helpviewer_keywords:
- CA1054
- UriParametersShouldNotBeStrings
ms.assetid: 8e99d72b-a658-47a7-8dd5-9784ce2c30b8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 740a3354b9b14bb62dee259c6534ce8065162894
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1054-uri-parameters-should-not-be-strings"></a>CA1054: URI 매개 변수는 문자열이면 안 됩니다.
|||
|-|-|
|TypeName|UriParametersShouldNotBeStrings|
|CheckId|CA1054|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 형식이 이름에 "uri", "Uri", "urn", "Urn", "url" 또는 "Url" 문자열 매개 변수를 사용 하 여 메서드를 선언 하 고 형식을 사용 하는 해당 오버 로드를 선언 하지 않는 한 <xref:System.Uri?displayProperty=fullName> 매개 변수입니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙에서는 매개 변수 이름을 카멜식 대/소문자 규칙에 따라 토큰으로 분할 하 고 각 토큰 "uri", "Uri", "urn", "Urn", "url" 또는 "Url"와 같은지 여부를 확인 합니다. 일치 하는 경우 규칙 uniform resource identifier (URI)을 나타내는 매개 변수를 가정 합니다. URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다. URI의 문자열 표현을 사용 하는 메서드를 해당 오버 로드를 제공 해야의 인스턴스를 사용 하는 <xref:System.Uri> 안전한 방식으로 이러한 서비스를 제공 하는 클래스입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반을 해결 하려면 매개 변수를 변경는 <xref:System.Uri> 입력; 주요 변경 내용입니다. 또는 사용 하는 메서드 오버 로드를 제공는 <xref:System.Uri> ; 매개 변수 줄 바꿈하지 않는 변경 내용입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 매개 변수는 URI를 나타내지 않는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 형식 `ErrorProne`,이 규칙을 위반 하는 형식 하 `SaferWay`, 규칙을 충족 하 합니다.

 [!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1054-uri-parameters-should-not-be-strings_1.cs)]
 [!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1054-uri-parameters-should-not-be-strings_1.vb)]
 [!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1054-uri-parameters-should-not-be-strings_1.cpp)]

## <a name="related-rules"></a>관련된 규칙
 [CA1056: URI 속성은 문자열이면 안 됩니다.](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1055: URI 반환 값은 문자열이면 안 됩니다.](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)

 [CA2234: 문자열 대신 System.Uri 개체를 전달하십시오.](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다.](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)