---
title: "MSBuild를 사용 하 여 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage를 MSBuild로 컴파일"
  - "MSBuild를 확장성"
  - "패키지, MSBuild로 컴파일"
ms.assetid: 9d38c388-1f64-430e-8f6c-e88bc99a4260
caps.latest.revision: 20
caps.handback.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
---
# MSBuild를 사용 하 여
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

MSBuild를 완벽 하 게 빌드할 수, 작업, 빌드 및 빌드 구성에 대 한 프로젝트 항목을 설명 하는 프로젝트 파일을 만들기 위한 잘 정의 되 고 확장 가능한 XML 형식을 제공 합니다.  
  
 MSBuild 기반 언어 프로젝트 시스템의 종단 간 예제를 참조에서 IronPython 샘플 심층 분석은[VSSDK 샘플](../../misc/vssdk-samples.md)합니다.  
  
## 일반 MSBuild 고려 사항  
 MSBuild 프로젝트 파일, 예를 들어 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] .csproj 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] .vbproj 파일을 빌드할 때 사용 되지만 또한 디자인 타임에 사용 되는 데이터를 포함할 수 데이터를 포함 합니다. 빌드 시간 데이터는 포함 하는 MSBuild 기본 형식을 사용 하 여 저장 [Item Element \(MSBuild\)](../../msbuild/item-element-msbuild.md) 및 [Property Element \(MSBuild\)](../../msbuild/property-element-msbuild.md)합니다. 프로젝트 형식 및 모든 관련된 프로젝트 하위 형식에 관련 된 데이터는 디자인 타임 데이터를 예약 하는 자유 형식 XML에 저장 됩니다.  
  
 MSBuild는 구성 개체에 대 한 기본 지원을 없지만 구성 관련 데이터를 지정 하는 것에 대 한 조건부 특성이 제공지 않습니다. 예:  
  
```  
<OutputDir Condition="'$(Configuration)'=="release'">Bin\MyReleaseConfig</OutputDir>  
```  
  
 조건부 특성에 대 한 자세한 내용은 참조 하십시오. [Conditional Constructs](../../msbuild/msbuild-conditional-constructs.md)합니다.  
  
### MSBuild 프로젝트 형식에 대 한 확장  
 MSBuild 인터페이스 및 Api의 이후 버전에서 변경 사항이 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 따라서이 변경 내용에서 차폐를 제공 하기 때문에 관리 되는 패키지 \(MPF\) 프레임 워크 클래스를 사용 하는 것이 좋습니다.  
  
 프로젝트 \(MPFProj\)에 대 한 관리 되는 패키지 프레임 워크는 만들고 새로운 프로젝트 시스템을 관리 하기 위한 도우미 클래스를 제공 합니다. 소스 코드와 컴파일 지침을 찾을 수 있습니다 [프로젝트\-Visual Studio 2013에 대 한 MPF](http://mpfproj12.codeplex.com/)합니다.  
  
 프로젝트 관련 MPF 클래스는 다음과 같습니다.  
  
|클래스|구현|  
|---------|--------|  
|`Microsoft.VisualStudio.Package.ProjectNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents>|  
|`Microsoft.VisualStudio.Package.ProjectFactory`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|  
|`Microsoft.VisualStudio.Package.HierarchyNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|  
|`Microsoft.VisualStudio.Package.ProjectConfig`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|  
|`Microsoft.VisualStudio.Package.SettingsPage`|<xref:Microsoft.VisualStudio.OLE.Interop.IPropertyPageSite>|  
  
 `Microsoft.VisualStudio.Package.ProjectElement` 클래스는 MSBuild 항목에 대 한 래퍼입니다.  
  
#### 단일 파일 생성기 vs입니다. MSBuild 작업  
 단일 파일 생성기가 디자인 타임에만, 액세스할 수 있지만 디자인 타임 및 빌드 타임에 MSBuild 작업을 사용할 수 있습니다. 유연성을 극대화 따라서 사용 하 여 MSBuild 작업을 변환 하 여 코드를 생성 합니다. 자세한 내용은 [사용자 지정 도구](../../extensibility/internals/custom-tools.md)을 참조하세요.  
  
## 참고 항목  
 [MSBuild Reference](../../msbuild/msbuild-reference.md)   
 [MSBuild](http://msdn.microsoft.com/ko-kr/7c49aba1-ee6c-47d8-9de1-6f29a906e20b)   
 [사용자 지정 도구](../../extensibility/internals/custom-tools.md)