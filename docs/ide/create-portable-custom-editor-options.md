---
title: "EditorConfig를 사용하여 휴대용, 사용자 지정 편집기 설정 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 10/27/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editor
ms.assetid: 
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: 2c1df6f8e34d2b8e72486dd804ba57f0dcf2406b
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>EditorConfig를 사용하여 휴대용, 사용자 지정 편집기 설정 만들기
Visual Studio의 텍스트 편집기 설정은 지정된 형식의 모든 프로젝트에 적용됩니다. 따라서 예를 들어 C# 텍스트 편집기 설정을 변경하는 경우 해당 설정이 Visual Studio의 *모든* C# 프로젝트에 적용됩니다. 그러나 고유한 개인 편집기 기본 설정과 다른 규칙을 사용해야 하는 경우도 있습니다. 이 경우 [EditorConfig](http://editorconfig.org/) 파일을 사용하여 프로젝트 단위로 공통 텍스트 편집기 옵션을 제공하면 됩니다. 코드베이스에 추가되는 .editorconfig 파일에 포함된 EditorConfig 설정이 전역 Visual Studio 텍스트 편집기 설정보다 우선합니다. 따라서 원하는 텍스트 편집기 설정을 사용하도록 각 코드베이스를 조정할 수 있습니다. Visual Studio에서 이 기능을 사용하기 위해 플러그 인이 필요하지는 않습니다.

## <a name="coding-consistency"></a>코딩 일관성
EditorConfig 파일의 설정을 사용하면 사용 중인 IDE 편집기에 관계없이 코드베이스에서 들여쓰기 스타일, 탭 너비, 줄의 끝 문자, 인코딩 등 언어의 코딩 스타일 및 설정을 일관성 있게 유지할 수 있습니다. 예를 들어 C#으로 코딩하는 경우 코드베이스에 들여쓰기가 항상 공백 문자 5개로 구성되고, 문서에서 UTF-8 인코딩을 사용하고, 각 줄이 항상 CR/LF로 끝나도록 하는 규칙이 있다면 .editorconfig 파일을 해당 규칙에 따라 구성할 수 있습니다.

개인 프로젝트에서 사용하는 코딩 규칙과 팀 프로젝트에서 사용되는 규칙이 서로 다를 수 있습니다. 예를 들어 사용자는 코딩 시 Tab 키를 누를 때 탭 문자가 추가되는 것을 선호합니다. 그러나 팀은 들여쓰기 시 탭 문자 대신 공백 문자 4개가 추가되는 것을 선호할 수 있습니다. EditorConfig 파일을 통해 각 시나리오에 맞게 구성하면 이 문제를 해결할 수 있습니다.

설정은 코드베이스의 파일에 포함되므로 해당 코드베이스와 함께 전송됩니다. EditorConfig 규격 편집기에서 코드 파일을 열기만 하면 텍스트 편집기 설정이 구현됩니다. EditorConfig 파일에 대한 자세한 내용은 [EditorConfig.org](http://editorconfig.org/) 웹 사이트를 참조하세요.

## <a name="override-editorconfig-settings"></a>EditorConfig 설정 재정의
파일 계층 구조의 폴더에 .editorconfig 파일을 추가하는 경우 해당 설정이 이 수준과 그 아래에 있는 모든 파일에 적용됩니다. 최상위 .editorconfig 파일과 다른 교칙을 사용하는 특정 프로젝트 또는 코드베이스에 대해 EditorConfig 설정을 재정의하려면 .editorconfig 파일을 코드베이스의 리포지토리 또는 프로젝트 디렉터리의 루트에 추가하면 됩니다. Visual Studio가 디렉터리 구조에서 .editorconfig 파일을 더 찾지 않도록 파일에 ```root=true``` 속성을 넣으세요. 새 .editorconfig 파일 설정은 모든 하위 디렉터리에 파일이 있는 수준에 적용됩니다.

```
# top-most EditorConfig file
root = true
```

![EditorConfig 계층 구조](../ide/media/vside_editorconfig_hierarchy.png)

EditorConfig 파일은 위쪽에서 아래쪽으로 읽으며 가장 가까운 EditorConfig 파일을 마지막으로 읽습니다. 일치하는 EditorConfig 섹션의 규칙이 읽는 순서로 적용되므로, 가까운 파일의 규칙이 우선 적용됩니다.

## <a name="supported-settings"></a>지원되는 설정
Visual Studio의 편집기는 [EditorConfig properties](http://editorconfig.org/#supported-properties)의 핵심 집합에서 다음 값을 지원합니다.  

- indent_style
- indent_size
- tab_width
- end_of_line
- 문자 집합
- 루트

또한 [.NET 코드 스타일 규칙](../ide/editorconfig-code-style-settings-reference.md)을 지원합니다.  

EditorConfig 설정은 XML을 제외하고 Visual Studio가 지원하는 모든 언어에서 지원됩니다.

## <a name="intellisense"></a>IntelliSense
Visual Studio는 .editorconfig 파일을 편집할 수 있는 제한된 IntelliSense를 제공하빈다. 많은 .editorconfig 파일을 편집하는 경우 [EditorConfig Language Service](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) 확장이 유용할 수 있습니다.

## <a name="example"></a>예제
다음은 .editorconfig 파일을 프로젝트에 추가하기 전과 이후 C# 코드 조각의 들여쓰기 상태를 보여 주는 예제입니다. Visual Studio 텍스트 편집기에 대한 **옵션** 대화 상자의 **탭** 설정은 코드에서 **Tab** 키를 누를 때 공백 문자를 생성하도록 설정되었습니다.

![텍스트 편집기 탭 설정](../ide/media/vside_editorconfig_tabsetting.png)

예상대로 다음 줄에서 **Tab** 키를 누르면 공백 문자 4개가 추가되어 줄이 들여쓰기됩니다.

![EditorConfig를 사용하기 전의 코드](../ide/media/vside_editorconfig_before.png)

.editorconfig라는 새 파일을 다음 콘텐츠를 포함하여 프로젝트에 추가합니다. `[*.cs]` 설정은 이 변경 내용이 이 프로젝트의 .cs 파일에만 적용됨을 의미합니다.  

![.editorconfig 파일이 프로젝트에 추가됨](../ide/media/vside_editorconfig_addconfig.png)

이제 **Tab** 키를 누르면 공백 대신 탭 문자가 추가됩니다.

![Tab 키를 누르면 탭 문자가 추가됨](../ide/media/vside_editorconfig_tab.png)

> [!NOTE]
>  프로젝트 또는 코드베이스에 .editorconfig 파일을 추가해도 기존 스타일이 새 스타일로 변환되지는 않습니다. 새로 추가한 줄에만 적용됩니다. 프로젝트 또는 코드베이스에서 .editorconfig 파일을 제거하는 경우 편집기 설정에 대한 코드 파일을 다시 로드하여 전역 설정으로 되돌려야 합니다. .editorconfig 파일에 오류가 있으면 Visual studio의 오류 목록 창에 모두 보고됩니다.

## <a name="troubleshooting-editorconfig-settings"></a>EditorConfig 설정 문제 해결
프로젝트 위에 또는 그 이상에 있는 디렉터리 구조의 어디엔가 EditorConfig 파일이 있다면 Visual Studio는 해당 파일의 편집기 설정을 사용자의 편집기에 적용합니다. 이 경우에는 상태 표시줄에서 다음 메시지가 보일 수 있습니다.

**"이 파일 형식에 대한 사용자 기본 설정이 이 프로젝트의 코딩 규칙으로 재정의됩니다."**

즉, **도구**, **옵션**, **텍스트 편집기**의 편집기 설정(예: 들여쓰기 크기, 탭 크기, 들여쓰기 스타일 &mdash; 탭 또는 공백, 또는 `var` 사용 등의 코딩 규칙)이 디렉터리 구조에서 프로젝트 또는 위의 EditorConfig 파일에 지정되어 있는 경우 EditorConfig 파일의 규칙은 옵션의 설정을 재정의합니다. **도구**, **옵션**, **텍스트 편집기**에서 **프로젝트 코딩 규칙 따름** 옵션을 전환하여 이 동작을 제어할 수 있습니다. 옵션을 선택 취소하면 Visual Studio에 대한 EditorConfig 지원이 해제됩니다.

![도구 옵션 - 프로젝트 코딩 규칙 따름](media/coding_conventions_option.png)

명령 프롬프트를 열고 사용자의 프로젝트가 포함된 디스크의 루트에서 다음 명령을 실행하여 부모 디렉터리에서 .editorconfig 파일을 찾을 수 있습니다.

```
dir .editorconfig /s
```

리포지토리의 루트 또는 프로젝트가 상주하는 디렉터리의 .editorconfig 파일에서 ```root=true``` 속성을 설정하여 EditorConfig 규칙의 범위를 제어할 수 있습니다. Visual Studio는 열린 파일의 디렉터리와 모든 부모 디렉터리에서 .editorconfig라는 파일을 찾습니다. Visual Studio는 루트 파일 경로에 도달하거나 ```root=true``` 포함 .editorconfig 파일을 찾은 경우 검색을 중지합니다.

## <a name="support-editorconfig-for-your-language-service"></a>언어 서비스에 대한 EditorConfig 지원
대부분의 경우 Visual Studio 언어 서비스를 구현할 때 EditorConfig 유니버설 속성을 지원하기 위해 추가 작업이 필요하지 않습니다. 사용자가 파일을 열면 코어 편집기에서 .editorconfig 파일을 자동으로 검색하여 읽은 다음 적절한 텍스트 버퍼와 보기 옵션을 설정합니다. 하지만 일부 언어 서비스에서는 사용자가 텍스트를 편집하거나 서식을 지정할 때 항목에 대한 전역 설정(예: 탭, 공백) 대신 적절한 상황별 텍스트 보기 옵션을 사용하도록 선택합니다. 이러한 경우 EditorConfig 파일을 지원하도록 언어 서비스를 업데이트해야 합니다.

다음은 EditorConfig 파일을 지원하기 위해 전역 _language-specific_ 옵션을 _contextual_ 옵션으로 대체하여 언어 서비스를 지원하기 위해 필요한 변경 사항입니다.  

### <a name="indent-style"></a>들여쓰기 스타일
바꾸기:  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs  
_또는_  
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs  

바꿀 대상:  

!textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)  
_또는_  
!textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)  

### <a name="indent-size"></a>들여쓰기 크기
바꾸기:  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize  
_또는_  
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize  

바꿀 대상:  

textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)  
_또는_  
textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)  

### <a name="tab-size"></a>탭 크기
바꾸기:  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize  
_또는_  
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize  

바꿀 대상:  

textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)  
_또는_  
textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)  

## <a name="see-also"></a>참고 항목
[.NET 코드 스타일 규칙](../ide/editorconfig-code-style-settings-reference.md)  
[EditorConfig.org](http://editorconfig.org/)  
[편집기에서 코드 작성](writing-code-in-the-code-and-text-editor.md)