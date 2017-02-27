---
title: "ProjectSubType 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#ProjectSubType"
helpviewer_keywords: 
  - "<ProjectSubType> 요소[Visual Studio 템플릿]"
  - "ProjectSubType 요소[Visual Studio 템플릿]"
ms.assetid: f6895cd4-3e95-4f0e-aa9e-8c7750f46ed4
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# ProjectSubType 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

템플릿을 `ProjectType` 요소에 지정된 값의 하위 범주로 분류합니다.  
  
## 구문  
  
```  
<ProjectSubType> SubType </ProjectSubType>  
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
  
 이 값은 템플릿의 하위 범주를 지정합니다.  
  
## 설명  
 `ProjectSubType`은 `TemplateData`의 선택적 자식 요소입니다.  
  
 `ProjectSubType` 요소는 [ProjectType](../extensibility/projecttype-element-visual-studio-templates.md) 요소에 대한 하위 범주를 제공합니다.  이 값은 다음을 포함할 수 있습니다.  
  
-   `SmartDevice-NETCFv1`: 템플릿이 [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] 버전 1.0을 대상으로 하도록 지정합니다.  
  
-   `SmartDevice-NETCFv2`: 템플릿이 [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] 버전 2.0을 대상으로 하도록 지정합니다.  
  
 템플릿에 있는 `ProjectType` 요소의 값이 `Web`인 경우 `ProjectSubType` 요소는 템플릿의 프로그래밍 언어를 지정합니다.  이 요소는 다음 값을 가질 수 있습니다.  
  
-   `CSharp`: 템플릿이 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 웹 프로젝트나 항목을 만들도록 지정합니다.  
  
-   `VisualBasic`: 템플릿이 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 웹 프로젝트나 항목을 만들도록 지정합니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] 버전 2.0을 대상으로 하는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 장치 응용 프로그램의 프로젝트 템플릿에 대한 메타데이터를 보여줍니다.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic device template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <ProjectSubType>SmartDevice-NETCFv2</ProjectSubType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
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
 [ProjectType 요소\(Visual Studio 템플릿\)](../extensibility/projecttype-element-visual-studio-templates.md)