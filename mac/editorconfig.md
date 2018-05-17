---
title: EditorConfig
description: EditorConfig 파일을 사용하여 Mac용 Visual Studio에서 일관된 프로젝트 코딩 스타일 활성화.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 26A0DE31-2FBF-4E1B-99FB-083111AA1680
ms.openlocfilehash: 553a8ceeae16b660115ea3c8e32e544e903a72af
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="creating-and-editing-a-custom-editorconfig-file"></a>사용자 지정 EditorConfig 파일 만들기 및 편집

Mac용 Visual Studio에서는 프로젝트 또는 코드베이스에 [EditorConfig](http://editorconfig.org/) 파일을 추가하여 코드베이스에서 작업하는 모든 사람들의 코딩 스타일을 일관적으로 유지할 수 있습니다. EditorConfig 파일에 선언된 설정은 전역 Visual Studio 텍스트 편집기 설정에 우선합니다. 프로젝트 또는 코드베이스 내에서 EditorConfig를 사용하여 프로젝트의 코딩 스타일, 기본 설정 및 경고를 지정할 수 있습니다. 그러면 모든 Mac용 Visual Studio 사용자가 특정 프로젝트의 코딩 방침을 더 쉽게 준수할 수 있습니다.

[EditorConfig](http://editorconfig.org/) 파일은 Visual Studio 2017을 비롯한 여러 IDE 및 코드 편집기에서 지원됩니다. 

## <a name="supported-settings"></a>지원되는 설정

Visual Studio의 편집기는 다음과 같은 [EditorConfig 속성](http://editorconfig.org/#supported-properties)의 핵심 집합을 지원합니다.

- `indent_style`
- `indent_size`
- `tab_width`
- `end_of_line`
- `charset`
- `trim_trailing_whitespace`
- `insert_final_newline`
- `root`

EditorConfig는 또한 C#의 [코드 스타일 서식 지정](https://docs.microsoft.com/visualstudio/ide/editorconfig-code-style-settings-reference)을 지원합니다.

## <a name="add-an-editorconfig-file-to-a-project"></a>프로젝트에 EditorConfig 파일 추가

### <a name="adding-a-new-editorconfig-file"></a>새 EditorConfig 파일 추가

1. Mac용 Visual Studio에서 프로젝트를 엽니다. 파일을 추가하려는 프로젝트 노드를 선택합니다.

2. 프로젝트 노드를 선택한 상태로 메뉴 표시줄의 **파일 > 새 파일...** 로 이동하여 **새 파일** 대화 상자를 엽니다.

3. **기타 > 빈 텍스트 파일**을 선택하고 **이름**에 `.editorconfig`를 지정합니다. **새로 만들기**를 눌러 파일을 만들고 편집기에서 엽니다.

    ![새 파일 대화 상자](media/editorconfig-image1.png)

4. 파일을 편집합니다. 예:

    ```EditorConfig
    # This file is the top-most EditorConfig file
    root = true

    # All Files
    [*]
    indent_style = space
    indent_size = 8
    insert_final_newline = false
    trim_trailing_whitespace = false

    [*.cs]
    csharp_new_line_before_open_brace = none
    ```

4. 파일을 추가할 경우 설정이 자동으로 업데이트되지 않습니다. `.editorconfig` 파일의 설정을 적용하려면 프로젝트 노드를 선택하고 메뉴 표시줄에서 **편집 > 서식 > 문서 서식**을 선택합니다.

    ![문서 서식 메뉴 항목](media/editorconfig-image2.png)

### <a name="adding-an-existing-editorconfig-file"></a>기존 EditorConfig 파일 추가

`.editorconfig` 파일이 이미 포함된 프로젝트 또는 솔루션으로 작업 중인 경우 설정을 적용하기 위해 해야 할 일이 없습니다. 새로운 코드 줄은 EditorConfig 설정에 따라 서식이 지정됩니다. Mac용 Visual Studio는 솔루션 수준에서 `.editorconfig` 파일을 적용하지만 `.`으로 시작하는 파일은 macOS에서 숨겨진 파일이라는 사실 때문에 솔루션 패드에 표시되지 않을 수 있습니다.

기존의 `.editorconfig` 파일을 프로젝트에서 재사용하는 것이 좋습니다. 기존 파일을 추가하려면 먼저 **터미널**에 다음 명령을 입력하여 Finder에서 숨겨진 파일을 표시해야 합니다.

```
$ defaults write com.apple.Finder AppleShowAllFiles true
$ killall Finder
```

`.editorconfig` 파일이 표시되면 프로젝트 노드로 끌어서 놓습니다. 다음 대화 상자가 표시되면 **디렉터리에 파일 복사** 옵션을 선택하고 **확인**을 선택합니다.

![문서 서식 메뉴 항목](media/editorconfig-image3.png)

`.editorconfig` 파일의 설정을 적용하려면 프로젝트 노드를 선택하고 메뉴 표시줄에서 **편집 > 서식 > 문서 서식**을 선택합니다.

## <a name="editing-an-editorconfig-file"></a>EditorConfig 파일 편집

EditorConfig 파일은 직관적인 파일 레이아웃을 사용하여 설정을 지정합니다. 이전 예를 사용한 이에 대한 설명이 아래에 나와 있습니다.


```EditorConfig
# This file is the top-most EditorConfig file
root = true

# All Files
[*]
indent_style = space
indent_size = 4
insert_final_newline = false
trim_trailing_whitespace = false

[*.cs]
csharp_new_line_before_open_brace = none
```

`root`를 `true`로 설정하면 [EditorConfig 설정 무시](#override-editorconfig-settings) 섹션에 설명된 것처럼 이 파일에 코드베이스의 최상위 파일 플래그가 지정되고, 프로젝트의 모든 상위 `.editorconfig` 파일이 무시됩니다.

각 섹션은 꺾쇠 괄호(**[ ]**)로 표시되며, 다음 속성과 관련된 파일 형식에 대한 정보를 나타냅니다.

위의 예에서 일부 설정은 프로젝트의 모든 파일에 적용되며, 다른 설정은 C# 파일에만 추가됩니다. 아래 스크린샷은 `.editorconfig` 설정 적용 전후를 보여줍니다.

**이전**:

![editorconfig 설정이 적용되기 전](media/editorconfig-image4.png)

**이후**:

![editorconfig 설정이 적용된 후](media/editorconfig-image5.png)

사용 가능한 EditorConfig 설정에 대한 자세한 내용은 [EditorConfig에 대한 .NET 코딩 규칙 설정](https://docs.microsoft.com/visualstudio/ide/editorconfig-code-style-settings-reference) 아티클과 공식 문서의 [지원되는 속성](http://editorconfig.org/#supported-properties) 섹션을 참조하세요.

## <a name="override-editorconfig-settings"></a>EditorConfig 설정 재정의

각 솔루션에는 `.editorconfig` 파일이 여러 개 있을 수 있습니다. Mac용 Visual Studio는 솔루션의 위에서 아래로 `.editorconfig` 파일을 읽으면서 설정을 추가하고 재정의합니다. 즉, 사용자가 편집하고 있는 파일과 _가장 가까운_ `.editorconfig`의 설정이 우선하게 됩니다. 

모든 상위 수준 `.editorconfig` 파일에서 이 코드베이스 부분에 적용된 설정이 _없음_을 확인하려면 `root=true` 속성을 하위 수준 `.editorconfig` 파일의 최상위에 추가합니다.

```EditorConfig
# top-most EditorConfig file
root = true
```