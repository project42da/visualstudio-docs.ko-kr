---
title: "TemplateData 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#TemplateData"
helpviewer_keywords: 
  - "TemplateData 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: db17ec9b-bfdf-46b1-bbe7-5ccc140056e2
caps.latest.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 24
---
# TemplateData 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

템플릿을 분류하고 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에 템플릿을 표시하는 방법을 정의합니다.  
  
## 구문  
  
```  
<TemplateData>  
    <Name> ... </Name>  
    <Description> ... </Description>  
    <Icon> ... </Icon>  
    <ProjectType> ... </ProjectType>  
    ...  
</TemplateData>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[이름](../extensibility/name-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> **새 프로젝트** 또는 **새 항목 추가** 대화 상자에 나타나는 템플릿 이름을 지정합니다.|  
|[설명](../extensibility/description-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> **새 프로젝트** 또는 **새 항목 추가** 대화 상자에 나타나는 템플릿 설명을 지정합니다.|  
|[아이콘](../extensibility/icon-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> **새 프로젝트** 또는 **새 항목 추가** 대화 상자에 나타나는 템플릿의 아이콘으로 사용되는 이미지 파일의 경로와 파일 이름을 지정합니다.|  
|[ProjectType](../extensibility/projecttype-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> **새 프로젝트** 대화 상자의 지정된 그룹에 나타나도록 프로젝트 템플릿을 분류합니다.|  
|[ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> **새 프로젝트** 대화 상자의 지정된 하위 범주에 나타나도록 프로젝트 템플릿을 분류합니다.|  
|[TemplateID](../extensibility/templateid-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 템플릿 ID를 지정합니다.|  
|[TemplateGroupID](../extensibility/templategroupid-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 템플릿 그룹 ID를 지정합니다.|  
|[SortOrder](../extensibility/sortorder-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> **새 프로젝트** 또는 **새 항목 추가** 대화 상자에 나타낼 때 같은 범주에 있는 다른 템플릿들 사이에 템플릿을 정렬하는 데 사용되는 값을 지정합니다.|  
|[CreateNewFolder](../extensibility/createnewfolder-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 프로젝트가 인스턴스화될 때 포함하는 폴더가 만들어지는지 여부를 지정합니다.|  
|[DefaultName](../extensibility/defaultname-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 프로젝트 또는 항목이 만들어질 때 Visual Studio 프로젝트 시스템이 생성할 이름을 지정합니다.|  
|[ProvideDefaultName](../extensibility/providedefaultname-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 프로젝트 또는 항목이 만들어질 때 Visual Studio 프로젝트 시스템이 기본 이름을 생성하는지 여부를 지정합니다.|  
|[PromptForSaveOnCreation](../extensibility/promptforsaveoncreation-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 프로젝트가 임시 프로젝트로 만들어질 수 있는지 여부를 지정합니다.|  
|[EnableLocationBrowseButton](../extensibility/enablelocationbrowsebutton-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 새 프로젝트가 저장되는 기본 디렉터리를 사용자가 쉽게 수정할 수 있도록 **새 프로젝트** 대화 상자에서 **찾아보기** 단추를 사용할 수 있는지 여부를 지정합니다.|  
|[Hidden](../extensibility/hidden-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> **새 프로젝트** 또는 **새 항목 추가** 대화 상자에 템플릿이 나타나는지 여부를 지정합니다.|  
|[NumberOfParentCategoriesToRollUp](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> **새 프로젝트** 대화 상자에 템플릿을 표시할 부모 범주의 수를 지정합니다.|  
|[LocationFieldMRUPrefix](../extensibility/locationfieldmruprefix-element-visual-studio-templates.md)|선택적 요소입니다.|  
|[LocationField](../extensibility/locationfield-element-visual-studio-project-templates.md)|선택적 요소입니다.<br /><br /> **새 프로젝트** 대화 상자에서 프로젝트 템플릿에 대해 **위치** 텍스트 상자가 활성화되었는지, 비활성화되었는지 아니면 숨겨져 있는지 지정합니다.|  
|[RequiredFrameworkVersion](../extensibility/requiredframeworkversion-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 템플릿이 .NET Framework의 특정 최소 버전과, 최신 버전\(있는 경우\)만 지원하는 경우 이 요소를 사용합니다.|  
|[SupportsMasterPage](../extensibility/supportsmasterpage-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 템플릿이 웹 프로젝트의 마스터 페이지를 지원하는지 여부를 지정합니다.|  
|[SupportsCodeSeparation](../extensibility/supportscodeseparation-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 템플릿이 웹 프로젝트에 대해 코드 구분을 지원하는지 코드 숨김 페이지 모델을 지원하는지를 지정합니다.|  
|[SupportsLanguageDropDown](../extensibility/supportslanguagedropdown-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 템플릿이 여러 언어에 대해 동일한지 여부와 **새 프로젝트** 대화 상자에서 **언어** 옵션을 사용할 수 있는지 여부를 지정합니다.|  
|[TargetPlatformName](../extensibility/targetplatformname-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 플랫폼을 지정 된 프로젝트 서식 파일의 대상입니다.  프로젝트 템플릿을 만드는 데 사용 되는 것이 요소를 지정 합니다. [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 응용 프로그램입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 프로젝트 템플릿, 항목 템플릿 또는 시작 키트에 대한 모든 메타데이터가 들어 있습니다.|  
  
## 설명  
 `TemplateData`는 필수 요소입니다.  
  
 선택적 요소를 포함하지 않는 경우 해당 요소의 기본값이 사용됩니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 응용 프로그램의 프로젝트 템플릿에 대한 메타데이터를 보여 줍니다.  
  
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
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)