---
title: "ProjectItem 요소 (Visual Studio 항목 템플릿) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem
helpviewer_keywords:
- <ProjectItem> element [Visual Studio item templates]
- ProjectItem element [Visual Studio item templates]
ms.assetid: 9ed94112-0c38-49df-b728-0dd2d0d1eb47
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 035e698b0b8f34cbbefc665cc96f38a87a812e2d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="projectitem-element-visual-studio-item-templates"></a>ProjectItem 요소(Visual Studio 항목 템플릿)
항목 템플릿에 포함 되어 있는 파일을 지정 합니다.  
  
> [!NOTE]
>  `ProjectItem` 요소는 프로젝트 또는 항목에 대 한 서식 파일 인지에 따라 서로 다른 특성을 수락 합니다. 이 항목에 설명 된 `ProjectItem` 항목에 대 한 요소입니다. 에 대 한 설명은 `ProjectItem` 프로젝트 템플릿에 대 한 요소 참조 [ProjectItem 요소 (Visual Studio 프로젝트 템플릿)](../extensibility/projectitem-element-visual-studio-project-templates.md)합니다.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<프로젝트 항목 >  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`SubType`|선택적 특성입니다.<br /><br /> 다중 파일 항목 템플릿에 항목의 하위 형식을 지정합니다. 편집기를 확인 하려면이 값은 사용 하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 항목을 열 때 사용 합니다.|  
|`CustomTool`|선택적 특성입니다.<br /><br /> 프로젝트 파일에서 항목에 대 한 사용자 지정 도구를 설정합니다.|  
|`ItemType`|선택적 특성입니다.<br /><br /> 프로젝트 파일의 항목 형식을 설정합니다.|  
|`ReplaceParameters`|선택적 특성입니다.<br /><br /> 항목 템플릿에서 프로젝트를 만들 때 교체 해야 하는 매개 변수 값에 있는지 여부를 지정 하는 부울 값입니다. 기본값은 `false`여야 합니다.|  
|`TargetFileName`|선택적 특성입니다.<br /><br /> 서식 파일에서 생성 된 항목의 이름을 지정 합니다. 이 특성은 매개 변수 대체를 사용 하 여 항목 이름을 만드는 데 유용 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|서식 파일의 내용을 지정합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 필수입니다.  
  
 A `string` 템플릿.zip 파일에 있는 파일의 이름을 나타내는입니다.  
  
## <a name="remarks"></a>설명  
 `ProjectItem`선택적 자식은 `TemplateContent`합니다.  
  
 `TargetFileName` 매개 변수를 사용 하 여 파일의 이름을 바꾸려면 특성을 사용할 수 있습니다. 예를 들어 경우 파일 `MyFile.vb` 원하는 이름을 지정 하는 파일에 사용자가 제공한 파일 이름에 따라 템플릿.zip 파일의 루트 디렉터리에 있는 **새 항목 추가** 대화 상자에서 다음 XML을 사용:  
  
```  
<ProjectItem TargetFileName="$fileinputname$.vb">MyFile.vb</ProjectItem>  
```  
  
 파일 이름은에 입력 한 사용자 이름에 기반 합니다 항목이 만들어지면이 템플릿에서 **새 항목 추가** 대화 상자. 다중 파일 항목 템플릿을 만들 때 유용 합니다. 자세한 내용은 참조 [하는 방법: 다중 파일 항목 템플릿 만들기](../ide/how-to-create-multi-file-item-templates.md) 및 [템플릿 매개 변수](../ide/template-parameters.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에 대 한 표준 항목 템플릿에 대 한 메타 데이터는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 클래스입니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)   
 [방법: 다중 파일 항목 템플릿 만들기](../ide/how-to-create-multi-file-item-templates.md)   
 [템플릿 매개 변수](../ide/template-parameters.md)