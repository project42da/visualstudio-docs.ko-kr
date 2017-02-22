---
title: "ProvideDefaultName 요소(Visual Studio 템플릿) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/developer/vstemplate/2005#ProvideDefaultName"
helpviewer_keywords: 
  - "ProvideDefaultName 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: 7b0e7b20-fd6b-42e2-81d0-e5100cea0528
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# ProvideDefaultName 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 시스템이 **새 항목 추가** 또는 **새 프로젝트** 대화 상자에서 템플릿의 기본 이름을 생성하는지 여부를 지정합니다.  
  
## 구문  
  
```  
<ProvideDefaultName> true/false </ProvideDefaultName>  
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
  
 텍스트는 **새 항목 추가** 또는 **새 프로젝트** 대화 상자에 템플릿의 기본 이름을 생성하는지 여부를 나타내는 `true` 또는 `false`여야 합니다.  
  
## 설명  
 `ProvideDefaultName`은 선택적 요소입니다.  기본값은 `true`입니다.  
  
 `ProvideDefaultName` 요소가 `false`인 경우 **새 항목 추가** 및 **새 프로젝트** 대화 상자의 **이름** 상자에는 `<이름 입력>` 값이 들어 있습니다.  
  
 [DefaultName](../extensibility/defaultname-element-visual-studio-templates.md) 요소를 사용하여 **새 항목 추가** 및 **새 프로젝트** 대화 상자에 프로젝트나 항목의 기본 이름을 지정할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 `ProvideDefaultName` 요소를 `false`로 설정합니다.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <ProvideDefaultName>false</ProvideDefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)