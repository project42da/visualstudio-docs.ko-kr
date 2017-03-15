---
title: "TemplateID 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#TemplateID"
helpviewer_keywords: 
  - "<TemplateID> 요소[Visual Studio 템플릿]"
  - "TemplateID 요소[Visual Studio 템플릿]"
ms.assetid: 6ca24b4e-0325-4a9e-855e-0cbbe7361d8f
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# TemplateID 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[TemplateGroupID](../extensibility/templategroupid-element-visual-studio-templates.md) 요소에 의해 항목 템플릿 그룹으로 분류되는 항목 템플릿의 식별자를 지정합니다.  
  
## 구문  
  
```  
<TemplateID> ... </TemplateID>  
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
 `TemplateGroupID` 요소에 의해 항목 템플릿 그룹으로 분류되는 항목 템플릿의 식별자를 나타내는 `string`입니다.  
  
## 설명  
 `TemplateID`은 선택적 요소입니다.  
  
 .vstemplate 파일에서 `TemplateID` 요소가 생략된 경우 [Name](../extensibility/name-element-visual-studio-templates.md) 요소가 템플릿의 식별자로 사용됩니다.  
  
 `TemplateID` 요소의 값은 프로젝트 시스템 등록\(\(HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\11.0\\Projects\\\)과 함께 **새 항목 추가** 대화 상자에 나타나는 템플릿을 필터링하는 데 사용됩니다.  
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)