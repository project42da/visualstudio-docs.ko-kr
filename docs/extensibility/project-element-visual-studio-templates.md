---
title: "Project 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#Project"
helpviewer_keywords: 
  - "<Project> 요소[Visual Studio 템플릿]"
  - "Project 요소[Visual Studio 템플릿]"
ms.assetid: 1da15ea6-26e2-462b-a03e-584ef4996579
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# Project 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로젝트에 추가할 파일 또는 디렉터리를 지정합니다.  
  
## 구문  
  
```  
<Project  
    File="MyProject.proj"  
    TargetFileName="MyTargetProject.proj"  
    ReplaceParameters="true/false">  
    IgnoreProjectParameter="$myCustomParameter$"  
        ...  
</Project>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`File`|필수 특성입니다.<br /><br /> 템플릿 .zip 파일에 있는 프로젝트 파일의 이름을 지정합니다.|  
|`ReplaceParameters`|선택적 특성입니다.<br /><br /> 프로젝트가 템플릿에서 만들어지는 경우 프로젝트 파일에 대체해야 할 매개 변수 값이 있는지 여부를 지정하는 부울 값입니다.  기본값은 `false`으로,|  
|`TargetFileName`|선택적 특성입니다.<br /><br /> 프로젝트가 템플릿에서 만들어지는 경우 프로젝트 파일의 이름을 지정합니다.|  
|`IgnoreProjectParameter`|선택적 특성입니다.<br /><br /> 현재 솔루션에 프로젝트를 추가할지 여부를 지정 합니다.  하는 경우 사용자 지정 매개 변수 값 "*myCustomParameter*$" 존재 매개 변수에 교체 파일에는 프로젝트 생성 되었지만 현재 열려 있는 솔루션의 일부로 추가 되지.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[폴더](../extensibility/folder-element-visual-studio-project-templates.md)|선택적 요소입니다.<br /><br /> 프로젝트에 추가할 폴더를 지정합니다.|  
|[ProjectItem](../extensibility/projectitem-element-visual-studio-project-templates.md)|선택적 요소입니다.<br /><br /> 프로젝트에 추가할 파일을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|필수적 요소입니다.|  
  
## 설명  
 `Project`은 `TemplateContent`의 선택적 자식 요소입니다.  
  
 `Project` 요소는 프로젝트를 지정하는 데 사용되므로 프로젝트 템플릿에서만 유효합니다.  
  
 `Project` 요소에는 [Folder](../extensibility/folder-element-visual-studio-project-templates.md) 자식 요소 또는 [ProjectItem](../extensibility/projectitem-element-visual-studio-project-templates.md) 자식 요소가 있을 수 있으나 `Folder`와 `ProjectItem` 자식 요소가 모두 함께 있을 수 없습니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 **새 프로젝트** 대화 상자에서 사용자가 입력한 이름에 기반하여 프로젝트 파일 이름을 자동으로 바꿉니다.  템플릿을 사용하여 만든 프로젝트 파일에 대체 파일을 이름을 제공하려는 경우 `TargetFileName` 특성을 사용합니다.  
  
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
 [ProjectItem 요소\(Visual Studio 프로젝트 템플릿\)](../extensibility/projectitem-element-visual-studio-project-templates.md)   
 [Folder 요소\(Visual Studio 프로젝트 템플릿\)](../extensibility/folder-element-visual-studio-project-templates.md)