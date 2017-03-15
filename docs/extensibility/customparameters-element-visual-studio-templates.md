---
title: "CustomParameters 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameters"
helpviewer_keywords: 
  - "CustomParameters 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: cf3efc91-1532-4022-bbb8-a18658424fee
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# CustomParameters 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 마법사에서는 매개 변수 대체를 수행 하는 경우에 템플릿 마법사 전달 될 수 있는 사용자 지정 매개 변수를 그룹화 합니다.  
  
## 구문  
  
```  
<CustomParameters>  
    <CustomParameter/>  
    <CustomParameter/>  
</CustomParameters>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[CustomParameter](../extensibility/customparameter-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 사용자 지정 매개 변수 이름 및 서식 파일에서 프로젝트 또는 항목이 만들어질 때 사용 하 여 값을 포함 합니다.`CustomParameter` 요소에는 `CustomParameters` 요소가 0개 또는 그 이상 있을 수 있습니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|서식 파일의 내용을 지정합니다.|  
  
## 설명  
  
## 예제  
 다음 예제에서는 서식 파일에 여러 사용자 지정 매개 변수를 사용 하는 방법을 보여 줍니다. 프로젝트 또는 항목이 만들어질 때 다음과 같은 사용자 지정 매개 변수를의 모든 인스턴스를 사용 하 여 템플릿에서 `$color1$` 및 `$color2$` 서식 파일에서 파일은 바뀝니다 `Red` 및 `Blue`, 각각.  
  
```  
<CustomParameters>  
    <CustomParameter Name="$color1$" Value="Red"/>  
    <CustomParameter Name="$color2$" Value="Blue "/>  
</CustomParameters>  
```  
  
## 참고 항목  
 [CustomParameter 요소\(Visual Studio 템플릿\)](../extensibility/customparameter-element-visual-studio-templates.md)   
 [템플릿 매개 변수](../ide/template-parameters.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)