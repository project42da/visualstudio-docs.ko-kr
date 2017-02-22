---
title: "MaxFrameworkVersion 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "<MaxFrameworkVersion> 요소(Visual Studio 템플릿)"
  - "MaxFrameworkVersion 요소(Visual Studio 템플릿)"
ms.assetid: f732a9d3-fc29-405b-9298-01ea83fc58b8
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# MaxFrameworkVersion 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

템플릿에서 요구하는 .NET Framework의 최대 버전을 지정합니다.  템플릿이 **새 프로젝트 추가** 대화 상자의 **대상 Framework 버전** 상자에서 선택하는 값을 기반으로 하여 **새 프로젝트 추가** 대화 상자의 **템플릿** 섹션에 표시되는지 확인합니다.  
  
## 구문  
  
```  
<MaxFrameworkVersion> ... </MaxFrameworkVersion>  
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
  
 텍스트는 템플릿에서 허용되는 가장 높은 버전의 .NET Framework여야 합니다.  
  
## 설명  
 `MaxFrameworkVersion`은 선택적 요소입니다.  .vstemplate 파일의 `TemplateData` 섹션 내 요소는 **새 프로젝트 추가** 대화 상자의 **템플릿** 섹션의 필터 역할을 합니다.  템플릿이 **새 프로젝트 추가** 대화 상자의 **대상 Framework 버전** 상자에서 선택하는 값을 기반으로 하여 `MaxFrameworkVersion` 요소 값보다 작은 .NET Framework 요구 사항을 가진 템플릿만 표시됩니다.  `MaxFrameworkVersion` 요소는 필수가 아닌 경우에는 생략해야 하므로 최신 .NET Framework의 버전에 사용되는 경우 템플릿이 실수로 표시되지 않도록 해야 합니다.  
  
## 예제  
 다음 예제에서는 표준 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 클래스 템플릿에 대한 메타데이터를 보여 줍니다.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class template.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <MaxFrameworkVersion>3.5</MaxFrameworkVersion>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 이 예제에서 `MaxFrameworkVersion`에 표시되는 템플릿에 필요한 .NET Framework의 최대 버전은 3.5입니다.  위 템플릿은 **새 프로젝트 추가** 대화 상자의 **대상 프레임워크 버전** 상자에서 3.0 또는 3.5를 선택할 경우에만 표시됩니다.  
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)