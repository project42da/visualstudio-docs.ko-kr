---
title: "ProjectType 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#ProjectType"
helpviewer_keywords: 
  - "ProjectType 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: ccf9d83f-c7f3-49c7-a31f-e1f22bec004c
caps.latest.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 19
---
# ProjectType 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**새 프로젝트** 또는 **새 항목 추가** 대화 상자의 지정된 그룹에 나타나도록 프로젝트 템플릿을 분류합니다.  
  
> [!WARNING]
>  2012 Visual Studio를 시작 하는 c \+ \+ 프로젝트 템플릿은 사용할 수 있습니다.  Visual Studio 2010과 이전 버전의 c \+ \+는 지원 되지 않습니다.  
  
## 구문  
  
```  
<ProjectType> CSharp/VisualBasic/VC/Web </ProjectType>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|템플릿을 분류하고 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에 템플릿을 표시하는 방법을 정의합니다.|  
  
## 텍스트 값  
 텍스트 값이 필요합니다.  
  
 이 값은 템플릿이 만들 프로젝트의 형식을 지정하며 다음 값 중 하나를 포함해야 합니다.  
  
-   `CSharp`: 템플릿이 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 프로젝트나 항목을 만들도록 지정합니다.  
  
-   `VisualBasic`: 템플릿이 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 프로젝트나 항목을 만들도록 지정합니다.  
  
-   `Web`: 템플릿이 웹 프로젝트나 항목을 만들도록 지정합니다.  `ProjectType` 요소에 이 값이 포함되어 있으면 프로젝트나 항목의 언어는 [ProjectSubType 요소\(Visual Studio 템플릿\)](../extensibility/projectsubtype-element-visual-studio-templates.md)에서 정의됩니다.  
  
## 설명  
 `ProjectType`은 `TemplateData`의 필수 자식 요소입니다.  
  
 `ProjectType` 요소의 값은 **새 프로젝트** 또는 **새 항목 추가**에서 템플릿의 위치를 지정합니다.  예를 들어, `ProjectType` 값이 `CSharp`인 템플릿은 **새 프로젝트** 대화 상자의 **Visual C\#** 노드에 나타납니다.  
  
 템플릿 하위 형식은 [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) 요소를 사용하여 지정될 수 있습니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 응용 프로그램의 프로젝트 템플릿에 대한 메타데이터를 보여 줍니다.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyStarterKit.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [ProjectSubType 요소\(Visual Studio 템플릿\)](../extensibility/projectsubtype-element-visual-studio-templates.md)