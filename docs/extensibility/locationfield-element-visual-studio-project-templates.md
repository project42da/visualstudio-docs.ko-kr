---
title: LocationField 요소 (Visual Studio 프로젝트 템플릿) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#LocationField
helpviewer_keywords:
- LocationField element [Visual Studio project templates]
ms.assetid: 6aaaa155-6ce0-4f7f-aa50-8d63d7a7c992
caps.latest.revision: 13
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1aa4acf4b0d2aeb83e4ea4feb70ace3ae55ea2b2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="locationfield-element-visual-studio-project-templates"></a>LocationField 요소(Visual Studio 프로젝트 템플릿)
지정 여부는 **위치** 텍스트 상자에 **새 프로젝트** 대화 상자가 활성화, 비활성화 또는 프로젝트 템플릿에 대 한 숨겨진 합니다.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<LocationField >  
  
## <a name="syntax"></a>구문  
  
```  
<LocationField> Enabled/Disabled/Hidden </LocationField>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿을 분류 하 고 표시 하는 방법을 정의 **새 프로젝트**합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 필수입니다.  
  
 유효한 텍스트 값은 같습니다.  
  
-   `Enabled`를 지정 하는 **위치** 상자는 **새 프로젝트** 대화 상자가 활성화 됩니다.  
  
-   `Disabled`를 지정 하는 **위치** 의 상자는 **새 프로젝트** 대화 상자는 비활성화 됩니다.  
  
-   `Hidden`를 지정 하는 **위치** 의 상자는 **새 프로젝트** 대화 상자가 숨겨집니다.  
  
## <a name="remarks"></a>설명  
 기본값은 `Enabled`입니다.  
  
 **위치** 텍스트 상자에 **새 프로젝트** 대화 상자를 사용 하면 사용자가 새 프로젝트가 저장 되는 기본 디렉터리를 변경할 수 있습니다.  
  
 에 지정 된 값은 `Location` 요소 기본 프로젝트 시스템에서 지원할 경우에 대화 상자에 의해 적용 됩니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 템플릿의 메타데이터를 보여 줍니다.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <LocationField>Disabled</LocationField>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)