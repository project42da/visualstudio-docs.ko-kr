---
title: 'CA1703: 리소스 문자열에는 정확한 철자를 사용해야 합니다.'
ms.date: 03/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ResourceStringsShouldBeSpelledCorrectly
- CA1703
helpviewer_keywords:
- CA1703
- ResourceStringsShouldBeSpelledCorrectly
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e8103353fc5d2e0d74b5355259f0e2bc77ddd974
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1703-resource-strings-should-be-spelled-correctly"></a>CA1703: 리소스 문자열에는 정확한 철자를 사용해야 합니다.

|||
|-|-|
|TypeName|ResourceStringsShouldBeSpelledCorrectly|
|CheckId|CA1703|
|범주|Microsoft.Naming|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

리소스 문자열에 Microsoft 맞춤법 검사 라이브러리에서 인식하지 못하는 단어가 하나 이상 있습니다.

## <a name="rule-description"></a>규칙 설명

이 규칙 (복합 단어를 토큰화) 단어로 리소스 문자열을 구문 분석 하 고 각 단어/토큰의 맞춤법을 검사 합니다. 구문 분석 알고리즘에 대 한 정보를 참조 하십시오. [CA1704: 식별자에는 정확한 철자를 사용 해야](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결 하는 방법

이 규칙 위반 문제를 해결 하려면 철자가 또는 사용자 지정 사전에 있는 단어를 추가 하는 완전 한 단어를 사용 합니다. 사용자 지정 사전을 사용 하는 방법에 대 한 정보를 참조 하십시오. [CA1704: 식별자에는 정확한 철자를 사용 해야](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)합니다.

## <a name="change-the-dictionary-language"></a>사전 언어 변경

기본적으로 영어 (en) 버전의 맞춤법 검사기 사용 됩니다. 맞춤법 검사기의 언어를 변경 하려면 다음 중 하나에 특성 추가 하 여 하므로 수행할 수 있습니다 프로그램 *AssemblyInfo.cs* 또는 *AssemblyInfo.vb* 파일:

- 사용 하 여 <xref:System.Reflection.AssemblyCultureAttribute> 위성 어셈블리에 리소스가 있는 경우 문화권을 지정할 수 있습니다.
- 사용 하 여 <xref:System.Resources.NeutralResourcesLanguageAttribute> 지정 하는 *중립 문화권* 코드와 동일한 어셈블리에 리소스가 있는 경우 어셈블리의 합니다.

> [!IMPORTANT]
> 영어 기반 문화권 이외의 문화권을 설정 하는 경우이 코드 분석 규칙은 자동으로 사용할 수 없습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다. 맞춤법이 단어를 사용 하는 새 소프트웨어 라이브러리에 알아보려면 필요한 시간이 줄어듭니다.

## <a name="related-rules"></a>관련된 규칙

- [CA1701: 리소스 문자열 복합 단어는 정확한 대/소문자를 사용해야 합니다.](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1704: 식별자에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA2204: 리터럴의 철자가 맞아야 합니다.](../code-quality/ca2204-literals-should-be-spelled-correctly.md)