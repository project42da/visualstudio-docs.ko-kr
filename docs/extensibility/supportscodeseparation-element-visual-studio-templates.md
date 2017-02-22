---
title: "SupportsCodeSeparation 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#SupportsCodeSeparation"
helpviewer_keywords: 
  - "<SupportsCodeSeparation> 요소[Visual Studio 템플릿]"
  - "SupportsCodeSeparation 요소[Visual Studio 템플릿]"
ms.assetid: 8112aac8-a269-40e5-b92b-9b9a6ff5a542
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# SupportsCodeSeparation 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**새 항목 추가** 대화 상자에서 **다른 파일에 코드 입력** 확인란이 활성화되는지 여부를 지정합니다.  
  
## 구문  
  
```  
<SupportsCodeSeparation> true/false </SupportsCodeSeparation>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿을 분류하고 **새 프로젝트** 또는 **새 항목** 대화 상자에 템플릿을 표시하는 방법을 정의합니다.|  
  
## 텍스트 값  
 텍스트 값이 필요합니다.  
  
 텍스트는 **새 항목 추가** 대화 상자에서 **다른 파일에 코드 입력** 확인란이 활성화되는지 여부를 나타내는 `true` 또는 `false`여야 합니다.  
  
## 설명  
 `SupportsCodeSeparation`은 선택적 요소입니다.  기본값은 `false`입니다.  
  
 `SupportsCodeSeparation` 요소는 웹 항목 템플릿에서만 사용할 수 있습니다.  
  
 코드 구분 또는 코드 숨김 페이지 모델을 사용하여 태그와 프로그래밍 코드를 각각 다른 파일에 유지할 수 있습니다.  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 및 기타 .NET 언어에서 이 모델을 사용합니다.  
  
## 예제  
 다음 예제에서는 **다른 파일에 코드 입력** 옵션을 표시하도록 지정합니다.  
  
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
        <SupportsCodeSeparation>true</SupportsCodeSeparation>  
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