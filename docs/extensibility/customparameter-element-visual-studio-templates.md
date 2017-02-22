---
title: "CustomParameter 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameter"
helpviewer_keywords: 
  - "CustomParameters 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: 743c4489-74ac-403a-bbaa-eed7d785a3ac
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# CustomParameter 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로젝트나 항목이 템플릿에서 만들어지는 경우 사용할 사용자 지정 매개 변수 이름과 값이 들어 있습니다.  
  
## 구문  
  
```  
<CustomParameter Name="name" Value="value">  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`Name`|필수 요소.  매개 변수의 이름입니다.  매개 변수의 형식은 $*name*$입니다.|  
|`Value`|필수 요소.  매개 변수의 대체 값입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[CustomParameters](../extensibility/customparameters-element-visual-studio-templates.md)|템플릿 마법사가 매개 변수를 대체할 때 이 마법사로 전달될 사용자 지정 매개 변수를 그룹화합니다.|  
  
## 설명  
 템플릿에 `CustomParameter` 요소가 있는 경우 `Name` 특성의 모든 인스턴스는 만들어진 프로젝트나 항목 파일에서 `Value` 특성으로 바뀝니다.  
  
## 예제  
 다음 예제에서는 템플릿에서 몇 개의 사용자 지정 매개 변수를 사용하는 방법을 보여 줍니다.  다음 사용자 지정 매개 변수를 사용하여 템플릿에서 프로젝트나 항목을 만드는 경우 템플릿 파일에 있는 `$color1$` 및 `$color2$`의 모든 인스턴스는 각각 `Red` 및 `Blue`로 바뀝니다.  
  
```  
<CustomParameters>  
    <CustomParameter Name="$color1$" Value="Red"/>  
    <CustomParameter Name="$color2$" Value="Blue "/>  
</CustomParameters>  
```  
  
## 참고 항목  
 [CustomParameters 요소\(Visual Studio 템플릿\)](../extensibility/customparameters-element-visual-studio-templates.md)   
 [템플릿 매개 변수](../ide/template-parameters.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)