---
title: "Visual Studio에서 EditorConfig 설정 사용 | Microsoft Docs"
ms.custom: 
ms.date: 12/13/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editorconfig [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: 65eafeab083b85fb7e872adabf97f5497cc62291
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>EditorConfig를 사용하여 휴대용, 사용자 지정 편집기 설정 만들기

Visual Studio 2017에서는 프로젝트 또는 코드베이스에 [EditorConfig](http://editorconfig.org/) 파일을 추가하여 코드베이스에서 작업하는 모든 사람들의 코딩 스타일을 일관적으로 유지할 수 있습니다. EditorConfig 설정은 전역 Visual Studio 텍스트 편집기 설정에 우선합니다. 따라서 해당 프로젝트와 관련된 텍스트 편집기 설정을 사용하도록 각 코드베이스를 조정할 수 있습니다. Visual Studio **옵션** 대화 상자에서 사용자 고유의 개인 편집기 기본 설정을 지정할 수 있습니다. 사용자가 .editorconfig 파일 없이 코드베이스에서 작업을 수행하거나 .editorconfig 파일이 특정 설정을 재정의하지 않은 경우 이러한 설정이 적용됩니다. 이러한 기본 설정의 예로 들여쓰기 스타일(탭 또는 공백)을 들 수 있습니다.

Visual Studio를 포함하여 다양한 코드 편집기와 IDE에서 EditorConfig 설정이 지원됩니다. 코드를 이용하여 휴대할 수 있는 구성 요소이며 Visual Studio 외부에서도 코딩 스타일을 적용할 수 있습니다.

> [!NOTE]
> Visual Studio에서 프로젝트에 EditorConfig 파일을 추가할 때 문서의 서식을 지정(**편집** > **고급** > **문서 서식** 또는 **Ctrl**+**K**, **Ctrl**+**D**)하지 않으면 기존 코드의 서식이 변경되지 않습니다. 하지만 새로운 코드 줄은 EditorConfig 설정에 따라 서식이 지정됩니다.

## <a name="coding-consistency"></a>코딩 일관성

EditorConfig 파일의 설정을 사용하면 사용하는 편집기나 IDE에 관계없이 코드베이스에서 들여 쓰기 스타일, 탭 너비, 줄의 끝 문자, 인코딩 등과 같은 일관된 코딩 스타일과 설정을 유지할 수 있습니다. 예를 들어 C#으로 코딩하는 경우 코드베이스에 들여쓰기가 항상 공백 문자 5개로 구성되고, 문서에서 UTF-8 인코딩을 사용하고, 각 줄이 항상 CR/LF로 끝나도록 하는 규칙이 있다면 .editorconfig 파일을 해당 규칙에 따라 구성할 수 있습니다.

개인 프로젝트에서 사용하는 코딩 규칙과 팀 프로젝트에서 사용되는 규칙이 서로 다를 수 있습니다. 예를 들어, 코딩할 때 들여쓰기를 하면 탭 문자가 추가되는 것을 선호할 수 있습니다. 그러나 팀에서는 들여쓰기 시 탭 문자 대신 공백 문자 4개가 추가되는 것을 선호할 수 있습니다. EditorConfig 파일을 통해 각 시나리오에 맞게 구성하면 이 문제를 해결할 수 있습니다.

설정은 코드베이스의 파일에 포함되므로 해당 코드베이스와 함께 전송됩니다. EditorConfig 규격 편집기에서 코드 파일을 열기만 하면 텍스트 편집기 설정이 구현됩니다. EditorConfig 파일에 대한 자세한 내용은 [EditorConfig.org](http://editorconfig.org/) 웹 사이트를 참조하세요.

## <a name="supported-settings"></a>지원되는 설정

Visual Studio의 편집기는 다음과 같은 [EditorConfig 속성](http://editorconfig.org/#supported-properties)의 핵심 집합을 지원합니다.

- indent_style
- indent_size
- tab_width
- end\_of_line
- 문자 집합
- trim\_trailing_whitespace
- insert\_final_newline
- 루트

EditorConfig 편집기 설정은 XML을 제외하고 Visual Studio가 지원하는 모든 언어에서 지원됩니다. 또한 EditorConfig는 C# 및 Visual Basic에 대해 [코드 스타일](../ide/editorconfig-code-style-settings-reference.md) 및 [명명](../ide/editorconfig-naming-conventions.md) 규칙을 지원합니다.

## <a name="adding-and-removing-editorconfig-files"></a>EditorConfig 파일 추가 및 제거

EditorConfig 파일을 프로젝트나 코드베이스에 추가해도 기존 스타일이 새로운 스타일로 변환되지 않습니다. 예를 들어 파일에 탭으로 서식이 지정된 들여쓰기가 있는 경우 공백으로 들여쓰기가 적용되는 EditorConfig 파일을 추가해도 들여쓰기 문자가 공백으로 자동 변환되지 않습니다. 하지만 새로운 코드 줄은 EditorConfig 파일에 따라 서식이 지정됩니다. 또한 문서의 서식을 지정(**편집** > **고급** > **문서 서식** 또는 **Ctrl**+**K**, **Ctrl**+**D**)하는 경우 EditorConfig 파일의 설정이 기존 코드 줄에 적용됩니다.

프로젝트나 코드베이스에서 EditorConfig 파일을 제거하면 열려있는 코드 파일을 닫았다가 다시 열어야 새로운 코드 줄에 대해 전역 편집기 설정으로 돌아갑니다.

### <a name="to-add-an-editorconfig-file-to-a-project-or-solution"></a>프로젝트 또는 솔루션에 EditorConfig 파일을 추가하려면 다음을 수행합니다.

1. Visual Studio에서 프로젝트 또는 솔루션을 엽니다. .editorconfig 설정을 솔루션의 모든 프로젝트에 적용할지 아니면 하나에만 적용할지에 따라 프로젝트 또는 솔루션 노드 중 하나를 선택합니다. 프로젝트 또는 솔루션에서 폴더를 선택하여 .editorconfig 파일을 추가합니다.

1. 메뉴 모음에서 **프로젝트** > **새 항목 추가...**를 선택하거나 **Ctrl**+**Shift**+**A**를 누릅니다.

   **새 항목 추가** 대화 상자가 열립니다.

1. 왼쪽의 범주에서 **일반**을 선택한 다음, **텍스트 파일** 템플릿을 선택합니다. **이름** 텍스트 상자에 `.editorconfig`를 입력한 다음 **추가**를 선택합니다.

   .editorconfig 파일이 솔루션 탐색기에 표시되고 편집기에서 열립니다.

   ![솔루션 탐색기의 .editorconfig 파일](media/editorconfig-in-solution-explorer.png)

1. 다음과 같이 원하는 대로 파일을 편집합니다.

   ```EditorConfig
   root = true

   [*.{cs,vb}]
   indent_size = 4
   trim_trailing_whitespace = true

   [*.cs]
   csharp_new_line_before_open_brace = methods
   ```

또는 [EditorConfig 언어 서비스 확장](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig)을 설치할 수 있습니다. 이 확장을 설치한 후, 마우스 오른쪽 단추를 클릭하거나 솔루션 탐색기의 솔루션 노드, 프로젝트 노드 또는 폴더의 바로 가기 메뉴에서 **추가** > **.editorconfig 파일**을 선택하면 됩니다.

![확장을 사용하여 .editorconfig 파일 추가](media/editorconfig-extension-add.png)

## <a name="override-editorconfig-settings"></a>EditorConfig 설정 재정의

파일 계층 구조의 폴더에 .editorconfig 파일을 추가하는 경우 해당 설정이 이 수준과 그 아래에 있는 모든 파일에 적용됩니다. 코드베이스의 다른 부분과는 다른 규칙을 사용하는, 특정 프로젝트, 코드베이스 또는 코드베이스 일부에 대한 EditorConfig 설정을 재정의할 수 있습니다. 이는 다른 위치에서 코드를 통합하면서 해당 규칙을 변경하지 않으려는 경우에 유용할 수 있습니다.

EditorConfig 설정의 일부 또는 전부를 재정의하려면 이러한 재정의된 설정을 적용할 파일 계층 구조 수준에서 .editorconfig 파일을 추가합니다. 새 EditorConfig 파일 설정은 동일한 수준 및 모든 하위 디렉터리의 파일에 적용됩니다.

![EditorConfig 계층 구조](../ide/media/vside_editorconfig_hierarchy.png)

설정의 전부가 아닌 일부를 재정의하려는 경우 .editorconfig 파일에서 해당 설정만 지정하면 됩니다. 하위 수준 파일에 명시적으로 나열된 속성만 재정의됩니다. 상위 수준 .editorconfig 파일의 다른 설정은 계속 적용됩니다. _모든_ 상위 수준에서 이 코드베이스 부분에 적용된 설정이 _없음_을 확인하려면 ```root=true``` 속성을 하위 수준 .editorconfig 파일에 추가합니다.

```EditorConfig
# top-most EditorConfig file
root = true
```

EditorConfig 파일은 위쪽에서 아래쪽으로 읽으며 가장 가까운 EditorConfig 파일을 마지막으로 읽습니다. 일치하는 EditorConfig 섹션의 규칙이 읽는 순서로 적용되므로, 가까운 파일의 규칙이 우선 적용됩니다.

## <a name="editing-editorconfig-files"></a>EditorConfig 파일 편집

Visual Studio는 .editorconfig 파일을 편집할 수 있는 몇 가지 IntelliSense를 제공합니다.

![.editorconfig 파일의 IntelliSense](media/editorconfig-intellisense-no-extension.png)

EditorConfig 파일을 편집한 후 새 설정을 적용하려면 코드 파일을 다시 로드해야 합니다.

수많은 .editorconfig 파일을 편집하는 경우 [EditorConfig 언어 서비스 확장](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig)이 유용할 수 있습니다. 이 확장의 기능 중 일부에는 구문 강조 표시, 향상된 IntelliSense, 유효성 검사 및 코드 서식 지정이 포함되어 있습니다.

![EditorConfig 언어 서비스 확장을 사용한 IntelliSense](media/editorconfig-intellisense.png)

## <a name="example"></a>예

다음은 .editorconfig 파일을 프로젝트에 추가하기 전과 후의 C# 코드 조각 들여쓰기 상태를 보여주는 예입니다. Visual Studio 텍스트 편집기에 대한 **옵션** 대화 상자의 **탭** 설정은 **Tab** 키를 누를 때 공백 문자를 생성하도록 설정되어 있습니다.

![텍스트 편집기 탭 설정](../ide/media/vside_editorconfig_tabsetting.png)

예상대로 다음 줄에서 **Tab** 키를 누르면 공백 문자 4개가 추가되어 줄이 들여쓰기됩니다.

![EditorConfig를 사용하기 전의 코드](../ide/media/vside_editorconfig_before.png)

다음 콘텐츠를 포함하여 .editorconfig라는 새 파일을 프로젝트에 추가합니다. `[*.cs]` 설정은 이 변경 내용이 이 프로젝트의 C# 코드 파일에만 적용된다는 것을 의미합니다.

```EditorConfig
# Top-most EditorConfig file
root = true

# Tab indentation
[*.cs]
indent_style = tab
```

이제 **Tab** 키를 누르면 공백 대신 탭 문자가 추가됩니다.

![Tab 키가 탭 문자 추가](../ide/media/vside_editorconfig_tab.png)

## <a name="troubleshooting-editorconfig-settings"></a>EditorConfig 설정 문제 해결

프로젝트 위에 또는 그 이상에 있는 디렉터리 구조의 어디엔가 EditorConfig 파일이 있다면 Visual Studio는 해당 파일의 편집기 설정을 사용자의 편집기에 적용합니다. 이 경우에는 상태 표시줄에서 다음 메시지가 보일 수 있습니다.

   **"이 파일 형식에 대한 사용자 기본 설정이 이 프로젝트의 코딩 규칙으로 재정의됩니다."**

즉, **도구** > **옵션** > **텍스트 편집기**의 편집기 설정(예: 들여쓰기 크기 및 스타일, 탭 크기 또는 코딩 규칙)이 디렉터리 구조에서 프로젝트 또는 위의 EditorConfig 파일에 지정되어 있는 경우 EditorConfig 파일의 규칙은 옵션의 설정을 재정의합니다. **도구** > **옵션** > **텍스트 편집기**에서 **프로젝트 코딩 규칙 따름** 옵션을 전환하여 이 동작을 제어할 수 있습니다. 옵션을 선택 취소하면 Visual Studio에 대한 EditorConfig 지원이 해제됩니다.

![도구 옵션 - 프로젝트 코딩 규칙 따름](media/coding_conventions_option.png)

명령 프롬프트를 열고 사용자의 프로젝트가 포함된 디스크의 루트에서 다음 명령을 실행하여 부모 디렉터리에서 .editorconfig 파일을 찾을 수 있습니다.

```Shell
dir .editorconfig /s
```

리포지토리의 루트 또는 프로젝트가 상주하는 디렉터리의 .editorconfig 파일에서 ```root=true``` 속성을 설정하여 EditorConfig 규칙의 범위를 제어할 수 있습니다. Visual Studio는 열린 파일의 디렉터리와 모든 부모 디렉터리에서 .editorconfig라는 파일을 찾습니다. 루트 파일 경로에 도달하거나 ```root=true```인 .editorconfig 파일이 발견되면 검색이 종료됩니다.

## <a name="see-also"></a>참고 항목

[.NET 코드 스타일 규칙](../ide/editorconfig-code-style-settings-reference.md)  
[.NET 명명 규칙](../ide/editorconfig-naming-conventions.md)  
[언어 서비스를 위한 EditorConfig 지원](../extensibility/supporting-editorconfig.md)  
[EditorConfig.org](http://editorconfig.org/)  
[편집기에서 코드 작성](writing-code-in-the-code-and-text-editor.md)