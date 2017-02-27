---
title: "LocationField 요소(Visual Studio 프로젝트 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#LocationField"
helpviewer_keywords: 
  - "LocationField 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: 6aaaa155-6ce0-4f7f-aa50-8d63d7a7c992
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# LocationField 요소(Visual Studio 프로젝트 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정 여부는 **위치** 텍스트 상자에 **새 프로젝트** 대화 상자가 활성화, 비활성화 또는 프로젝트 템플릿에 대 한 숨겨진 합니다.  
  
 \<VSTemplate\>  
 \<TemplateData\>  
 \<LocationField\>  
  
## 구문  
  
```  
<LocationField> Enabled/Disabled/Hidden </LocationField>  
```  
  
## 특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿을 분류 하 고 표시 하는 방법을 정의 **새 프로젝트**합니다.|  
  
## 텍스트 값  
 텍스트 값은 필수입니다.  
  
 유효한 텍스트 값은 같습니다.  
  
-   `Enabled`, 를 지정 하는 **위치** 의 상자는 **새 프로젝트** 대화 상자가 활성화 됩니다.  
  
-   `Disabled`, 를 지정 하는 **위치** 상자는 **새 프로젝트** 대화 상자가 비활성화 됩니다.  
  
-   `Hidden`, 를 지정 하는 **위치** 의 상자는 **새 프로젝트** 대화 상자가 숨겨집니다.  
  
## 설명  
 기본값은 `Enabled`입니다.  
  
 **위치** 텍스트 상자에 **새 프로젝트** 대화 상자를 사용 하면 사용자가 새 프로젝트가 저장 되는 기본 디렉터리를 변경할 수 있습니다.  
  
 에 지정 된 값은 `Location` 요소 기본 프로젝트 시스템에서 지 원하는 경우에 대화 상자에서 적용 됩니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 템플릿의 메타데이터를 보여 줍니다.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <LocationField>Disabled</LocationField>  
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