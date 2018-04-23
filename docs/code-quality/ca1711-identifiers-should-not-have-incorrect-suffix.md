---
title: 'CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 13160a8056c8fb4ec824d84c132fe87a7b565f27
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.
|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 식별자에 잘못 된 접미사가 있습니다.

## <a name="rule-description"></a>규칙 설명
 규칙에 따라 특정 기본 형식을 확장 하거나 특정 인터페이스 또는 이러한 형식에서 파생 된 형식을 구현 하는 형식의 이름만 예약 된 특정 접미사로 끝나야 합니다. 다른 형식 이름에는 이러한 예약된 접미사를 사용하면 안 됩니다.

 다음 표에 예약 된 접미사 및 기본 형식, 인터페이스와 연결 되어 있습니다.

|접미사|기본 형식/인터페이스|
|------------|--------------------------|
|특성|<xref:System.Attribute?displayProperty=fullName>|
|컬렉션|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|사전|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|이벤트 처리기|이벤트 처리기 대리자|
|예외|<xref:System.Exception?displayProperty=fullName>|
|사용 권한|<xref:System.Security.IPermission?displayProperty=fullName>|
|Queue|<xref:System.Collections.Queue?displayProperty=fullName>|
|스택|<xref:System.Collections.Stack?displayProperty=fullName>|
|스트림|<xref:System.IO.Stream?displayProperty=fullName>|

 다음 접미사 해야 또한 **하지** 사용할 수 있습니다.

-   대리자

-   Enum

-   -Impl '코어'를 대신 사용 합니다.

-   동일한 유형의 이전 버전에서 구분 하기 위해 Ex 또는 유사한 접미사

 명명 규칙은 공통 된 모양을 라이브러리에 대 한 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요 하 고 관리 되는 코드를 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 하는 신뢰성이 향상를 배워야 할 필요성이 줄어듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 형식 이름에서 접미사를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 접미사가 응용 프로그램 도메인에서 명확한 의미를 갖지 않는 한 이 규칙의 경고를 숨기지 마십시오.

## <a name="related-rules"></a>관련된 규칙
 [CA1710: 식별자에는 올바른 접미사를 사용해야 합니다.](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## <a name="see-also"></a>참고 항목
 [특성](/dotnet/standard/design-guidelines/attributes) [처리 및 이벤트를 발생 시키기](/dotnet/standard/events/index)