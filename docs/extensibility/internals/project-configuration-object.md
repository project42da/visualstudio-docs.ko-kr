---
title: "프로젝트 구성 개체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 구성, 개체"
  - "개체를 프로젝트 구성"
ms.assetid: 877756c9-4261-43d9-9f32-51bf06b4219f
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 프로젝트 구성 개체
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 구성 개체 관리를 UI에 구성 정보를 표시 합니다.  
  
 ![Visual Studio 프로젝트 구성](~/docs/extensibility/internals/media/vsprojectcfg.gif "vsProjectCfg")  
프로젝트 구성 속성 페이지  
  
 프로젝트 구성 공급자 프로젝트 구성을 관리합니다. 환경 및 다른 패키지를 프로젝트의 구성에 대 한 정보를 검색, 프로젝트 구성 공급자 개체에 연결 된 인터페이스를 호출 하 고에 대 한 액세스 권한을 얻으려고 합니다.  
  
> [!NOTE]
>  솔루션 구성 파일을 프로그래밍 방식으로 편집 하거나 만들 수 없습니다. 사용 해야 `DTE.SolutionBuilder`합니다. 자세한 내용은 [솔루션 구성](../../extensibility/internals/solution-configuration.md)를 참조하세요.  
  
 UI 구성에 사용할 표시 이름에 게시 하려면 프로젝트를 구현 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg.get_DisplayName%2A>합니다. 환경 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgs%2A>, 목록을 반환 하는 `IVsCfg` 환경 UI에 나열 될 구성 및 플랫폼 정보에 대 한 표시 이름을 가져오는 데 사용할 수 있는 포인터입니다. 활성 구성 및 플랫폼 활성 솔루션 구성에 저장 된 프로젝트의 구성에 의해 결정 됩니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager.FindActiveProjectCfg%2A> 메서드를 사용 하 여 활성 프로젝트 구성을 검색할 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfgProvider> 에서 필요에 따라 개체를 구현할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2> 개체는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProviderEventsHelper> 개체를 검색할 수 있도록는 `IVsProjectCfg2` 정식 프로젝트 구성 이름에 따라 개체입니다.  
  
 구현을 제공 하는 프로젝트에 대 한 프로젝트 구성에 액세스할 수 있는 환경 및 다른 프로젝트를 제공 하는 다른 방법은 되는 `IVsCfgProvider2::GetCfgs` 메서드를 하나 이상의 구성 개체를 반환 합니다. 프로젝트 구현할 수도 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2>, 에서 상속 된 `IVsProjectCfg` 함으로써에서 `IVsCfg`, 구성 관련 정보를 제공 합니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2> 추가, 삭제 및 프로젝트 구성 이름 바꾸기에 대 한 플랫폼 및 기능을 지원 합니다.  
  
> [!NOTE]
>  Visual Studio를 더 이상 없는 두 개의 구성 유형으로 제한 되므로 구성을 처리 하는 코드 작성 하지 않아야 가정을와 구성, 수에 대 한도 그 쓸지 구성이 하나만 포함 된 프로젝트를 반드시은 가정 하에 디버그 또는 소매. 이렇게 하면 사용 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg.get_IsReleaseOnly%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg.get_IsDebugOnly%2A> 사용 되지 않습니다.  
  
 호출 `QueryInterface` 에서 반환 된 개체에`IVsGetCfgProvider::GetCfgProvider` 검색 `IVsCfgProvider2`합니다. 경우 `IVsGetCfgProvider` 를 호출 하 여 없는 `QueryInterface` 에 `IVsProject3` 프로젝트 개체를 호출 하 여 구성 공급자 개체를 액세스할 수 있습니다 `QueryInterface` 계층 루트 브라우저 개체에 대해 반환 되는 개체에 대 한 `IVsHierarchy::GetProperty(VSITEM_ROOT, VSHPROPID_BrowseObject)`, 또는 포인터에 대해 반환 되는 구성 공급자를 통해 `IVsHierarchy::GetProperty(VSITEM_ROOT, VSHPROPID_ConfigurationProvider)`합니다.  
  
 `IVsProjectCfg2` 주로 통해 빌드, 디버그 및 배포 관리 개체 및 프로젝트 그룹 출력 수 있습니다. 메서드 `IVsProjectCfg` 및 `IVsProjectCfg2` 구현 하는 데 사용 될 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg> 빌드 프로세스를 관리 하 고 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputGroup> 구성의 출력 그룹에 대 한 포인터입니다.  
  
 프로젝트 구성에서 구성 다를 수 있습니다 그룹 내에 포함 된 출력 수 있지만 지원 되는 각 구성에 대 한 그룹의 동일한 수를 반환 해야 합니다. 그룹 있어야 동일한 식별자 정보 \(정식 이름, 표시 이름 및 그룹 정보\) 구성에서 구성 프로젝트 내에서 합니다. 자세한 내용은 [출력에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md)을 참조하세요.  
  
 디버깅을 사용 하 여 구성을 구현 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>합니다.`IVsDebuggableProjectCfg` 디버거에서 구성을 시작할 수 있도록 하는 프로젝트에 의해 구현 되는 선택적 인터페이스 이며 포함 된 구성 개체에서 구현 되는 `IVsCfg` 및 `IVsProjectCfg`합니다. 환경 f5 키를 눌러 디버거를 시작 하 여 사용자가 하는 경우 호출 합니다.  
  
 `ISpecifyPropertyPages` 및 `IDispatch` 속성 페이지와 함께에서 검색 하 고 사용자에 게 구성에 종속 된 정보를 표시 하는 데 사용 됩니다. 자세한 내용은 [속성 페이지](../../extensibility/internals/property-pages.md)을 참조하세요.  
  
## 참고 항목  
 [구성 옵션 관리](../../extensibility/internals/managing-configuration-options.md)   
 [빌드를 위한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)   
 [출력에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md)   
 [속성 페이지](../../extensibility/internals/property-pages.md)   
 [솔루션 구성](../../extensibility/internals/solution-configuration.md)