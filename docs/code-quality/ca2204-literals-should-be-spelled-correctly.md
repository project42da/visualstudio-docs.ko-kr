---
title: 'CA2204: 리터럴을 철자가 | Microsoft Docs'
ms.date: 03/28/2018
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- Literals should be spelled correctly
- CA2204
- LiteralsShouldBeSpelledCorrectly
helpviewer_keywords:
- CA2204
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b57f4b30ffcebf6c51aa8741a21392ea29719a3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2204-literals-should-be-spelled-correctly"></a>CA2204: 리터럴의 철자가 맞아야 합니다.

|||
|-|-|
|TypeName|LiteralsShouldBeSpelledCorrectly|
|CheckId|CA2204|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

리터럴 문자열은 지역화할 수 있는 매개 변수에 대해 또는 지역화할 수 있는 속성에는 인수로 전달 하 고 문자열에 Microsoft 맞춤법 검사 라이브러리에서 인식 하지 못하는 단어가 하나 이상 포함 되어 있습니다.

## <a name="rule-description"></a>규칙 설명

매개 변수 또는 한 경우이 속성에 값으로 전달 되는 리터럴 문자열을 검사 하는이 규칙 또는 다음과 같은 경우 true입니다.

- <xref:System.ComponentModel.LocalizableAttribute> 매개 변수 또는 속성의 특성은 설정을 true로 합니다.

- "Text", "Message" 또는 "캡션" 매개 변수 또는 속성 이름에 포함 되어 있습니다.

- 에 전달 된 문자열 변수의 이름을 <xref:System.Console.Write%2A> 또는 <xref:System.Console.WriteLine> 메서드는 "value" 또는 "format"입니다.

이 규칙은 복합 단어를 토큰화 리터럴 문자열을 구문 분석 하 고 각 단어 또는 토큰의 맞춤법을 검사 합니다. 구문 분석 알고리즘에 대 한 정보를 참조 하십시오. [CA1704: 식별자에는 정확한 철자를 사용 해야](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)합니다.

## <a name="language"></a>언어

맞춤법 검사기는 현재 문화권이 영어 기반 사전에 대해서만 검사합니다. 추가 하 여 프로젝트 파일에서 프로젝트의 문화권을 변경할 수 있습니다는 **CodeAnalysisCulture** 요소입니다.

예를 들어:

```xml
<Project ...>
  <PropertyGroup>
    <CodeAnalysisCulture>en-AU</CodeAnalysisCulture>
```

> [!IMPORTANT]
> 영어 기반 문화권 이외의 문화권을 설정 하는 경우이 코드 분석 규칙은 자동으로 사용할 수 없습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결 하는 방법

이 규칙 위반 문제를 해결 하는 word의 철자를 수정 하거나 사용자 지정 사전에 단어를 추가 합니다. 사용자 지정 사전을 사용 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 코드 분석 사전 사용자 지정](../code-quality/how-to-customize-the-code-analysis-dictionary.md)합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다. 올바르게 맞춤법이 단어를 새 소프트웨어 라이브러리에 필요한 배워야 할 필요성이 줄어듭니다.

## <a name="related-rules"></a>관련된 규칙

- [CA1704: 식별자에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA1703: 리소스 문자열에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)