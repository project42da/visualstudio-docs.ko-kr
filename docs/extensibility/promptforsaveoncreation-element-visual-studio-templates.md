---
title: "PromptForSaveOnCreation 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#PromptForSaveOnCreation"
helpviewer_keywords: 
  - "PromptForSaveOnCreation 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: 75174674-0c3c-4b57-b2fd-6ea8e817b67d
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# PromptForSaveOnCreation 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로젝트를 만들 때 **새 프로젝트** 대화 상자를 통해 프로젝트 저장 위치를 지정하라는 메시지를 사용자에게 표시할지 여부를 지정합니다.  이 요소를 `true`로 설정하면 사용자 위치를 묻는 메시지가 사용자에게 표시되고, `false`로 설정하면 해당 메시지가 표시되지 않습니다. 즉, 프로젝트 저장 위치를 지정하지 않는 경우 임시 프로젝트가 만들어집니다.  
  
## 구문  
  
```  
<PromptForSaveOnCreation> true/false </PromptForSaveOnCreation>  
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
  
 텍스트는 `true` 또는 `false`여야 합니다. `true`는 새 프로젝트를 만들 때 저장 위치를 묻는 메시지를 사용자에게 표시함을 의미합니다.  
  
## 설명  
 `PromptForSaveOnCreation`은 선택적 요소입니다.  기본값은 `false`입니다.  
  
 임시 프로젝트는 프로젝트의 내용을 디스크에 저장하지 않고  만들고 수정할 수 있는 프로젝트입니다.  자세한 내용은 [임시 프로젝트](http://msdn.microsoft.com/ko-kr/9cf1944c-7045-44cc-8701-7b0eb4099f2b)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `PromptForSaveOnCreation` 값을 `false`로 설정하여 프로젝트가 임시 프로젝트로 생성될 수 있도록 허용합니다.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <PromptForSaveOnCreation>false</PromptForSaveOnCreation>  
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