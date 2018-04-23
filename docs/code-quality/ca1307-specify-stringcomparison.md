---
title: 'CA1307: StringComparison 지정'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ef2f8dbb265f0e5c82f2ea0adefc35d0721b4bd
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307: StringComparison 지정
|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|범주|Microsoft.Globalization|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 문자열 비교 작업을 설정 하지 않는 메서드 오버 로드를 사용 하 여 한 <xref:System.StringComparison> 매개 변수입니다.

## <a name="rule-description"></a>규칙 설명
 대부분의 문자열 가장 중요 한 작업의 <xref:System.String.Compare%2A> 및 <xref:System.String.Equals%2A> 메서드를 허용 하는 오버 로드를 제공는 <xref:System.StringComparison> 열거형 값을 매개 변수로 합니다.

 때마다는 오버 로드가 있으면 해당 하나는 <xref:System.StringComparison> 매개 변수를이 매개 변수를 사용 하지 않는 오버 로드를 대신 사용 해야 합니다. 이 매개 변수를 명시적으로 설정 하면 코드 방식은 보다 명확 해지고 유지 관리가 더 용이 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하는 오버 로드를 문자열 비교 방법 변경는 <xref:System.StringComparison> 열거형을 매개 변수로 합니다. 예: 변경 `String.Compare(str1, str2)` 를 `String.Compare(str1, str2, StringComparison.Ordinal)`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 라이브러리 또는 응용 프로그램은 제한 된 로컬 사용자 에게만 되며 따라서 지역화 되지 않는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="see-also"></a>참고 항목
 [전역화 경고](../code-quality/globalization-warnings.md) [CA1309: 서 수 StringComparison을 사용 하 여](../code-quality/ca1309-use-ordinal-stringcomparison.md)