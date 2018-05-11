---
title: Visual Studio에서 템플릿 구성
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- project templates [Visual Studio], locations
- item templates [Visual Studio], locations
- template locations [Visual Studio]
- Visual Studio templates, organizing
- templates [Visual Studio], organizing
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 65d4940e7a7969fe28fe115ec7ef42cfdc645c9a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-locate-and-organize-project-and-item-templates"></a>방법: 프로젝트 템플릿과 항목 템플릿 찾기 및 구성

Visual Studio에서 인식할 수 있는 위치에 템플릿 파일이 있어야 **새 프로젝트** 및 **새 항목 추가** 대화 상자에 템플릿이 나타납니다. 사용자 템플릿 위치에서 사용자 지정 하위 범주를 만들 수 있으며 범주는 **새 프로젝트** 및 **새 항목 추가** 대화 상자에 표시됩니다.

## <a name="locate-templates"></a>템플릿 찾기

설치된 템플릿과 사용자 템플릿은 서로 다른 두 위치에 저장됩니다.

### <a name="user-templates"></a>사용자 템플릿

사용자 템플릿 디렉터리에 *.vstemplate* 파일을 포함하는 압축된(*.zip*) 파일을 추가하는 경우 템플릿이 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에 표시됩니다. 기본적으로 사용자 템플릿은 다음 위치에 있습니다.

- *%USERPROFILE%\Documents\Visual Studio \<버전\>\Templates\ProjectTemplates*

- *%USERPROFILE%\Documents\Visual Studio \<버전\>\Templates\ItemTemplates*

예를 들어 다음 디렉터리에는 C#용 사용자 프로젝트 템플릿이 포함되어 있습니다.

- *C:\Users\UserName\Documents\Visual Studio 2017\Templates\ProjectTemplates\Visual C#*

> [!TIP]
> **도구** > **옵션** > **프로젝트 및 솔루션** > **위치**에서 사용자 템플릿의 위치를 설정할 수 있습니다.

### <a name="installed-templates"></a>설치된 템플릿

기본적으로 Visual Studio와 함께 설치되는 템플릿은 다음 위치에 있습니다.

- *\\<VisualStudioInstallationDirectory\>\Common7\IDE\ItemTemplates\\<Programming Language\>\\<Locale ID>*

- *\\<VisualStudioInstallationDirectory\>\Common7\IDE\ProjectTemplates\\<Programming Language\>\\<Locale ID>*

예를 들어 다음 디렉터리에는 영어용 Visual Basic 프로젝트 템플릿(LCID 1033)이 포함되어 있습니다.

- *C:\\<VisualStudioInstallationDirectory\>\Common7\IDE\ItemTemplates\VisualBasic\1033*

## <a name="organize-templates"></a>템플릿 구성

**새 프로젝트** 및 **새 항목 추가** 대화 상자의 범주는 설치된 템플릿과 사용자 템플릿 위치에 있는 디렉터리 구조를 반영합니다. 사용자 템플릿 디렉터리에 새 폴더를 추가하여 사용자 템플릿을 독자적인 범주로 구성할 수 있습니다. **새 프로젝트** 및 **새 항목 추가** 대화 상자는 사용자 템플릿 범주에 수행된 모든 변경 내용을 보여줍니다.

> [!NOTE]
> 프로그래밍 언어 수준에서 새 범주를 만들 수 없습니다. 새 범주는 각 언어 내에서만 만들어질 수 있습니다.

### <a name="to-create-new-user-project-template-categories"></a>사용자 프로젝트 템플릿 범주를 새로 만들려면

1. 사용자 프로젝트 템플릿 디렉터리의 프로그래밍 언어 폴더에 폴더를 만듭니다. 예를 들어 C# 프로젝트 템플릿에 대해 **HelloWorld** 범주를 만들려면 다음 디렉터리를 만듭니다.

    - *\%USERPROFILE%\Documents\Visual Studio \<버전\>\Templates\ProjectTemplates\Visual C#\HelloWorld*

1. 이 범주의 모든 템플릿을 새 폴더에 넣습니다.

1. **파일** 메뉴에서 **새로 만들기** > **프로젝트**를 차례로 선택합니다.

   **HelloWorld** 범주가 **새 프로젝트** 대화 상자의 **설치됨** > **Visual C#** 아래에 나타납니다.

### <a name="to-create-new-user-item-template-categories"></a>사용자 항목 템플릿 범주를 새로 만들려면

1. 사용자 항목 템플릿 디렉터리의 프로그래밍 언어 폴더에 폴더를 만듭니다. 예를 들어 C# 항목 템플릿에 대해 **HelloWorld** 범주를 만들려면 다음 디렉터리를 만듭니다.

    - *\%USERPROFILE%\Documents\Visual Studio \<버전\>\Templates\ItemTemplates\Visual C#\HelloWorld*

1. 이 범주의 모든 템플릿을 새 폴더에 넣습니다.

1. 프로젝트를 만들거나 기존 프로젝트를 엽니다. 그런 다음 **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.

   **HelloWorld** 범주가 **새 항목 추가** 대화 상자의 **설치됨** > **Visual C# 항목** 아래에 나타납니다.

### <a name="display-templates-in-parent-categories"></a>템플릿을 부모 범주에 표시

*.vstemplate* 파일에서 `NumberOfParentCategoriesToRollUp` 요소를 사용하여 하위 범주의 템플릿이 부모 범주에 표시되도록 할 수 있습니다. 이 단계는 프로젝트 템플릿과 항목 템플릿에 대해 동일합니다.

#### <a name="to-display-templates-in-parent-categories"></a>템플릿을 부모 범주에 표시하려면

1. 템플릿을 포함하는 *.zip* 파일을 찾습니다.

1. *.zip* 파일의 압축을 풉니다.

1. Visual Studio에서 *.vstemplate* 파일을 엽니다.

1. `TemplateData` 요소에서 `NumberOfParentCategoriesToRollUp` 요소를 추가합니다. 예를 들어 다음 코드에서는 템플릿이 부모 범주에 표시되고 더 높은 범주에는 표시되지 않도록 합니다.

    ```xml
    <TemplateData>
        ...
        <NumberOfParentCategoriesToRollUp>
            1
        </NumberOfParentCategoriesToRollUp>
        ...
    </TemplateData>
    ```

1. *.vstemplate* 파일을 저장한 다음, 닫습니다.

1. 템플릿에 있는 파일을 선택하고 마우스 오른쪽 단추를 클릭한 다음 **보내기** > **압축(ZIP) 폴더**를 선택합니다.

   파일이 *.zip* 파일로 압축됩니다.

1. 추출된 템플릿 파일과 이전 템플릿 *.zip* 파일을 삭제합니다.

1. 새 *.zip* 파일을 삭제된 *.zip* 파일이 있던 디렉터리에 넣습니다.

## <a name="see-also"></a>참고 항목

- [템플릿 사용자 지정](../ide/customizing-project-and-item-templates.md)
- [Visual Studio 템플릿 스키마 참조(확장성)](../extensibility/visual-studio-template-schema-reference.md)
- [NumberOfParentCategoriesToRollUp(Visual Studio 템플릿)](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)
- [방법: 프로젝트 템플릿 만들기](../ide/how-to-create-project-templates.md)
- [방법: 항목 템플릿 만들기](../ide/how-to-create-item-templates.md)