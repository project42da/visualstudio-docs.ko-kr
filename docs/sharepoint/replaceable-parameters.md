---
title: 대체 가능 매개 변수 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, tokens
- tokens [SharePoint development in Visual Studio]
- replaceable parameters [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, replaceable parameters
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 86d6b08d209703f73901d7a839c731e1a9a63fdd
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="replaceable-parameters"></a>대체 가능 매개 변수
  대체 가능 매개 변수 또는 *토큰*, 실제 값을 갖는 디자인 타임에 알 수 없는 SharePoint 솔루션 항목에 대 한 값을 제공 합니다. 프로젝트 파일 내 사용할 수 있습니다. 이러한 매개 변수는 기능적으로 표준 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 템플릿 토큰과 유사합니다. 자세한 내용은 참조 [템플릿 매개 변수](/visualstudio/ide/template-parameters)합니다.  
  
## <a name="token-format"></a>토큰 형식  
 토큰 시작 하 고 달러 기호 ($) 문자로 끝나야 합니다. 배포에서 SharePoint 솔루션 패키지 (.wsp 파일)에 프로젝트는 패키지 될 때 사용 된 모든 토큰 실제 값으로 바뀝니다. 예를 들어 토큰 **$SharePoint.Package.Name$** 문자열 "테스트 SharePoint 패키지"으로 확인 될 수  
  
## <a name="token-rules"></a>토큰 규칙  
 토큰에는 다음 규칙이 적용 됩니다.  
  
-   토큰은 줄의 아무 곳 이나 지정할 수 있습니다.  
  
-   토큰 여러 줄으로 나누어 입력할 수 없습니다.  
  
-   동일한 토큰 같은 줄에서와 같은 파일에 여러 번 지정할 수 있습니다.  
  
-   같은 줄에 서로 다른 토큰을 지정할 수 있습니다.  
  
 이러한 규칙을 따르지 않는 토큰은 경고나 오류를 제공 하지 않고 무시 됩니다.  
  
 토큰이 문자열 값으로 대체 매니페스트 변환 후 즉시 수행 됩니다. 이 대체 토큰을 사용 하 여 매니페스트 템플릿을 편집할 수 있습니다.  
  
### <a name="token-name-resolution"></a>토큰 이름 확인  
 대부분의 경우 토큰이 포함 된 위치에 관계 없이 특정 값으로 확인 됩니다. 그러나 패키지 또는 기능에 연결 되어, 토큰의 값은 포함 된 위치에 따라 다릅니다. 예를 들어 기능에 있으면 패키지, 토큰 `$SharePoint.Package.Name$` "패키지 A." 값으로 확인 동일한 기능이 인지 패키지 b에서 다음 `$SharePoint.Package.Name$` "패키지 B."를 확인 합니다.  
  
## <a name="tokens-list"></a>토큰 목록  
 다음 표에서 사용 가능한 토큰을 나열합니다.  
  
|이름|설명|  
|----------|-----------------|  
|$SharePoint.Project.FileName$|"NewProj.csproj"와 같은 포함 된 프로젝트 파일의 이름입니다.|  
|$SharePoint.Project.FileNameWithoutExtension$|파일 이름 확장명 없이 포함 하는 프로젝트 파일의 이름입니다. 예를 들어 "NewProj"가 있습니다.|  
|$SharePoint.Project.AssemblyFullName$|포함 하는 프로젝트의 표시 이름 (강력한 이름)의 어셈블리를 출력 합니다.|  
|$SharePoint.Project.AssemblyFileName$|포함 하는 프로젝트의 출력 어셈블리의 이름입니다.|  
|$SharePoint.Project.AssemblyFileNameWithoutExtension$|이름을 포함 하는 프로젝트의 파일 이름 확장명을 제외한 어셈블리의 출력입니다.|  
|$SharePoint.Project.AssemblyPublicKeyToken$|포함 하는 프로젝트의 공개 키 토큰의 어셈블리를 문자열로 변환 된 출력입니다. ("x2" 16 자 16 진수 형식입니다.)|  
|$SharePoint.Package.Name$|포함 하는 패키지의 이름입니다.|  
|$SharePoint.Package.FileName$|포함 하는 패키지 정의 파일의 이름입니다.|  
|$SharePoint.Package.FileNameWithoutExtension$|포함 하는 패키지 정의 파일의 확장명을 제외한 이름입니다.|  
|$SharePoint.Package.Id$|포함 하는 패키지에 대 한 SharePoint ID입니다. 둘 이상의 패키지에는 기능을 사용 하는 경우이 값이 변경 됩니다.|  
|$SharePoint.Feature.FileName$|Feature1.feature 등, 포함 기능의 정의 파일의 이름입니다.|  
|$SharePoint.Feature.FileNameWithoutExtension$|기능 정의 파일의 파일 이름 확장명 없이 이름입니다.|  
|$SharePoint.Feature.DeploymentPath$|패키지에이 기능을 포함 하는 폴더의 이름입니다. 기능 디자이너에서 "배포 경로" 속성에이 토큰은 같습니다. 값의 예는 "Project1_Feature1"입니다.|  
|$SharePoint.Feature.Id$|포함 하는 기능의 SharePoint ID입니다. 이 토큰 기능을 통해 패키지에 포함 된 파일에 의해서만 모든 기능 수준이 토큰으로 사용할 수에 추가 되지 직접 기능 외부에서 패키지.|  
|$SharePoint.ProjectItem.Name$|가져온 프로젝트 항목 (해당 파일 이름 아님), 이름 **ISharePointProjectItem.Name**합니다.|  
|$SharePoint.Type 합니다. \<GUID > 합니다. AssemblyQualifiedName $|토큰의 [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)]와 일치하는 형식의 정규화된 어셈블리 이름입니다. [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)]의 형식은 소문자이며 Guid.ToString("D") 형식과 일치합니다(즉, xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|  
|$SharePoint.Type 합니다. \<GUID > 합니다. FullName $|토큰의 GUID와 일치 하는 형식의 전체 이름입니다. GUID의 형식은 소문자 이며 Guid.ToString("D") 형식에 맞는 (즉, xxxxxxxx-xxxx-xxxx-개의 자릿수)입니다.|  
  
## <a name="adding-extensions-to-the-token-replacement-file-extensions-list"></a>토큰 교체에 확장명 추가 파일 확장명 목록  
 토큰 이론상 항목 기본적으로는 패키지에 포함 된 SharePoint 프로젝트에 속하는 모든 파일에 사용할 수 있지만 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 패키지 파일과 매니페스트 파일을 다음 확장명을 가진 파일에만 토큰을 검색 합니다.  
  
-   [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]  
  
-   ASCX  
  
-   ASPX  
  
-   웹 파트  
  
-   DWP  
  
 이러한 확장명은 `<TokenReplacementFileExtensions>` 에 있는 Microsoft.VisualStudio.SharePoint.targets 파일의 요소는 중... \\< 프로그램 파일\>\MSBuild\Microsoft\VisualStudio\v11.0\SharePointTools 폴더입니다.  
  
 그러나 목록에 추가 파일 확장명을 추가할 수, 있습니다. 추가 `<TokenReplacementFileExtensions>` 앞에 정의 된 SharePoint 프로젝트 파일에서 임의의 PropertyGroup 요소는 \<가져오기 > SharePoint 대상 파일의 합니다.  
  
> [!NOTE]  
>  프로젝트를 컴파일한 후 토큰 바꾸기 나타나므로.cs,.vb,.resx 등 컴파일되는 파일 형식에 대 한 파일 확장명 추가 하지 말아야 합니다. 토큰 컴파일되지 않는 파일에만 대체 됩니다.  
  
 예를 들어 파일 이름 확장명 ".myextension" 및 ".yourextension" 토큰 대체 파일 이름 확장명의 목록에 추가 하려면 추가할 때 다음을는 `.csproj` 파일:  
  
```xml  
<Project ToolsVersion="4.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <PropertyGroup>  
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
.  
.  
.  
    <!-- Define the following property to add your extension to the list of token replacement file extensions.  -->  
<TokenReplacementFileExtensions>myextension;yourextension</TokenReplacementFileExtensions>  
</PropertyGroup>  
```  
  
 .Targets 파일에 직접 확장을 추가할 수 있습니다. 그러나 확장명 목록 뿐 아니라 로컬 시스템에 패키지 하는 모든 SharePoint 프로젝트에 대 한 변경이 직접 합니다. 시스템에서 유일한 개발자 또는 대부분의 프로젝트에서 필요한 경우 편리할 수 있습니다. 그러나 이며 때문에 시스템 관련,이 방법은 매우 이식 가능 하지 않습니다. 따라서는 것이 좋습니다 추가한 확장 프로젝트 파일을 대신 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  