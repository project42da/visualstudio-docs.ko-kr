---
title: "EnableLocationBrowseButton 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#EnableLocationBrowseButton"
helpviewer_keywords: 
  - "EnableLocationBrowseButton[Visual Studio 프로젝트 템플릿]"
ms.assetid: a12d10d8-af49-482a-af77-e084fd07a47d
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# EnableLocationBrowseButton 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

새 프로젝트가 저장되는 기본 디렉터리를 사용자가 쉽게 수정할 수 있도록 **새 프로젝트** 대화 상자에서 **찾아보기** 단추를 사용할 수 있는지 여부를 지정합니다.  
  
## 구문  
  
```  
<EnableLocationBrowseButton> true/false </EnableLocationBrowseButton>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿을 분류하고 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에 템플릿을 표시하는 방법을 정의합니다.|  
  
## 텍스트 값  
 텍스트 값이 필요합니다.  
  
 텍스트는 **새 프로젝트** 대화 상자에 **찾아보기** 단추를 표시하는지 여부를 나타내는 `true` 또는 `false`입니다.  
  
## 설명  
 `EnableLocationBrowseButton`은 선택적 요소입니다.  기본값은 `true`이며, **새 프로젝트** 대화 상자에 **찾아보기** 단추를 표시합니다.  
  
 **새 프로젝트** 대화 상자의 **위치** 텍스트 상자는 새 프로젝트가 저장되는 디렉터리를 지정합니다.  **찾아보기** 단추는 **프로젝트 위치** 대화 상자를 표시하여 이 디렉터리를 수정할 수 있도록 합니다. 이 대화 상자에서 컴퓨터의 사용 가능한 다른 디렉터리로 쉽게 이동한 다음 그 디렉터리를 새 프로젝트가 저장되는 디렉터리로 선택할 수 있습니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Windows 응용 프로그램에 대한 메타데이터를 보여 줍니다.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <EnableLocationBrowseButton>false</EnableLocationBrowseButton>  
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