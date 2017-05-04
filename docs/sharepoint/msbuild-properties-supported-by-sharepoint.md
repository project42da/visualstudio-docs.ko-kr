---
title: "SharePoint에서 지원하는 MSBuild 속성 | Microsoft Docs"
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
  - "Visual Studio에서 SharePoint 개발, MSBuild 속성"
ms.assetid: 7b2b58c6-55cd-4682-a5d7-43874e70920d
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# SharePoint에서 지원하는 MSBuild 속성
  Microsoft.VisualStudio.SharePoint.targets 파일, 프로젝트 파일 또는 프로젝트 사용자 파일에 정의된 모든 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 속성은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트에서 사용할 수 있습니다.  SharePoint에서는 프로젝트에서 제공하는 일반 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 속성 외에도 SharePoint 프로젝트와 관련된 추가 속성을 정의합니다.  
  
 일반적인 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 속성 목록의 경우, [일반 MSBuild 프로젝트 속성](http://go.microsoft.com/fwlink/?LinkID=168687) 을 참조하십시오.  사용하는 프로그래밍 언어에서 지원하는 속성의 전체 목록은 .targets 파일, 프로젝트 파일\(.csproj 또는 .vbproj\) 또는 프로젝트 사용자 파일\(csproj.user 또는 .vbproj.user\)에 있습니다.  
  
## SharePoint와 관련된 MSBuild 속성  
 다음 표에는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 프로젝트에만 적용되는 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 속성이 나와 있습니다.  다른 속성도 있지만 내부용입니다.  
  
|속성 이름|설명|  
|-----------|--------|  
|SharePointSiteUrl|SharePoint 사이트의 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)]을 나타내는 문자열입니다.|  
|SandboxedSolution|솔루션이 샌드박스 솔루션인지 여부를 나타내는 부울 값입니다.|  
|ActiveDeploymentConfiguration|활성 배포 구성입니다.|  
|IncludeAssemblyInPackage|어셈블리가 패키지 파일에 포함되어 있는지 여부를 나타내는 부울 값입니다.|  
|PreDeploymentCommand|배포 전 명령 단계에서 실행할 명령을 나타내는 문자열 값입니다.|  
|PostDeploymentCommand|배포 후 명령 단계에서 실행할 명령을 나타내는 문자열 값입니다.|  
|CustomBeforeSharePointTargets|[!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 대상 파일의 경로를 나타내는 문자열입니다.  대상 파일이 있고 정의되어 있는 경우 모든 SharePoint 대상 데이터 이전에 대상 파일을 가져옵니다.  이 속성을 사용하면 제공된 SharePoint 대상 파일을 수정하지 않고 패키징 관련 속성을 미리 정의하여 패키지 프로세스를 사용자 지정할 수 있습니다. 하지만 대상 파일은 여전히 모든 SharePoint 프로젝트에 적용됩니다.|  
|CustomAfterSharePointTargets|[!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 대상 파일의 경로를 나타내는 문자열입니다.  대상 파일이 있고 정의되어 있는 경우 모든 SharePoint 대상 데이터 다음에 대상 파일을 가져옵니다.  이 속성을 사용하면 제공된 SharePoint 대상 파일을 수정할 필요 없이 패키징 관련 속성 및 대상을 재정의하여 패키지 프로세스를 사용자 지정할 수 있습니다. 하지만 대상 파일은 여전히 모든 SharePoint 프로젝트에 적용됩니다.|  
|LayoutPath|패키지될 각 파일이 .wsp 파일에 추가되기 전에 임시로 배치되는 루트 디렉터리를 나타내는 문자열입니다.  BeforeLayout 및 AfterLayout 대상을 재정의하여 패키지될 파일을 추가, 제거 또는 수정하는 경우 이 경로를 사용하여 .wsp 파일의 내용을 변경할 수 있기 때문에 이 경로를 알고 있으면 유용할 수 있습니다.|  
|BasePackagePath|패키지가 배치되는 폴더를 나타내는 문자열입니다.  이 값에는 프로젝트의 출력 디렉터리가 사용됩니다\(예: Bin\\Debug\).|  
|PackageExtension|패키지에 추가할 파일 확장명을 나타내는 문자열입니다.  기본값은 wsp입니다.|  
|AssemblyDeploymentTarget|프로젝트 어셈블리가 SharePoint 서버에 배포되는 위치를 나타내는 문자열입니다.  값은 GlobalAssemblyCache\(기본값\) 또는 WebApplication입니다.  이 속성은 속성 창에서도 설정할 수 있습니다.|  
|PackageWithValidation|유효성 검사가 패키징 전에 수행되는지 여부를 지정하는 부울 값입니다.  이 속성을 설정하면 패키지를 만드는 동안 유효성 검사 오류를 무시할 수 있습니다.|  
|ValidatePackageDependsOn|ValidatePackage 대상 이전에 실행할 추가 대상을 정의하는 문자열입니다.|  
|TokenReplacementFileExensions|패키징 중에 토큰을 바꿀 파일을 정의하는 문자열입니다.|  
  
## 속성 페이지에서 MSBuild 속성 사용  
 융통성을 위해 SharePoint 속성 페이지의 **배포 전 명령줄** 및 **배포 후 명령줄** 상자에서 하드 코드된 문자열을 사용하는 대신 SharePoint 속성을 인수로 사용할 수 있습니다.  예를 들어, SharePoint 사이트에 대해 특정 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] 문자열을 지정하는 대신 `$(SharePointSiteUrl)`을 사용할 수 있습니다.  
  
> [!NOTE]  
>  [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 변수 구문 `$(`*propertyName*`)` 또는 환경 변수 구문 `%`*propertyName*`%`을 사용하여 속성을 지정할 수 있습니다.  
  
## 참고 항목  
 [MSBuild Reference](../msbuild/msbuild-reference.md)  
  
  