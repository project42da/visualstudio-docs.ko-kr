---
title: 'CA1309: 서수 StringComparison을 사용하십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseOrdinalStringComparison
- CA1309
helpviewer_keywords:
- UseOrdinalStringComparison
- CA1309
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 964dfee8b8ed78de76ead4ee5eda63fe0a49a72c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309: 서수 StringComparison을 사용하십시오.
|||
|-|-|
|TypeName|UseOrdinalStringComparison|
|CheckId|CA1309|
|범주|Microsoft.Globalization|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 비언어 문자열 비교 작업을 설정 하지 않습니다는 <xref:System.StringComparison> 매개 변수를 **서** 또는 **OrdinalIgnoreCase**합니다.

## <a name="rule-description"></a>규칙 설명
 대부분의 문자열 작업, 가장 중요 한는 <xref:System.String.Compare%2A?displayProperty=fullName> 및 <xref:System.String.Equals%2A?displayProperty=fullName> 메서드에서 이제 이와 같은 허용 하는 오버 로드는 <xref:System.StringComparison?displayProperty=fullName> 열거형 값을 매개 변수로 합니다.

 중 하나를 지정 하는 경우 **StringComparison.Ordinal** 또는 **StringComparison.OrdinalIgnoreCase**, 문자열 비교 비언어 됩니다. 즉, 자연 언어와 관련 된 기능에는 비교 작업을 결정할 때 무시 됩니다. 즉, 결정 한 단순 바이트 비교에 기반 하 고 문화권에 의해 매개 변수화 된 대/소문자 구분 또는 동일성 테이블이 무시 합니다. 매개 변수를 명시적으로 설정 하 여 결과적으로 **StringComparison.Ordinal** 또는 **StringComparison.OrdinalIgnoreCase**, 코드 종종 속도 향상, 정확성, 증가 매핑되며 안정적 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 변경 문자열 비교 방법을 허용 하는 오버 로드는 <xref:System.StringComparison?displayProperty=fullName> 열거형을 매개 변수로 지정 하 고 **서 수** 또는 **OrdinalIgnoreCase**합니다. 예를 들어 변경 `String.Compare(str1, str2)` 를 `String.Compare(str1, str2, StringComparison.Ordinal)`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 라이브러리 또는 응용 프로그램의 현재 문화권 의미 체계를 사용 해야 하거나 제한 된 로컬 사용자 에게만 위한 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="see-also"></a>참고 항목
 [전역화 경고](../code-quality/globalization-warnings.md) [CA1307: StringComparison 지정](../code-quality/ca1307-specify-stringcomparison.md)