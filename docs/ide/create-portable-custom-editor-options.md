---
title: "휴대용, 사용자 지정 편집기 설정 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 12/14/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- editor
ms.assetid: 
caps.latest.revision: 29
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 31f433b28b67dc6f3179be87cb5894b5b3f0aa4f
ms.openlocfilehash: 8c986958f141d3efc2ffe29b4176b43e9960e0e1

---
# <a name="create-portable-custom-editor-settings"></a>휴대용, 사용자 지정 편집기 설정 만들기
Visual Studio의 텍스트 편집기 설정은 지정된 형식의 모든 프로젝트에 적용됩니다. 따라서 예를 들어 C# 텍스트 편집기 설정을 변경하는 경우 해당 설정이 Visual Studio의 *모든* C# 프로젝트에 적용됩니다. 그러나 고유한 개인 편집기 기본 설정과 다른 규칙을 사용해야 하는 경우도 있습니다. 이 경우 [EditorConfig](http://editorconfig.org/) 파일을 사용하여 프로젝트 단위로 공통 텍스트 편집기 옵션을 제공하면 됩니다. 코드베이스에 추가되는 .editorconfig 파일에 포함된 EditorConfig 설정이 전역 Visual Studio 텍스트 편집기 설정보다 우선합니다. 따라서 원하는 텍스트 편집기 설정을 사용하도록 각 코드베이스를 조정할 수 있습니다. Visual Studio에서 이 기능을 사용하기 위해 플러그 인이 필요하지는 않습니다.

## <a name="coding-consistency"></a>코딩 일관성
EditorConfig 파일의 설정을 사용하면 사용 중인 IDE 편집기에 관계없이 코드베이스에서 들여쓰기 스타일, 탭 너비, 줄의 끝 문자, 인코딩 등 언어의 코딩 스타일 및 설정을 일관성 있게 유지할 수 있습니다. 예를 들어 C#으로 코딩하는 경우 코드베이스에 들여쓰기가 항상 공백 문자&5;개로 구성되고, 문서에서 UTF-8 인코딩을 사용하고, 각 줄이 항상 CR/LF로 끝나도록 하는 규칙이 있다면 .editorconfig 파일을 해당 규칙에 따라 구성할 수 있습니다.

개인 프로젝트에서 사용하는 코딩 규칙과 팀 프로젝트에서 사용되는 규칙이 서로 다를 수 있습니다. 예를 들어 사용자는 코딩 시 Tab 키를 누를 때 탭 문자가 추가되는 것을 선호합니다. 그러나 팀은 들여쓰기 시 탭 문자 대신 공백 문자&4;개가 추가되는 것을 선호할 수 있습니다. EditorConfig 파일을 통해 각 시나리오에 맞게 구성하면 이 문제를 해결할 수 있습니다.

설정은 코드베이스의 파일에 포함되므로 해당 코드베이스와 함께 전송됩니다. EditorConfig 규격 편집기에서 코드 파일을 열기만 하면 텍스트 편집기 설정이 구현됩니다. EditorConfig 파일에 대한 자세한 내용은 [EditorConfig.org](http://editorconfig.org/) 웹 사이트를 참조하세요. 많은 .editorconfig 파일을 편집하는 경우 [EditorConfig Language Service](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) 확장이 유용할 수 있습니다.

## <a name="override-editorconfig-settings"></a>EditorConfig 설정 재정의
파일 계층 구조의 폴더에 .editorconfig 파일을 추가하는 경우 해당 설정이 이 수준과 그 아래에 있는 모든 파일에 적용됩니다. 특정 프로젝트 또는 코드베이스에 대해 EditorConfig 설정을 재정의하고 최상위 .editorconfig 파일과 다른 값이나 재정의 값을 사용하려는 경우 변경할 수준에 .editorconfig 파일을 추가하면 됩니다.

![EditorConfig 계층 구조](../ide/media/vside_editorconfig_hierarchy.png)

새 .editorconfig 파일 설정은 해당 수준과 모든 하위 파일에 적용됩니다.

## <a name="supported-settings"></a>지원되는 설정
Visual Studio의 편집기는 EditorConfig의 핵심 옵션 집합에 대해 다음 값을 지원합니다.
- indent_style
- indent_size
- tab_width
- end_of_line
- 문자 집합
- 루트
- [코드 스타일 규칙](../ide/editorconfig-code-style-settings-reference.md)

EditorConfig 설정은 XML을 제외하고 Visual Studio가 지원하는 모든 언어에서 지원됩니다.

## <a name="example"></a>예제
다음은 .editorconfig 파일을 프로젝트에 추가하기 전과 이후 C# 코드 조각의 들여쓰기 상태를 보여 주는 예제입니다. Visual Studio 텍스트 편집기에 대한 **옵션** 대화 상자의 **탭** 설정은 코드에서 Tab 키를 누를 때 공백 문자를 생성하도록 설정되었습니다.

![텍스트 편집기 탭 설정](../ide/media/vside_editorconfig_tabsetting.png)

예상대로 다음 줄에서 Tab 키를 누르면 공백 문자&4;개가 추가되어 줄이 들여쓰기됩니다.

![EditorConfig를 사용하기 전의 코드](../ide/media/vside_editorconfig_before.png)

.editorconfig라는 새 파일에 다음 코드를 추가한 후 프로젝트에 추가합니다. `[*.cs]` 설정은 이 변경 내용이 이 프로젝트의 .cs 파일에만 적용됨을 의미합니다.

![.editorconfig 파일이 프로젝트에 추가됨](../ide/media/vside_editorconfig_addconfig.png)

이제 Tab 키를 누르면 공백 대신 탭 문자가 추가됩니다.

![Tab 키를 누르면 탭 문자가 추가됨](../ide/media/vside_editorconfig_tab.png)

> [!NOTE]
>  프로젝트 또는 코드베이스에 .editorconfig 파일을 추가해도 기존 스타일이 새 스타일로 변환되지는 않습니다. 새로 추가한 줄에만 적용됩니다. 프로젝트 또는 코드베이스에서 .editorconfig 파일을 제거하는 경우 편집기 설정에 대한 코드 파일을 다시 로드하여 전역 설정으로 되돌려야 합니다. .editorconfig 파일에 오류가 있으면 Visual studio의 오류 창에 모두 보고됩니다.



<!--HONumber=Feb17_HO4-->


