---
title: "EditorConfig에 대한 .NET 명명 규칙 | Microsoft Docs"
ms.custom: 
ms.date: 11/20/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- naming conventions [EditorConfig]
- EditorConfig naming conventions
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.workload: multiple
ms.openlocfilehash: 2719ecd60a68de795c51ec4363a9130e4da9019c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="naming-conventions-for-editorconfig"></a>EditorConfig에 대한 명명 규칙

명명 규칙은 클래스, 속성 및 메서드와 같은 코드 요소의 이름을 지정합니다. 예를 들어 공용 멤버가 대문자로 시작해야 하고 비동기 메서드가 "Async"로 끝나야 한다고 지정할 수 있습니다. [.editorconfig 파일](../ide/create-portable-custom-editor-options.md)에서 이러한 규칙을 지정하여 적용할 수 있습니다. 명명 규칙 위반은 규칙에서 선택한 심각도에 따라 오류 목록 또는 이름의 제안 중 하나에서 표시될 수 있습니다. 위반을 확인하기 위해 프로젝트를 빌드하지 않아도 됩니다.

명명 규칙은 .editorconfig 파일에서 가장 구체적인 규칙부터 가장 덜 구체적인 규칙으로 정렬되어야 합니다. 적용할 수 있는 첫 번째 규칙은 적용되는 유일한 규칙이 됩니다.

각 명명 규칙에서는 아래에서 설명한 속성을 사용하여 적용할 기호, 명명 스타일 및 규칙에 적용할 심각도를 지정해야 합니다. 속성의 순서는 중요하지 않습니다.

시작하려면 규칙 전체를 설명하기 위해 필요한 각각의 속성에서 사용할 명명 규칙에 제목을 선택합니다. 예를 들어 `public_members_must_be_capitalized`는 명명 규칙에 적합한 설명 이름입니다. 다음 섹션에서는 **<namingRuleTitle\>**로 선택한 제목을 참조합니다.

## <a name="symbols"></a>기호

먼저 명명 규칙을 적용할 기호 그룹을 식별합니다. 이 속성의 형식은 다음과 같습니다.

`dotnet_naming_rule.<namingRuleTitle>.symbols = <symbolTitle>`

**<symbolTitle\>** 값을 설명 제목으로 바꿔서 기호 그룹에 이름을 지정합니다(예: `public_symbols`). 규칙을 적용할 기호를 설명하는 세 개의 속성 이름(기호의 종류, 액세스 가능성 수준 및 한정자)에서 **<symbolTitle\>** 값을 사용합니다.

### <a name="kinds-of-symbols"></a>기호의 종류

명명 규칙을 적용할 기호의 종류를 설명하려면 다음과 같은 형식으로 속성을 지정합니다.

`dotnet_naming_symbols.<symbolTitle>.applicable_kinds = <values>`

허용 가능한 값은 아래와 같으며, 이러한 값을 쉼표로 구분하여 여러 값을 지정할 수 있습니다.

- \*(모든 기호를 지정하려면 이 값을 사용합니다.)
- 클래스
- struct
- interface(인터페이스)
- enum
- 속성
- 메서드
- 필드(field)
- 이벤트(event)
- 대리자(delegate)
- 매개 변수

### <a name="accessibility-levels-of-symbols"></a>기호의 액세스 가능성 수준

명명 규칙을 적용하려는 기호의 액세스 가능성 수준을 설명하려면 다음과 같은 형식으로 속성 이름을 지정합니다.

`dotnet_naming_symbols.<symbolTitle>.applicable_accessibilities = <values>`

허용 가능한 값은 아래와 같으며, 이러한 값을 쉼표로 구분하여 여러 값을 지정할 수 있습니다.

- \*(모든 액세스 가능성 수준을 지정하려면 이 값을 사용합니다.)
- public
- internal or friend
- private
- protected
- protected\_internal or protected_friend

> [!NOTE]
> 액세스 가능성 수준을 명명 규칙의 일부로 지정해야 합니다. 그렇지 않으면 명명 규칙이 무시될 수 있습니다.

### <a name="symbol-modifiers"></a>기호 한정자

명명 규칙을 적용하려는 기호의 한정자를 설명하려면 다음과 같은 형식으로 속성 이름을 지정합니다.

`dotnet_naming_symbols.<symbolTitle>.required_modifiers = <values>`

허용 가능한 값은 아래와 같으며, 이러한 값을 쉼표로 구분하여 여러 값을 지정할 수 있습니다.

- abstract or must_inherit
- async
- const
- readonly
- static or shared

`required_modifiers`는 선택적 속성입니다. 이 속성을 생략하는 경우 명명 규칙이 모든 한정자에 적용됩니다.

## <a name="style"></a>스타일

이제 명명 규칙을 적용할 기호 그룹을 식별했으므로 명명 스타일을 설명해야 합니다. 스타일은 이름에 특정 접두사 또는 특정 접미사를 사용거나 이름의 개별 단어를 특정 기호로 분리하도록 할 수 있습니다. 대/소문자 스타일을 지정할 수도 있습니다. 이 스타일의 형식은 다음과 같습니다.

`dotnet_naming_rule.<namingRuleTitle>.style = <styleTitle>`

**<styleTitle\>** 값을 설명 제목으로 바꾸어 이름의 스타일을 지정할 수 있습니다(예: `first_word_upper_case_style`). 명명 스타일(접두사, 접미사, 단어 구분 문자 및 대/소문자)을 설명하는 속성 이름에서 **<styleTitle\>** 값을 사용합니다. 스타일을 설명하는 이러한 속성을 하나 이상 사용합니다.

### <a name="require-a-prefix"></a>접두사 필요

기호 이름이 특정 문자로 시작해야 하도록 지정하려면 이 속성을 사용합니다.

`dotnet_naming_style.<styleTitle>.required_prefix = <prefix>`

### <a name="require-a-suffix"></a>접미사 필요

기호 이름이 특정 문자로 끝나야 하도록 지정하려면 이 속성을 사용합니다.

`dotnet_naming_style.<styleTitle>.required_suffix = <suffix>`

### <a name="require-a-certain-word-separator"></a>특정 단어 구분 기호 필요

기호의 개별 단어가 특정 문자로 구분되어야 하도록 지정하려면 이 속성을 사용합니다.

`dotnet_naming_style.<styleTitle>.word_separator = <separator character>`

### <a name="require-a-capitalization-style"></a>대/소문자 스타일 필요

기호 이름에 특정 대/소문자 스타일을 지정하려면 이 속성을 사용합니다.

`dotnet_naming_style.<styleTitle>.capitalization = <value>`

이 속성에 허용될 수 있는 값은 다음과 같습니다.

- pascal_case
- camel_case
- first\_word_upper
- all\_upper
- all_lower

> [!NOTE]
> 명명 스타일의 일부로 대/소문자 스타일을 지정해야 하고, 그렇지 않으면 명명 스타일이 무시될 수 있습니다.

## <a name="severity"></a>심각도

명명 규칙의 위반 심각도를 지정하려면 다음과 같은 형식으로 속성을 지정합니다.

`dotnet_naming_rule.<namingRuleTitle>.severity = <value>`

다음 표에서는 허용될 수 있는 심각도 값 및 해당 의미를 보여줍니다.

심각도 | 효과
------------ | -------------
none or silent | 이 스타일을 따르지 않을 경우 사용자에게 아무 것도 표시되지 않지만 자동 생성 코드는 이 스타일을 따릅니다.
suggestion | 이 스타일을 따르지 않을 경우 처음 두 문자에 점선이 밑줄로 표시되어 사용자에게 제안으로 표시됩니다. 컴파일 시간에 영향을 주지 않습니다.
경고 | 이 스타일을 따르지 않을 경우 오류 목록에서 컴파일러 경고가 표시됩니다.
오류 | 이 스타일을 따르지 않을 경우 오류 목록에서 컴파일러 오류가 표시됩니다.

> [!NOTE]
> 명명 규칙 위반을 확인하기 위해 프로젝트를 빌드하지 않아도 됩니다. 코드가 편집되면 오류 목록 또는 제안 중 하나로 표시됩니다.

## <a name="example"></a>예

다음 .editorconfig 파일은 공용 속성, 메서드, 필드, 이벤트 및 대리자를 대문자로 시작하도록 지정하는 명명 규칙을 포함하고 있습니다. 이 명명 규칙은 값을 구분하기 위해 쉼표를 사용하여 규칙을 적용하는 여러 종류의 기호를 지정합니다.

```EditorConfig
# Public members must be capitalized (public_members_must_be_capitalized)
[*.{cs,vb}]
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

다음 스크린샷에서는 편집기에서 이 명명 규칙의 영향을 보여줍니다. 두 공용 변수의 이름은 첫 번째 문자를 대문자로 시작하지 않고 지정되었습니다. 한 변수는 `const`이고 다른 변수는 `readonly`입니다. 명명 규칙이 *readonly* 기호에만 적용되므로 `readonly` 변수는 명명 규칙 제안만을 보여줍니다.

![명명 규칙 제안](media/editorconfig-naming-rule-suggestion.png)

이제 `warning`에 대한 위반 심각도를 변경하겠습니다.

```EditorConfig
dotnet_naming_rule.public_members_must_be_capitalized.severity = warning
```

이름 위반 하에서 제안을 확인하는 대신 코드 파일을 닫고 다시 여는 경우 오류 목록에서 녹색 물결 및 경고가 표시됩니다.

![명명 규칙 경고](media/editorconfig-naming-rule-warning.png)

## <a name="see-also"></a>참고 항목

[.NET 언어 및 서식 지정 규칙](../ide/editorconfig-code-style-settings-reference.md)  
[휴대용, 사용자 지정 편집기 옵션 만들기](../ide/create-portable-custom-editor-options.md)