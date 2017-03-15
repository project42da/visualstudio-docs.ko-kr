---
title: "DefaultName 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#DefaultName"
helpviewer_keywords: 
  - "DefaultName 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: 0ff056c8-b9d2-4747-9308-92adf1811491
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# DefaultName 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로젝트 또는 항목이 만들어질 때 Visual Studio 프로젝트 시스템이 생성할 이름을 지정합니다.  
  
## 구문  
  
```  
<DefaultName>  
    Default Project Name  
</DefaultName>  
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
  
 이 텍스트는 프로젝트나 항목의 기본 이름을 지정합니다.  
  
## 설명  
 `DefaultName`은 선택적 요소입니다.  
  
 프로젝트의 경우 이 요소는 프로젝트를 저장하는 디스크 상의 디렉터리 이름을 지정합니다.  항목의 경우 이것은 소스 파일의 파일 이름을 지정합니다.  
  
 프로젝트 또는 항목을 만들 때 사용 하 여 기본 이름을 수정할 수 있습니다의  **이름** 에서 사용할 수 있는 옵션을의  **새 프로젝트** 대화 상자 또는  **새 항목 추가** 대화 상자.  
  
 프로젝트 시스템이 프로젝트나 항목의 기본 이름을 생성하지 않도록 하려면 [ProvideDefaultName](../extensibility/providedefaultname-element-visual-studio-templates.md) 요소를 `False`로 설정합니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 클래스의 표준 항목 템플릿에 대한 메타데이터를 보여 줍니다.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <DefaultName>MyClass.cs</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem ReplaceParameters="true">MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)