---
title: "SupportsLanguageDropDown 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#SupportsLanguageDropDown"
helpviewer_keywords: 
  - "<SupportsLanguageDropDown> 요소[Visual Studio 템플릿]"
  - "SupportsLanguageDropDown 요소[Visual Studio 템플릿]"
ms.assetid: 641197d5-f724-4c06-bc47-2e22dad3fbfb
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# SupportsLanguageDropDown 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

웹 항목 템플릿이 여러 언어에 대해 동일한지 여부와 **새 항목 추가** 대화 상자에서 **언어** 옵션이 활성화되었는지 여부를 지정합니다.  
  
## 구문  
  
```  
<SupportsLanguageDropDown> true/false </SupportsLanguageDropDown>  
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
  
 텍스트는 **새 항목 추가** 대화 상자에서 **언어** 옵션을 사용할 수 있는지 여부를 나타내는 `true` 또는 `false`여야 합니다.  
  
## 설명  
 `SupportsLanguageDropDown`은 선택적 요소입니다.  기본값은 `false`입니다.  
  
 `SupportsLanguageDropDown` 요소는 웹 항목 템플릿에서만 사용할 수 있습니다.  
  
 이 요소의 값이 `true`로 설정되면 항목 템플릿은 모든 프로그래밍 언어에 대해 동일하며 **새 항목 추가** 대화 상자에서 **언어** 옵션이 활성화되어 있습니다.  이 옵션을 사용하면 템플릿에서 만들려는 새 항목의 프로그래밍 언어를 선택할 수 있습니다.  
  
## 예제  
 다음 예제에서는 **언어** 드롭다운 옵션을 표시하도록 지정합니다.  
  
```  
<VSTemplate Version="3.0.0" Type="Project"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>  
    <TemplateData>  
        <Name>MyWebProjecStarterKit</Name>  
        <Description>A simple Web template</Description>  
        <Icon>icon.ico</Icon>  
        <ProjectType>Web</ProjectType>  
        <ProjectSubType>CSharp</ProjectSubType>  
        <DefaultName>WebSite</DefaultName>  
        <SupportsLanguageDropDown>true</SupportsLanguageDropDown>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="WebApplication.webproj">  
            <ProjectItem>icon.ico</ProjectItem>  
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>  
            <ProjectItem>Default.aspx.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)