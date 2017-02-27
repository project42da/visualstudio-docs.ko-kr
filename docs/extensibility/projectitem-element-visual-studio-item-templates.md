---
title: "ProjectItem 요소(Visual Studio 항목 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem"
helpviewer_keywords: 
  - "<ProjectItem> 요소[Visual Studio 항목 템플릿]"
  - "ProjectItem 요소[Visual Studio 항목 템플릿]"
ms.assetid: 9ed94112-0c38-49df-b728-0dd2d0d1eb47
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# ProjectItem 요소(Visual Studio 항목 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

항목 템플릿에 포함되어 있는 파일을 지정합니다.  
  
> [!NOTE]
>  `ProjectItem` 요소는 템플릿이 프로젝트용인지 항목용인지에 따라 다른 특성을 사용합니다.  이 항목에서는 항목의 `ProjectItem` 요소에 대해 설명합니다.  프로젝트 템플릿의 `ProjectItem` 요소에 대한 설명은 [ProjectItem 요소\(Visual Studio 프로젝트 템플릿\)](../extensibility/projectitem-element-visual-studio-project-templates.md)를 참조하십시오.  
  
## 구문  
  
```  
<ProjectItem  
    SubType="Form/Component/CustomControl/UserControl"  
    CustomTool="string"  
    ItemType="string"  
    ReplaceParameters="true/false"  
    TargetFileName="TargetFileName.ext">  
        FileName.ext  
</ProjectItem>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`SubType`|선택적 특성입니다.<br /><br /> 다중 파일 항목 템플릿에 있는 항목의 하위 형식을 지정합니다.  이 값은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 항목을 여는 데 사용할 편집기를 결정하는 데 사용됩니다.|  
|`CustomTool`|선택적 특성입니다.<br /><br /> 프로젝트 파일에서 항목의 사용자 지정 도구를 설정합니다.|  
|`ItemType`|선택적 특성입니다.<br /><br /> 프로젝트 파일에서 항목의 항목 형식을 설정합니다.|  
|`ReplaceParameters`|선택적 특성입니다.<br /><br /> 프로젝트가 템플릿에서 만들어지는 경우 항목에 대체해야 할 매개 변수 값이 있는지 여부를 지정하는 부울 값입니다.  기본값은 `false`으로,|  
|`TargetFileName`|선택적 특성입니다.<br /><br /> 템플릿에서 만들어지는 항목의 이름을 지정합니다.  이 특성은 매개 변수 대체를 사용하여 항목 이름을 만드는 데 유용합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|템플릿 내용을 지정합니다.|  
  
## 텍스트 값  
 텍스트 값이 필요합니다.  
  
 템플릿 .zip 파일에 있는 파일의 이름을 나타내는 `string`입니다.  
  
## 설명  
 `ProjectItem`은 `TemplateContent`의 선택적 자식입니다.  
  
 `TargetFileName` 특성은 매개 변수를 사용하여 파일 이름을 바꾸는 데 사용될 수 있습니다.  예를 들어, `MyFile.vb` 파일이 템플릿 .zip 파일의 루트 디렉터리에 있지만 **새 항목 추가** 대화 상자에서 사용자가 제공한 파일 이름에 따라 파일 이름을 지정하려는 경우 다음 XML을 사용합니다.  
  
```  
<ProjectItem TargetFileName="$fileinputname$.vb">MyFile.vb</ProjectItem>  
```  
  
 항목이 이 템플릿에서 만들어지는 경우 파일 이름은 **새 항목 추가** 대화 상자에서 사용자가 입력한 이름을 기반으로 합니다.  이것은 다중 파일 항목 템플릿을 만드는 데 유용합니다.  자세한 내용은 [방법: 다중 파일 항목 템플릿 만들기](../ide/how-to-create-multi-file-item-templates.md) 및 [템플릿 매개 변수](../ide/template-parameters.md)를 참조하십시오.  
  
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
 [방법: 다중 파일 항목 템플릿 만들기](../ide/how-to-create-multi-file-item-templates.md)   
 [템플릿 매개 변수](../ide/template-parameters.md)