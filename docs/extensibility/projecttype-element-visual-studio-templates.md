---
title: ProjectType 요소 (Visual Studio 템플릿) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectType
helpviewer_keywords:
- ProjectType element [Visual Studio project templates]
ms.assetid: ccf9d83f-c7f3-49c7-a31f-e1f22bec004c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bb16116994648ec70c770af7ca4932cd1443bd30
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="projecttype-element-visual-studio-templates"></a>ProjectType 요소(Visual Studio 템플릿)
지정 된 그룹에 아래에 나타나는 프로젝트 템플릿을 분류는 **새 프로젝트** 또는 **새 항목 추가** 대화 상자.  
  
> [!WARNING]
>  Visual Studio 2012에서 시작 하는 c + +에 대 한 프로젝트 템플릿은 사용할 수 있습니다. Visual Studio 2010 및 이전 버전의 c + +에 대 한 지원 되지 않습니다.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<ProjectType >  
  
## <a name="syntax"></a>구문  
  
```  
<ProjectType> CSharp/VisualBasic/VC/Web </ProjectType>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|템플릿을 분류하고 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에서 템플릿이 표시되는 방식을 정의합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 필수입니다.  
  
 이 값 지정 서식 파일 프로젝트의 형식을 만들고, 다음 값 중 하나를 포함 해야 합니다.  
  
-   `CSharp`: 서식 파일을 만들도록 지정는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 프로젝트 또는 항목입니다.  
  
-   `VisualBasic`: 서식 파일을 만들도록 지정는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 프로젝트 또는 항목입니다.  
  
-   `Web`: 템플릿이 웹 프로젝트 또는 항목을 만들도록 지정 합니다. 경우는 `ProjectType` 프로젝트 또는 항목의 언어에 정의 된,이 값을 포함 하는 요소는 [ProjectSubType 요소 (Visual Studio 템플릿)](../extensibility/projectsubtype-element-visual-studio-templates.md)합니다.  
  
## <a name="remarks"></a>설명  
 `ProjectType`은 `TemplateData`의 필수 자식 요소입니다.  
  
 값은 `ProjectType` 요소에서 서식 파일의 위치 지정는 **새 프로젝트** 또는 **새 항목 추가** 대화 상자. 예를 들어 있는 템플릿을 `ProjectType` 값 `CSharp` 아래에 표시는 **Visual C#** 에서 노드는 **새 프로젝트** 대화 상자.  
  
 Template 하위 유형의 사용 하 여 지정할 수는 [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) 요소입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 프로젝트 템플릿에 대 한 메타 데이터는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 응용 프로그램입니다.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyStarterKit.csproj">  
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
 [ProjectSubType 요소(Visual Studio 템플릿)](../extensibility/projectsubtype-element-visual-studio-templates.md)