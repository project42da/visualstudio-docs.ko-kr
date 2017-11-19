---
title: "MSBuild를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, compiling with MSBuild
- MSBuild, extensibility
- packages, compiling with MSBuild
ms.assetid: 9d38c388-1f64-430e-8f6c-e88bc99a4260
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a148a7c5fa6d0e72345ab7f96696a11d5ba5185f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="using-msbuild"></a>MSBuild를 사용 하 여
MSBuild를 잘 정의 된 확장 가능한 XML 형식 완벽 하 게 빌드할 수, 작업, 빌드 및 빌드 구성 프로젝트 항목을 설명 하는 프로젝트 파일을 만들기 위한를 제공 합니다.  
  
## <a name="general-msbuild-considerations"></a>일반적인 MSBuild 고려 사항  
 MSBuild 프로젝트 파일, 예를 들어 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] .csproj 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] .vbproj 파일 데이터가 있는 빌드 시 사용 하지만 또한 디자인 타임에 사용 되는 데이터를 포함할 수 있습니다. 빌드 시간 데이터는 포함 하 여 MSBuild 기본 형식을 사용 하 여 저장 [Item 요소 (MSBuild)](../../msbuild/item-element-msbuild.md) 및 [Property 요소 (MSBuild)](../../msbuild/property-element-msbuild.md)합니다. 프로젝트 형식 및 모든 관련된 프로젝트 하위 형식에 특정 한 데이터는 디자인 타임 데이터를 예약 하는 자유 형식의 XML에 저장 됩니다.  
  
 MSBuild는 구성 개체에 대 한 기본 지원을 없지만에서는 구성 관련 데이터를 지정에 대해 조건부 특성을 제공 합니다. 예:  
  
```xml  
<OutputDir Condition="'$(Configuration)'=="release'">Bin\MyReleaseConfig</OutputDir>  
```  
  
 조건부 특성에 대 한 자세한 내용은 참조 하십시오. [조건부 생성](../../msbuild/msbuild-conditional-constructs.md)합니다.  
  
### <a name="extending-msbuild-for-your-project-type"></a>MSBuild 프로젝트 형식에 대 한 확장  
 MSBuild 인터페이스와 Api의 이후 버전에서 변경 될 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 따라서는 변경 된 내용에서 보호를 제공 하기 때문에 관리 되는 패키지 프레임 워크 (MPF) 클래스를 사용 하는 것이 좋습니다.  
  
 프로젝트 (MPFProj)에 대 한 관리 되는 패키지 프레임 워크는 만들고 새 프로젝트 시스템을 관리 하기 위한 도우미 클래스를 제공 합니다. 코드 및 컴파일 지침에는 소스를 찾을 수 [프로젝트-Visual Studio 2013에 대 한 MPF](http://mpfproj12.codeplex.com/)합니다.  
  
 프로젝트 관련 MPF 클래스는 다음과 같습니다.  
  
|클래스|구현|  
|-----------|--------------------|  
|`Microsoft.VisualStudio.Package.ProjectNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents>|  
|`Microsoft.VisualStudio.Package.ProjectFactory`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|  
|`Microsoft.VisualStudio.Package.HierarchyNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|  
|`Microsoft.VisualStudio.Package.ProjectConfig`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|  
|`Microsoft.VisualStudio.Package.SettingsPage`|<xref:Microsoft.VisualStudio.OLE.Interop.IPropertyPageSite>|  
  
 `Microsoft.VisualStudio.Package.ProjectElement`클래스는 MSBuild 항목에 대 한 래퍼입니다.  
  
#### <a name="single-file-generators-vs-msbuild-tasks"></a>단일 파일 생성기 vs입니다. MSBuild 작업  
 단일 파일 생성기는 디자인 타임에만, 액세스할 수 있지만 빌드 시간 및 디자인 타임에 MSBuild 작업을 사용할 수 있습니다. 유연성을 극대화 변형 하는 코드를 생성 합니다. 따라서 MSBuild 작업을 사용 합니다. 자세한 내용은 참조 [사용자 지정 도구](../../extensibility/internals/custom-tools.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild 참조](../../msbuild/msbuild-reference.md)   
 [MSBuild](../../msbuild/msbuild.md)   
 [사용자 지정 도구](../../extensibility/internals/custom-tools.md)