---
title: "SortOrder 요소(Visual Studio 템플릿) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/developer/vstemplate/2005#SortOrder"
helpviewer_keywords: 
  - "<SortOrder> 요소[Visual Studio 템플릿]"
  - "SortOrder 요소[Visual Studio 템플릿]"
ms.assetid: 151932c1-f08a-4f78-a8d0-bd2f32211a9c
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# SortOrder 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**새 프로젝트** 또는 **새 항목 추가** 대화 상자에 나타낼 때 같은 범주에 있는 다른 템플릿들 사이에 템플릿을 정렬하는 데 사용되는 값을 지정합니다.  
  
## 구문  
  
```  
<SortOrder> ... </SortOrder>  
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
  
 정렬 순서 값을 나타내는 `integer`입니다.  
  
## 설명  
 `SortOrder`는 선택적 요소입니다.  기본값은 100이고, 모든 값은 10의 배수여야 합니다.  
  
 사용자가 만든 템플릿의 경우 `SortOrder` 요소는 무시됩니다.  사용자가 만든 모든 템플릿은 사전순으로 정렬됩니다.  
  
 정렬 순서 값이 낮은 템플릿은 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에서 정렬 순서 값이 높은 템플릿 앞에 나타납니다.  
  
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
        <SortOrder>290</SortOrder>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 이 예제에서 `SortOrder` 요소는 비교적 높습니다.  다른 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 항목 템플릿의 `SortOrder` 값은 `290`보다 낮으므로 **새 항목** 대화 상자에서 이 템플릿 앞에 나타납니다.  
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)