---
title: "대체 가능 매개 변수"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "대체 가능 매개 변수[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 대체 가능 매개 변수"
  - "Visual Studio에서 SharePoint 개발, 토큰"
  - "토큰[Visual Studio에서 SharePoint 개발]"
ms.assetid: 3c46bbb1-0a98-495c-9fd1-dc57a6aedc11
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# 대체 가능 매개 변수
  바꿀 수 있는 매개 변수, 즉 *토큰*을 프로젝트 파일 내에 사용하여 디자인 타임에 실제 값을 알 수 없는 SharePoint 솔루션 항목의 값을 제공할 수 있습니다.  그들은 기능적으로 표준 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 템플릿 토큰과 비슷합니다.  자세한 내용은 [템플릿 매개 변수](../ide/template-parameters.md)을 참조하십시오.  
  
## 토큰 형식  
 토큰은 달러 기호\($\) 문자로 시작하고 끝납니다.  모든 토큰은 배포 시 프로젝트를 SharePoint 솔루션 패키지 파일\(.wsp\)로 패키징할 때 실제 값으로 바뀝니다.  예를 들어 **$SharePoint.Package.Name$** 토큰은 "SharePoint 패키지 테스트" 문자열로 확인될 수 있습니다.  
  
## 토큰 규칙  
 토큰에 적용되는 규칙은 다음과 같습니다.  
  
-   줄의 어느 곳에나 토큰을 지정할 수 있습니다.  
  
-   여러 줄에 걸쳐 토큰을 입력할 수 없습니다.  
  
-   한 줄과 한 파일에 동일한 토큰을 여러 번 지정할 수 있습니다.  
  
-   한 줄에 여러 토큰을 지정할 수 있습니다.  
  
 이러한 규칙을 따르지 않는 토큰은 무시되며 경고나 오류가 표시되지 않습니다.  
  
 매니페스트를 변환하고 나면 그 즉시 토큰이 문자열 값으로 대체되므로 사용자가 토큰을 사용하여 매니페스트 템플릿을 편집할 수 있습니다.  
  
### 토큰 이름 확인  
 대부분의 경우 토큰은 포함된 위치와 상관없이 특정 값으로 확인됩니다.  그러나 토큰이 패키지나 기능에 연결되어 있으면 토큰의 값은 포함된 위치에 따라 달라집니다.  예를 들어 Package A에 기능이 있는 경우 `$SharePoint.Package.Name$` 토큰은 "Package A"라는 값으로 확인됩니다. 동일한 기능이 Package B에 있으면 `$SharePoint.Package.Name$`은 "Package B"로 확인됩니다.  
  
## 토큰 목록  
 다음 표에서는 사용 가능한 토큰을 보여 줍니다.  
  
|Name|설명|  
|----------|--------|  
|$SharePoint.Project.FileName$|포함하는 프로젝트 파일의 이름\(예: "NewProj.csproj"\)입니다.|  
|$SharePoint.Project.FileNameWithoutExtension$|포함하는 프로젝트 파일의 이름 중 파일 확장명을 제외한 부분\(예:  "NewProj"\)입니다.|  
|$SharePoint.Project.AssemblyFullName$|포함하는 프로젝트 출력 어셈블리의 표시 이름\(강력한 이름\)입니다.|  
|$SharePoint.Project.AssemblyFileName$|포함하는 프로젝트 출력 어셈블리의 이름입니다.|  
|$SharePoint.Project.AssemblyFileNameWithoutExtension$|포함하는 프로젝트 출력 어셈블리의 이름 중 파일 확장명을 제외한 부분입니다.|  
|$SharePoint.Project.AssemblyPublicKeyToken$|문자열로 변환된 포함하는 프로젝트 출력 어셈블리의 공개 키 토큰으로서, "x2" 16진 형식의 16자로 구성됩니다.|  
|$SharePoint.Package.Name$|포함하는 패키지의 이름입니다.|  
|$SharePoint.Package.FileName$|포함하는 패키지 정의 파일의 이름입니다.|  
|$SharePoint.Package.FileNameWithoutExtension$|포함하는 패키지 정의 파일의 이름 중 확장명을 제외한 부분입니다.|  
|$SharePoint.Package.Id$|포함하는 패키지의 SharePoint ID입니다.  기능 하나를 여러 패키지에 사용하는 경우 이 값이 바뀔 수 있습니다.|  
|$SharePoint.Feature.FileName$|포함하는 기능 정의 파일의 이름\(예: Feature1.feature\)입니다.|  
|$SharePoint.Feature.FileNameWithoutExtension$|파일 확장명을 제외한 기능 정의 파일의 이름입니다.|  
|$SharePoint.Feature.DeploymentPath$|패키지의 기능이 포함된 폴더의 이름입니다.  이 토큰은 기능 디자이너의 "배포 경로" 속성과 같습니다.  "Project1\_Feature1"을 예로 들 수 있습니다.|  
|$SharePoint.Feature.Id$|포함하는 기능의 SharePoint ID입니다.  모든 기능 수준 토큰과 마찬가지로 이 토큰은 기능 외부의 패키지에 직접 추가할 수 없으며 기능을 통해 패키지에 포함되는 파일에만 사용할 수 있습니다.|  
|$SharePoint.ProjectItem.Name$|**ISharePointProjectItem.Name**에서 가져온 프로젝트 항목의 이름입니다. 이는 해당 파일 이름이 아닙니다.|  
|$SharePoint.Type.\<GUID\>.AssemblyQualifiedName$|토큰의 [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)] 와 일치하는 형식의 인증된 어셈블리 이름 입니다.  [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)] 의 형식은 소문자이며 Guid.ToString\("D"\) 형식과 일치합니다\(즉, xxxxxxxx\-xxxx\-xxxx\-xxxx\-xxxxxxxxxxxx\).|  
|$SharePoint.Type.\<GUID\>.FullName$|토큰의 GUID와 일치하는 형식의 전체 이름입니다.  GUID의 형식은 소문자이며 Guid.ToString\("D"\) 형식과 일치합니다\(즉, xxxxxxxx\-xxxx\-xxxx\-xxxx\-xxxxxxxxxxxx\).|  
  
## 토큰 대체 파일 확장명 목록에 확장명 추가  
 이론상 토큰은 패키지에 포함된 SharePoint 프로젝트 항목에 속하는 모든 파일에 사용할 수 있지만, 기본적으로 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]는 패키지 파일, 매니페스트 파일 및 확장명이 다음과 같은 파일에서만 토큰을 검색합니다.  
  
-   [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]  
  
-   ASCX  
  
-   ASPX  
  
-   Webpart  
  
-   DWP  
  
 이러한 확장명은 …\\\<program files\>\\MSBuild\\Microsoft\\VisualStudio\\v11.0\\SharePointTools 폴더에 있는 Microsoft.VisualStudio.SharePoint.targets 파일의 `<TokenReplacementFileExtensions>` 요소에 의해 정의됩니다.  
  
 하지만 목록에 파일 확장명을 더 추가할 수 있습니다.  이렇게 하려면 SharePoint 대상 파일의 \<Import\> 앞에 정의된 SharePoint 프로젝트 파일에서 임의의 PropertyGroup에 `<TokenReplacementFileExtensions>` 요소를 추가합니다.  
  
> [!NOTE]  
>  토큰은 프로젝트를 컴파일한 후에 교체되므로 컴파일 대상인 파일 형식에 대한 파일 확장명\(.cs, .vb, .resx 등\)을 추가하지 말아야 합니다.  토큰은 컴파일되지 않은 파일에서만 교체됩니다.  
  
 예를 들어 토큰 교체 파일 확장명의 목록에 ".myextension" 및 ".yourextension"이라는 파일 확장명을 추가하려면 .csproj 파일에 다음을 추가합니다.  
  
```  
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
  
 또는 .targets 파일에 직접 확장명을 추가할 수 있습니다.  하지만 이 경우 로컬 시스템에서 패키징된 모든 SharePoint 프로젝트의 확장명 목록이 변경됩니다.  이 기능은 시스템의 유일한 개발자인 경우나 대부분의 프로젝트에 필요한 경우에 편리할 수 있습니다.  그러나 이 방법은 시스템과 관련이 있기 때문에 이식성이 높지 않습니다. 따라서 이 방법을 사용하는 것보다 프로젝트 파일에 확장명을 추가하는 것이 좋습니다.  
  
## 참고 항목  
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  