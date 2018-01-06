---
title: "ProjectItem 요소 (Visual Studio 프로젝트 템플릿) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem
helpviewer_keywords:
- ProjectItem element [Visual Studio project templates]
- <ProjectItem> element [Visual Studio project templates]
ms.assetid: 82879fbe-7756-42cd-9a07-c10edf5b4673
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ca5143a3e5eaff488fee89b643a40adb60473bd8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="projectitem-element-visual-studio-project-templates"></a>ProjectItem 요소(Visual Studio 프로젝트 템플릿)
프로젝트 템플릿에 포함 되어 있는 파일을 지정 합니다.  
  
> [!NOTE]
>  `ProjectItem` 요소는 프로젝트 또는 항목에 대 한 서식 파일 인지에 따라 서로 다른 특성을 수락 합니다. 이 항목에 설명 된 `ProjectItem` 프로젝트 템플릿에 대 한 요소입니다. 에 대 한 설명은 `ProjectItem` 요소 항목 템플릿에 대 한 참조 [ProjectItem 요소 (Visual Studio 항목 템플릿)](../extensibility/projectitem-element-visual-studio-item-templates.md)합니다.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Project>  
 \<프로젝트 항목 >  
  
## <a name="syntax"></a>구문  
  
```  
<ProjectItem  
    TargetFileName="TargetFileName.ext"  
    ReplaceParameters="true/false"  
    OpenInEditor="true/false"  
    OpenInWebBrowser="true/false"  
    OpenInHelpBrowser="true/false"  
    OpenOrder="Value">  
        FileName.ext  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`TargetFileName`|선택적 특성입니다.<br /><br /> 서식 파일에서 프로젝트를 만들 때 이름 및 프로젝트 항목의 경로 지정 합니다. 이 특성은 항목 이름을 만드는 데 사용 되는 매개 변수를 대체 하거나 템플릿.zip 파일의 디렉터리 구조와에서 다른 디렉터리 구조를 만드는 데 유용 합니다.|  
|`ReplaceParameters`|선택적 특성입니다.<br /><br /> 항목 템플릿에서 프로젝트를 만들 때 교체 해야 하는 매개 변수 값에 있는지 여부를 지정 하는 부울 값입니다. 기본값은 `false`여야 합니다.|  
|`OpenInEditor`|선택적 특성입니다.<br /><br /> 항목을에서 각각의 편집기에서 열 수 있는지 여부를 지정 하는 부울 값 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 템플릿에서 만들어질 때.<br /><br /> `OpenInWebBrowser` 및 `OpenInHelpBrowser` 있는 항목에서 특성이 무시 됩니다.는 `OpenInEditor` 값 `true`합니다.<br /><br /> 기본값은 `false`입니다.|  
|`OpenInWebBrowser`|선택적 특성입니다.<br /><br /> 항목은 열 수 있는지 웹 브라우저는 템플릿에서 프로젝트를 만들 때 지정 하는 부울 값입니다.<br /><br /> 웹 브라우저에서 HTML 파일 및 프로젝트에 있는 텍스트 파일을 열 수 있습니다. 외부 Url이이 특성으로 열 수 없습니다.<br /><br /> 기본값은 `false`입니다.|  
|`OpenInHelpBrowser`|선택적 특성입니다.<br /><br /> 서식 파일에서 프로젝트를 만들 때 도움말 뷰어에서 항목을 열 해야 하는지 여부를 지정 하는 부울 값입니다.<br /><br /> 도움말 브라우저에서 HTML 파일 및 프로젝트에 있는 텍스트 파일을 열 수 있습니다. 외부 Url이이 특성으로 열 수 없습니다.<br /><br /> 기본값은 `false`입니다.|  
|`OpenOrder`|선택적 특성입니다.<br /><br /> 항목 각각의 편집기에서 열리는 순서를 나타내는 숫자 값을 지정 합니다. 모든 값에 10의 배수 여야 합니다. 높은 항목을 `OpenOrder` 값 먼저 열립니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[프로젝트](../extensibility/project-element-visual-studio-templates.md)|파일 또는 프로젝트에 추가할 디렉터리를 지정 합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 필수입니다.  
  
 A `string` 템플릿.zip 파일의 파일 이름 또는 경로 나타내는입니다.  
  
## <a name="remarks"></a>설명  
 `ProjectItem`선택적 자식은 `Project`합니다.  
  
 `TargetFileName` 특성 템플릿.zip 파일의 디렉터리 구조와에서 다른 디렉터리 구조를 만드는 데 사용할 수 있습니다. 예를 들어 경우 파일 `MyFile.vb` 템플릿.zip 파일의 루트에 있는 파일을 디렉터리에 있지만 `CustomFiles` 템플릿에서 만든 모든 프로젝트에서 다음 XML을 사용:  
  
```  
<ProjectItem TargetFileName="CustomFiles\MyFile.vb">MyFile.vb</ProjectItem>  
```  
  
 `TargetFileName` 특성은 파일 이름에 국제 문자가 포함 된 파일 이름을 바꾸는 데 사용할 수도 있습니다. 예를 들어 템플릿.zip 파일.zip 파일로 압축 하기 전에 파일 이름을 바꿀 수 있도록 파일 이름은 유니코드 문자를 포함할 수 없습니다. `TargetFileName` 파일 이름을 원래 유니코드 파일 이름으로 다시 설정 하려면 특성을 사용할 수 있습니다.  
  
 `TargetFileName` 특성 매개 변수를 사용 하는 파일 이름을 바꾸는 데 사용할 수도 있습니다. 다음 절차에서는 파일 이름을 변경 하는 방법에 설명 `MyFile.vb`, 프로젝트 이름을 기반으로 하는 파일 이름에 템플릿.zip 파일의 루트 디렉터리에 존재 하는 합니다.  
  
### <a name="to-rename-files-with-parameters"></a>매개 변수를 사용 하 여 파일의 이름을 바꾸려면  
  
1.  .Vstemplate 파일에 다음 XML을 사용 합니다.  
  
    ```  
    <ProjectItem TargetFileName="$safeprojectname$.vb">MyFile.vb</ProjectItem>  
    ```  
  
2.  프로젝트 파일을 엽니다 (.vbproj에 대 한는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 프로젝트)의 텍스트 편집기에서 또는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
3.  다음 XML 유사한 프로젝트 파일의 줄을 찾습니다.  
  
    ```  
    <Compile Include="MyFile.vb">  
    ```  
  
4.  다음 XML 코드 줄을 바꿉니다.  
  
    ```  
    <Compile Include="$safeprojectname$.vb">  
    ```  
  
     파일 이름은에 입력 한 사용자 이름에 기반 합니다이 템플릿에서 프로젝트를 만들면는 **새 프로젝트** 대화 상자에서 모든 안전 하지 않은 문자 및 공백을 제거 합니다. 자세한 내용은 참조 [템플릿 매개 변수](../ide/template-parameters.md)합니다.  
  
## <a name="example"></a>예  
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
            <ProjectItem ReplaceParameters="true">Form1.cs<ProjectItem>  
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
 [템플릿 매개 변수](../ide/template-parameters.md)   
 [ProjectItem 요소(Visual Studio 항목 템플릿)](../extensibility/projectitem-element-visual-studio-item-templates.md)