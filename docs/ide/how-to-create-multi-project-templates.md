---
title: Visual Studio에 대한 다중 프로젝트 템플릿 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, creating multi-project
- project templates, multi-project
- multi-project templates
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: b3902dd2b6f4dfac72d61d2c4d81937dcbbfdd07
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-multi-project-templates"></a>방법: 다중 프로젝트 템플릿 만들기

다중 프로젝트 템플릿은 두 개 이상의 프로젝트에 대한 컨테이너로 사용됩니다. **새 프로젝트** 대화 상자에서 다중 프로젝트 템플릿에 기반하는 프로젝트를 만든 경우 템플릿의 모든 프로젝트를 솔루션에 추가합니다.

다중 프로젝트 템플릿은 `ProjectGroup` 형식의 루트 템플릿이 있는 2개 이상의 프로젝트 템플릿입니다.

또한 다중 프로젝트 템플릿은 단일 프로젝트 템플릿 다르게 작동합니다. 다음과 같은 고유한 특징이 있습니다.

- 다중 프로젝트 템플릿에 있는 개별 프로젝트는 **새 프로젝트** 대화 상자에서 이름을 할당할 수 없습니다. 대신 *.vstemplate* 파일에 있는 `ProjectTemplateLink` 요소의 `ProjectName` 특성을 사용하여 각 프로젝트의 이름을 지정합니다.

- 다중 프로젝트 템플릿에는 다른 언어로 작성된 프로젝트가 포함될 수 있지만 전체 템플릿 자체는 하나의 범주에만 배치될 수 있습니다. *.vstemplate* 파일에 있는 `ProjectType` 요소에서 템플릿 범주를 지정합니다.

다중 프로젝트 템플릿에는 *.zip* 파일로 압축된 다음, 항목이 포함되어야 합니다.

- 전체 다중 프로젝트 템플릿에 대한 루트 *.vstemplate* 파일입니다. 이 루트 *.vstemplate* 파일은 **새 프로젝트** 대화 상자에서 표시하는 메타데이터를 포함하고, 이 템플릿에서 프로젝트의 *.vstemplate* 파일을 찾을 위치를 지정합니다. 이 파일은 *.zip* 파일의 루트에 있어야 합니다.

- 전체 프로젝트 템플릿에 필요한 파일이 포함된 둘 이상의 폴더입니다. 폴더에는 프로젝트의 모든 코드 파일 및 프로젝트의 *.vstemplate* 파일이 포함됩니다.

예를 들어 두 개의 프로젝트가 포함된 다중 프로젝트 템플릿 *.zip* 파일에는 다음 파일 및 디렉터리가 있을 수 있습니다.

- *MultiProjectTemplate.vstemplate*
- *\Project1\Project1.vstemplate*
- *\Project1\Project1.vbproj*
- *\Project1\Class.vb*
- *\Project2\Project2.vstemplate*
- *\Project2\Project2.vbproj*
- *\Project2\Class.vb*

다중 프로젝트 템플릿의 루트 *.vstemplate* 파일은 다음과 같은 점에서 단일 프로젝트 템플릿과 다릅니다.

- `VSTemplate` 요소의 `Type` 특성에는 `Project` 대신 `ProjectGroup` 값이 포함됩니다. 예:

    ```xml
    <VSTemplate Version="2.0.0" Type="ProjectGroup"
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    ```

- `TemplateContent` 요소에는 포함된 프로젝트의 *.vstemplate* 파일에 대한 경로를 정의하는 하나 이상의 `ProjectTemplateLink` 요소를 가진 `ProjectCollection` 요소가 포함됩니다. 예:

    ```xml
    <TemplateContent>
        <ProjectCollection>
            <ProjectTemplateLink>
                Project1\Project1.vstemplate
            </ProjectTemplateLink>
            <ProjectTemplateLink>
                Project2\Project2.vstemplate
            </ProjectTemplateLink>
        </ProjectCollection>
    </TemplateContent>
    ```

## <a name="to-create-a-multi-project-template-from-an-existing-solution"></a>기존 솔루션에서 다중 프로젝트 템플릿을 만들려면 다음을 수행합니다.

1. 솔루션을 만들고 두 개 이상의 프로젝트를 추가합니다.

1. 서식 파일에 내보낼 준비가 될 때까지 프로젝트를 사용자 지정합니다.

1. **프로젝트** 메뉴에서 **템플릿 내보내기**를 선택합니다.

   **템플릿 내보내기 마법사**가 열립니다.

1. **템플릿 형식 선택** 페이지에서 **프로젝트 템플릿**을 선택합니다. 템플릿으로 내보낼 프로젝트를 선택한 후 **다음**을 선택합니다.

1. **템플릿 옵션 선택** 페이지에서 템플릿의 이름 및 설명(옵션), 아이콘 및 미리 보기 이미지를 입력합니다. **마침**을 선택합니다.

   프로젝트는 *.zip* 파일로 내보내지고 지정된 출력 위치에 배치됩니다.

   > [!NOTE]
   > 각 프로젝트는 템플릿에 개별적으로 내보내져야 하므로 솔루션의 각 프로젝트에 대해 위의 단계를 반복합니다.

1. 각 프로젝트에 대한 하위 디렉터리로 템플릿에 대한 디렉터리를 만듭니다.

1. 만든 해당 하위 디렉터리에 각 프로젝트의 *.zip* 파일 콘텐츠의 압축을 풉니다.

1. 기본 디렉터리에 파일 확장명이 *.vstemplate*인 XML 파일을 만듭니다. 이 파일은 다중 프로젝트 템플릿에 대한 메타데이터를 포함합니다. 파일의 구조를 따르는 예제를 참조하세요. 각 프로젝트의 *.vstemplate* 파일에 상대 경로를 지정해야 합니다.

1. 기본 디렉터리를 선택하고, 마우스 오른쪽 단추를 클릭하면 나타나는 메뉴, 즉 바로 가기 메뉴에서 **보내기** > **압축(ZIP) 폴더**를 선택합니다.

   파일 및 폴더가 *.zip* 파일로 압축됩니다.

1. 사용자 프로젝트 템플릿 디렉터리에 *.zip* 파일을 복사합니다. 기본적으로 이 디렉터리는 *%USERPROFILE%\Documents\Visual Studio \<버전\>\Templates\ProjectTemplates*입니다.

1. Visual Studio에서 **새 프로젝트** 대화 상자를 열고 템플릿에 나타나는지 확인합니다.

## <a name="two-project-example"></a>두 프로젝트 예제

이 예제에서는 기본 다중 프로젝트 루트 *.vstemplate* 파일을 보여줍니다. 이 예제에서 템플릿에는 `My Windows Application` 프로젝트와 `My Class Library` 프로젝트가 있습니다. `ProjectTemplateLink` 요소에서 `ProjectName` 특성은 프로젝트에 지정된 이름을 지정합니다.

> [!TIP]
> `ProjectName` 특성이 지정되지 않았으면 *.vstemplate* 파일의 이름이 프로젝트 이름으로 사용됩니다.

```xml
<VSTemplate Version="2.0.0" Type="ProjectGroup"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>Multi-Project Template Sample</Name>
        <Description>An example of a multi-project template</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>VisualBasic</ProjectType>
    </TemplateData>
    <TemplateContent>
        <ProjectCollection>
            <ProjectTemplateLink ProjectName="My Windows Application">
                WindowsApp\MyTemplate.vstemplate
            </ProjectTemplateLink>
            <ProjectTemplateLink ProjectName="My Class Library">
                ClassLib\MyTemplate.vstemplate
            </ProjectTemplateLink>
        </ProjectCollection>
    </TemplateContent>
</VSTemplate>
```

## <a name="example-with-solution-folders"></a>솔루션 폴더의 예

이 예제에서는 `SolutionFolder` 요소를 사용하여 프로젝트를 `Math Classes` 및 `Graphics Classes`의 두 그룹으로 나눕니다. 이 템플릿에는 각 솔루션 폴더에 2개가 포함되는 4개의 프로젝트가 있습니다.

```xml
<VSTemplate Version="2.0.0" Type="ProjectGroup"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>Multi-Project Template Sample</Name>
        <Description>An example of a multi-project template</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>VisualBasic</ProjectType>
    </TemplateData>
    <TemplateContent>
        <ProjectCollection>
            <SolutionFolder Name="Math Classes">
                <ProjectTemplateLink ProjectName="MathClassLib1">
                    MathClassLib1\MyTemplate.vstemplate
                </ProjectTemplateLink>
                <ProjectTemplateLink ProjectName="MathClassLib2">
                    MathClassLib2\MyTemplate.vstemplate
                </ProjectTemplateLink>
            </SolutionFolder>
            <SolutionFolder Name="Graphics Classes">
                <ProjectTemplateLink ProjectName="GraphicsClassLib1">
                    GraphicsClassLib1\MyTemplate.vstemplate
                </ProjectTemplateLink>
                <ProjectTemplateLink ProjectName="GraphicsClassLib2">
                    GraphicsClassLib2\MyTemplate.vstemplate
                </ProjectTemplateLink>
            </SolutionFolder>
        </ProjectCollection>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>참고 항목

[프로젝트 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)  
[방법: 프로젝트 템플릿 만들기](../ide/how-to-create-project-templates.md)  
[Visual Studio 템플릿 스키마 참조(확장성)](../extensibility/visual-studio-template-schema-reference.md)  
[SolutionFolder 요소(Visual Studio 템플릿)](../extensibility/solutionfolder-element-visual-studio-templates.md)  
[ProjectTemplateLink 요소(Visual Studio 템플릿)](../extensibility/projecttemplatelink-element-visual-studio-templates.md)
