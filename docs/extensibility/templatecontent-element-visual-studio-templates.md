---
title: "TemplateContent 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#TemplateContent"
helpviewer_keywords: 
  - "TemplateContent 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: 90ae401c-b294-49ac-98da-e0d274f5bebb
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# TemplateContent 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

템플릿 내용을 지정합니다.  
  
## 구문  
  
```  
<TemplateContent>  
    ...  
</TemplateContent>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|[BuildOnLoad](../extensibility/buildprojectonload-visual-studio-templates.md)|프로젝트가 템플릿에서 만들어지는 경우 솔루션을 빌드할지 여부를 지정합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[ProjectCollection](../extensibility/projectcollection-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 다중 프로젝트 템플릿의 구성과 내용을 지정합니다.|  
|[프로젝트](../extensibility/project-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 프로젝트에 추가할 파일 또는 디렉터리를 지정합니다.|  
|[참조](../extensibility/references-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 항목 템플릿에 필요한 어셈블리 참조를 지정합니다.|  
|[ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md)|선택적 요소입니다.<br /><br /> 템플릿에 포함된 파일을 지정합니다.|  
|[CustomParameters](../extensibility/customparameters-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 프로젝트나 항목이 템플릿에서 만들어지는 경우 사용 될 사용자 지정 매개 변수를 지정 합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 프로젝트 템플릿, 항목 템플릿 또는 시작 키트에 대한 모든 메타데이터가 들어 있습니다.|  
  
## 설명  
 `TemplateContent`는 필수 요소입니다.  
  
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