---
title: "방법: 다중 프로젝트 템플릿 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "다중 프로젝트 템플릿"
  - "프로젝트 템플릿, 다중 프로젝트 템플릿 만들기"
  - "Visual Studio 템플릿, 다중 프로젝트 템플릿 만들기"
ms.assetid: 8c7f7065-137e-40ad-868d-37e007270efd
caps.latest.revision: 16
caps.handback.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: 다중 프로젝트 템플릿 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다중 프로젝트 템플릿은 두 개 이상의 프로젝트에 대한 컨테이너로 사용됩니다.  다중 프로젝트 템플릿을 기반으로 하는 프로젝트가 **새 프로젝트** 대화 상자에서 만들어지는 경우 템플릿의 모든 프로젝트가 솔루션에 추가됩니다.  
  
 다중 프로젝트 템플릿은 다음 항목을 .zip 파일로 압축하여 포함해야 합니다.  
  
-   전체 다중 프로젝트 템플릿에 대한 루트 .vstemplate 파일.  이 루트 .vstemplate 파일은 **새 프로젝트** 대화 상자에 표시되는 메타데이터를 포함하며 이 템플릿의 프로젝트에 대한 .vstemplate 파일을 찾을 위치를 지정합니다.  이 파일은 .zip 파일의 루트에 있어야 합니다.  
  
-   완전한 프로젝트 템플릿에 필요한 파일이 들어 있는 하나 이상의 폴더입니다.  이러한 폴더에는 프로젝트에 대한 .vstemplate 파일과 프로젝트에 대한 모든 코드 파일이 들어 있습니다.  
  
 예를 들어, 프로젝트가 두 개 있는 다중 프로젝트 템플릿 .zip 파일에는 다음 파일과 디렉터리가 있을 수 있습니다.  
  
 MultiProjectTemplate.vstemplate  
  
 \\Project1\\Project1.vstemplate  
  
 \\Project1\\Project1.vbproj  
  
 \\Project1\\Class.vb  
  
 \\Project2\\Project2.vstemplate  
  
 \\Project2\\Project2.vbproj  
  
 \\Project2\\Class.vb  
  
 다중 프로젝트 템플릿에 대한 루트 .vstemplate 파일은 다음과 같은 점에서 단일 프로젝트 템플릿과 다릅니다.  
  
-   `VSTemplate` 요소의 `Type` 특성 값이 `ProjectGroup`입니다.  예를 들면 다음과 같습니다.  
  
    ```  
    <VSTemplate Version="2.0.0" Type="ProjectGroup"  
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    ```  
  
-   `TemplateContent` 요소에는 포함된 프로젝트의 .vstemplate 파일에 대한 경로를 정의하는 하나 이상의 `ProjectTemplateLink` 요소가 있는 `ProjectCollection` 요소가 포함되어 있습니다.  예를 들면 다음과 같습니다.  
  
    ```  
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
  
 다중 프로젝트 템플릿은 또한 일반 템플릿과 다르게 동작합니다.  다중 프로젝트 템플릿에는 다음과 같은 고유한 특성이 있습니다.  
  
-   다중 프로젝트 템플릿에 있는 개별 프로젝트에는 **새 프로젝트** 대화 상자에서 이름을 할당할 수 없습니다.  대신 `ProjectTemplateLink` 요소의 `ProjectName` 특성을 사용하여 각 프로젝트의 이름을 지정합니다.  자세한 내용은 다음 단원의 첫 번째 예제를 참조하십시오.  
  
-   다중 프로젝트 템플릿은 여러 언어로 작성된 프로젝트를 포함할 수 있으나 전체 템플릿 자체는 `ProjectType` 요소를 사용하여 하나의 범주에만 배치될 수 있습니다.  
  
### 다중 프로젝트 템플릿을 만들려면  
  
1.  다중 프로젝트 템플릿에 포함할 프로젝트를 만듭니다.  
  
2.  모든 프로젝트에 대해 .vstemplate 파일을 만듭니다.  자세한 내용은 [방법: 프로젝트 템플릿 만들기](../ide/how-to-create-project-templates.md)를 참조하십시오.  
  
3.  다중 프로젝트 템플릿에 대한 메타데이터를 포함하는 루트 .vstemplate 파일을 만듭니다.  자세한 내용은 다음 단원의 첫 번째 예제를 참조하십시오.  
  
4.  템플릿에 포함할 파일과 폴더를 선택하고 선택 영역을 마우스 오른쪽 단추로 클릭한 다음 **보내기**를 클릭하고 **압축\(ZIP\) 폴더**를 클릭합니다.  파일과 폴더가 .zip 파일로 압축됩니다.  
  
5.  .zip 템플릿 파일을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 템플릿 디렉터리에 넣습니다.  기본적으로이 디렉터리 \\My Documents\\Visual Studio입니다*버전*\\Templates\\ProjectTemplates\\.  
  
## 예제  
 이 예제에서는 기본 다중 프로젝트 루트 .vstemplate 파일을 보여 줍니다.  이 예제에서 템플릿에는 `My Windows Application` 프로젝트와 `My Class Library` 프로젝트가 들어 있습니다.  `ProjectTemplateLink` 요소의 `ProjectName` 특성은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]가 이 프로젝트에 할당할 이름을 설정합니다.  `ProjectName` 특성이 없으면 .vstemplate 파일의 이름이 프로젝트 이름으로 사용됩니다.  
  
```  
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
  
## 예제  
 이 예제에서는 `SolutionFolder` 요소를 사용하여 프로젝트를 `Math Classes` 그룹과 `Graphics Classes` 그룹으로 나눕니다.  이 템플릿에는 네 개의 프로젝트가 포함되어 있으며, 그 중 둘은 각각의 솔루션 폴더에 있습니다.  
  
```  
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
  
## 참고 항목  
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [방법: 프로젝트 템플릿 만들기](../ide/how-to-create-project-templates.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [SolutionFolder 요소\(Visual Studio 템플릿\)](../extensibility/solutionfolder-element-visual-studio-templates.md)   
 [ProjectTemplateLink 요소\(Visual Studio 템플릿\)](../extensibility/projecttemplatelink-element-visual-studio-templates.md)