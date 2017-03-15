---
title: "Reference 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#Reference"
helpviewer_keywords: 
  - "<Reference> 요소[Visual Studio 템플릿]"
  - "Reference 요소[Visual Studio 템플릿]"
ms.assetid: 852772ea-c324-42e9-8c8a-6d565414a109
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# Reference 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

항목이 프로젝트에 추가될 때 추가할 어셈블리 참조를 지정합니다.  
  
## 구문  
  
```  
<Reference>  
    <Assembly> ... </Assembly>  
</Reference>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[Assembly](../extensibility/assembly-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 어셈블리에 대한 정보를 지정합니다. 이 정보는 템플릿이 해당 어셈블리의 참조를 프로젝트에 추가하는 데 사용됩니다.  `Reference` 요소마다 `Assembly` 요소가 하나씩 있어야 합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[참조](../extensibility/references-element-visual-studio-templates.md)|템플릿이 프로젝트에 추가하는 어셈블리 참조를 그룹화합니다.|  
  
## 설명  
 `Reference`은 `References`의 필수 자식 요소입니다.  
  
 `Reference`와 `References` 요소는 `Type` 특성 값이 `Item`인 .vstemplate 파일에서만 사용될 수 있습니다.  
  
## 예제  
 다음 예제에서는 항목 템플릿의 `TemplateContent` 요소를 보여 줍니다.  이 XML은 System.dll 및 System.Data.dll 어셈블리에 대한 참조를 추가합니다.  
  
```  
<TemplateContent>  
    <References>  
        <Reference>  
            <Assembly>  
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>  
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
    </References>  
    ...  
</TemplateContent>  
```  
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)