---
title: "ProjectItem 요소(Visual Studio 프로젝트 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem"
helpviewer_keywords: 
  - "<ProjectItem> 요소[Visual Studio 프로젝트 템플릿]"
  - "ProjectItem 요소[Visual Studio 프로젝트 템플릿]"
ms.assetid: 82879fbe-7756-42cd-9a07-c10edf5b4673
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# ProjectItem 요소(Visual Studio 프로젝트 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로젝트 템플릿에 포함되어 있는 파일을 지정합니다.  
  
> [!NOTE]
>  `ProjectItem` 요소는 템플릿이 프로젝트용인지 항목용인지에 따라 다른 특성을 사용합니다.  이 항목에서는 프로젝트 템플릿의 `ProjectItem` 요소에 대해 설명합니다.  항목 템플릿의 `ProjectItem` 요소에 대한 설명은 [ProjectItem 요소\(Visual Studio 항목 템플릿\)](../extensibility/projectitem-element-visual-studio-item-templates.md)를 참조하십시오.  
  
## 구문  
  
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
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`TargetFileName`|선택적 특성입니다.<br /><br /> 프로젝트가 템플릿에서 만들어지는 경우 프로젝트 항목의 이름과 경로를 지정합니다.  이 특성은 템플릿 .zip 파일에 있는 디렉터리 구조와 다른 디렉터리 구조를 만들거나, 매개 변수 대체를 사용하여 항목 이름을 만드는 경우 유용합니다.|  
|`ReplaceParameters`|선택적 특성입니다.<br /><br /> 프로젝트가 템플릿에서 만들어지는 경우 항목에 대체해야 할 매개 변수 값이 있는지 여부를 지정하는 부울 값입니다.  기본값은 `false`으로,|  
|`OpenInEditor`|선택적 특성입니다.<br /><br /> 프로젝트가 템플릿에서 만들어지는 경우 항목이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 각각의 편집기에 열려야 하는지 여부를 지정하는 부울 값입니다.<br /><br /> `OpenInWebBrowser` 및 `OpenInHelpBrowser` 특성은 `OpenInEditor` 값이 `true`인 항목에서 무시됩니다.<br /><br /> 기본값은 `false`입니다.|  
|`OpenInWebBrowser`|선택적 특성입니다.<br /><br /> 프로젝트가 템플릿에서 만들어지는 경우 항목이 웹 브라우저에서 열려야 하는지 여부를 지정하는 부울 값입니다.<br /><br /> 프로젝트에 로컬인 HTML 파일과 텍스트 파일만 웹 브라우저에서 열릴 수 있습니다.  외부 URL은 이 특성으로 열릴 수 없습니다.<br /><br /> 기본값은 `false`입니다.|  
|`OpenInHelpBrowser`|선택적 특성입니다.<br /><br /> 프로젝트가 템플릿에서 만들어지는 경우 항목이 도움말 뷰어에서 열려야 하는지 여부를 지정하는 부울 값입니다.<br /><br /> 프로젝트에 로컬인 HTML 파일과 텍스트 파일만 도움말 브라우저에서 열 수 있습니다.  외부 URL은 이 특성으로 열릴 수 없습니다.<br /><br /> 기본값은 `false`입니다.|  
|`OpenOrder`|선택적 특성입니다.<br /><br /> 항목이 각각의 편집기에서 열릴 순서를 나타내는 숫자 값을 지정합니다.  모든 값은 10의 배수여야 합니다.  상위 항목 `OpenOrder` 값을 먼저 열립니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[프로젝트](../extensibility/project-element-visual-studio-templates.md)|프로젝트에 추가할 파일 또는 디렉터리를 지정합니다.|  
  
## 텍스트 값  
 텍스트 값이 필요합니다.  
  
 템플릿 .zip 파일에 있는 파일 이름 또는 경로를 나타내는 `string`입니다.  
  
## 설명  
 `ProjectItem`은 `Project`의 선택적 자식입니다.  
  
 `TargetFileName` 특성은 템플릿 .zip 파일에 있는 디렉터리 구조와 다른 디렉터리 구조를 만드는 데 사용될 수 있습니다.  예를 들어, `MyFile.vb` 파일이 템플릿 .zip 파일의 루트에 있지만 해당 파일을 템플릿에서 만들어진 모든 프로젝트에서 `CustomFiles`라는 디렉터리에 배치하려는 경우 다음 XML을 사용합니다.  
  
```  
<ProjectItem TargetFileName="CustomFiles\MyFile.vb">MyFile.vb</ProjectItem>  
```  
  
 `TargetFileName` 특성은 파일 이름에 국가별 문자가 들어 있는 파일의 이름을 바꾸는 데도 사용될 수 있습니다.  예를 들어, 템플릿 .zip 파일은 유니코드 문자가 있는 파일 이름을 포함할 수 없으므로 해당 파일을 .zip 파일로 압축하기 전에 이름을 바꾸어야 합니다.  `TargetFileName` 특성을 사용하여 파일 이름을 다시 원래의 유니코드 파일 이름으로 설정할 수 있습니다.  
  
 `TargetFileName` 특성은 매개 변수를 사용하여 파일 이름을 바꾸는 데 사용될 수도 있습니다.  다음 절차에서는 템플릿 .zip 파일의 루트 디렉터리에 있는 `MyFile.vb` 파일의 이름을 프로젝트 이름을 기반으로 한 파일 이름으로 바꾸는 방법을 설명합니다.  
  
### 매개 변수로 파일 이름을 바꾸려면  
  
1.  .vstemplate 파일에서 다음 XML을 사용합니다.  
  
    ```  
    <ProjectItem TargetFileName="$safeprojectname$.vb">MyFile.vb</ProjectItem>  
    ```  
  
2.  텍스트 편집기 또는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 프로젝트 파일\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 프로젝트의 경우 .vbproj\)을 엽니다.  
  
3.  프로젝트 파일에서 다음 XML과 비슷한 줄을 찾습니다.  
  
    ```  
    <Compile Include="MyFile.vb">  
    ```  
  
4.  이 코드 줄을 다음 XML로 바꿉니다.  
  
    ```  
    <Compile Include="$safeprojectname$.vb">  
    ```  
  
     프로젝트가 이 템플릿에서 만들어지는 경우 파일 이름은 **새 프로젝트** 대화 상자에서 사용자가 입력한 이름에 따라 지정됩니다. 이때 안전하지 않은 문자와 공백은 모두 제거됩니다.  자세한 내용은 [템플릿 매개 변수](../ide/template-parameters.md)을 참조하십시오.  
  
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
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [템플릿 매개 변수](../ide/template-parameters.md)   
 [ProjectItem 요소\(Visual Studio 항목 템플릿\)](../extensibility/projectitem-element-visual-studio-item-templates.md)