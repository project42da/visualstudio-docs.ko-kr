---
title: "Folder 요소(Visual Studio 프로젝트 템플릿) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/developer/vstemplate/2005#Folder"
helpviewer_keywords: 
  - "Folder 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: 558e3d41-0db5-4c44-82bb-6bb87892b093
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# Folder 요소(Visual Studio 프로젝트 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로젝트에 추가할 폴더를 지정합니다.  
  
## 구문  
  
```  
<Folder Name="Project Folder">  
    <Folder> ... </Folder>  
    <ProjectItem> ... </ProjectItem>  
</Folder>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`Name`|필수 특성입니다.<br /><br /> 프로젝트 폴더의 이름입니다.|  
|`TargetFolderName`|선택적 특성입니다.<br /><br /> 템플릿에서 프로젝트를 만드는 경우 폴더에 제공할 이름을 지정합니다.  이 특성은 매개 변수 대체를 사용하여 폴더 이름을 만들거나 .zip 파일에 직접 사용할 수 없는 국가별 문자열을 사용하여 폴더 이름을 지정하는 경우 유용합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|`Folder`|프로젝트에 추가할 폴더를 지정합니다.  `Folder` 요소는 자식 `Folder` 요소를 포함할 수 있습니다.|  
|[ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md)|프로젝트에 추가할 파일을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[프로젝트](../extensibility/project-element-visual-studio-templates.md)|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)의 선택적 자식 요소입니다.|  
  
## 설명  
 `Folder`는 `Project`의 선택적 자식입니다.  
  
 다음 방법 중 하나를 사용하여 프로젝트 항목을 템플릿에 있는 폴더로 구성할 수 있습니다.  
  
-   템플릿 .zip 파일에 폴더를 포함하고, `Folder` 요소를 사용하지 않고 `ProjectItem` 요소에 파일에 대한 경로를 지정하여 해당 폴더를 .vstemplate 파일의 프로젝트에 추가합니다.  이것이 권장되는 방법입니다.  예를 들면 다음과 같습니다.  
  
     `...`  
  
     `<ProjectItem>\Folder\item.cs</ProjectItem>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
-   템플릿 .zip 파일에 폴더를 포함하고, `Folder` 요소를 사용하여 해당 폴더를 .vstemplate 파일의 프로젝트에 추가합니다.  예를 들면 다음과 같습니다.  
  
     `...`  
  
     `<Folder name="Folder">`  
  
     `<ProjectItem>item.cs</ProjectItem>`  
  
     `</Folder>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
-   템플릿 .zip 파일에 폴더를 포함하지 않지만 `ProjectItem` 요소의 `TargetFileName` 특성을 사용하여 폴더를 추가합니다.  예를 들면 다음과 같습니다.  
  
     `...`  
  
     `<ProjectItem TargetFileName="\Folder\item.cs">item.cs</ProjectItem>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
## 예제  
 다음 예제에서는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Windows 응용 프로그램의 프로젝트 템플릿에 대한 메타데이터를 보여 줍니다.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <Folder Name="Properties">  
                <ProjectItem>AssemblyInfo.cs</ProjectItem>  
                <ProjectItem>Resources.resx</ProjectItem>  
                <ProjectItem>Resources.Designer.cs</ProjectItem>  
                <ProjectItem>Settings.settings</ProjectItem>  
                <ProjectItem>Settings.Designer.cs</ProjectItem>  
            </Folder>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [ProjectItem 요소\(Visual Studio 항목 템플릿\)](../extensibility/projectitem-element-visual-studio-item-templates.md)