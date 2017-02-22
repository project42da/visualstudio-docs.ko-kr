---
title: "프로젝트 모델에 대 한 핵심 구성 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 모델, 개체 및 인터페이스"
  - "서비스 프로젝트 모델"
ms.assetid: b2f572d3-b26d-4846-92d1-84055fac141a
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 모델에 대 한 핵심 구성 요소
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 모델에서 다음 테이블을 확장합니다.  테이블 인터페이스와 모델, 인터페이스 및 특정 개체와 연결 된 서비스에서 확인 서비스에 대 한 간단한 설명을 제공 합니다.  또한 테이블에 프로젝트 작성 및 유지 관리 요구 사항 특정 프로젝트 형식에 따라 선택적 인터페이스를 자세히 설명 합니다.  
  
 자세한 내용은 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)를 참조하십시오.  
  
### 패키지 개체  
  
|Interface|설명|  
|---------------|--------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>|IDE에 있는 Vspackage를 초기화 하 고 IDE로 해당 서비스를 사용할 수 있습니다.|  
  
### 프로젝트 공장 개체  
  
|Interface|설명|  
|---------------|--------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|새 프로젝트를 만들고 기존 프로젝트를 열어 관리 합니다.|  
  
### 프로젝트 개체  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>|추가 및 프로젝트 항목의 제거를 관리, 편집기를 열고 각 문서 모니커 간의 매핑을 유지 관리 하는 `VSITEMID`.  상속 `IVsProject` 및 `IVsProject2`.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|탐색 및 표시 속성을 관리 하 고 이벤트를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>|명령 실행에 비슷한 수 있습니다 `IOleCommandTarget` 에 솔루션 탐색기에 포커스가 있는 적용 명령을 잘라내기 및 이름 바꾸기와 같은.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|프로젝트 계층 구조에 대 한 기본 명령 대상 인터페이스 역할을 합니다.  이 개체의 상태 및 실행 중인 명령 또는 명령 상태를 쿼리 하는 것에 대 한 표준 인터페이스입니다.  프로젝트 창에서 중점적으로 경우에이 옵션을 사용할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|프로젝트 상태 지 속성을 조정합니다.  일반적으로 프로젝트 상태 프로젝트 파일로 저장 되지만 파일 기반이 아닌 저장소 시스템에 적용할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2>|프로젝트를 지 속성으로 파일을 디스크 또는 다른 저장소 시스템에서 개체를 해당 프로젝트 항목에 대 한 모든 측면을 관리할 수 있습니다.  `IVsPeristHierarchyItem2` 인터페이스를 구현 하지 않는 항목에 대 한 사용 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> 인터페이스.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|소스 코드 제어와 상호 작용을 조정합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfgProvider>|프로젝트를 구성 정보를 관리할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>|디버그\/릴리스 구성 프로젝트 구성 개체를 관리합니다.  빌드, 배포 및 디버깅 작업 프로젝트 구성 개체를 통해 조정 됩니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDeleteHandler>|계층 계층 구조 항목에 대 한 항목 id \(비 소거식\) delete \(삭제\)를 구현 합니다.  쿼리 인터페이스를 호출을 `IVsHierarchyDeleteHandler` 에서 인터페이스는 `IVsHierarchy` 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsGetCfgProvider>|구현 옵션을 지 원하는 개체를 제공의 `IVsCfgProvider2` 인터페이스를 구현 하는 프로젝트 개체 보다 다른 COM id는 `IVsHierarchy` 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectStartupServices>|다른 개발자가 프로젝트를 확장할 수 있도록 구현 하는 선택적 인터페이스입니다.  `IVsProjectStartupServices` 인터페이스는 타사 VSPackage 프로젝트 로드 될 때마다 타사 서비스 GUID에서 프로젝트 파일 및 호출에 로드할 수 있도록 프로젝트 파일에 유지 하는 GUID를 등록할 수 있습니다 `QueryService` 에 대 한 GUID.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierWinClipboardHelperEvents>|원본 계층 구조에 의해 구현 된 `UIHierarchy` 예: 잘라내기, 복사, 클립보드 작업을 조정 하 여 붙여넣기 창.  사용은 `AdviseClipboardHelperEvents` 인터페이스 클립보드 이벤트를 등록 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDropDataSource2>|UI 계층 구조 창에서 끌어서 놓기 작업 동안 끌어 온된 항목을 기준으로 해당 데이터 소스에 대 한 정보를 제공합니다.  호출을 `IVsHierarchy` 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDropDataTarget>|UI 계층 구조 창에서 끌어서 놓기 작업 도중 해당 놓기 대상 기준으로 끌어 온된 항목에 대 한 정보를 제공합니다.  호출을 `IVsHierarchy` 인터페이스입니다.|  
  
### 구성 개체  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg>|구성에 대 한 정보를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2>|프로젝트를 구성 정보를 관리할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|디버거의 제어 하에서 실행 해야 하는 프로젝트를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg>|다른 프로젝트에 대 한 배포 작업을 수행 하는 배포 프로젝트에 의해 구현 됩니다.|  
  
### 구성 작성기 개체입니다.  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg>|프로젝트 구성은 빌드 작업을 관리합니다.|  
  
### 프로젝트의 다른 개체  
  
|인터페이스|설명|  
|-----------|--------|  
|`IDispatch`<br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.ISpecifyPropertyPages>|표시 항목의 속성은  **속성** 창.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs>|배포에 대 한 출력을 표시합니다.|  
  
 다음 표에서 프로젝트 모델에서 식별 되는 서비스에 대 한 간단한 설명을 제공 합니다.  
  
### 서비스  
  
|서비스|설명|  
|---------|--------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterProjectTypes>|프로젝트 공장 IDE와 있는지, 등록 하는 프로젝트 형식은 구현 Vspackages가 사용 됩니다.  Vspackage를 호출 해야 `QueryService` 이 대 한 서비스 및 해당 프로젝트 공장 등록 때 `IVsPackage::SetSite` 메서드가 호출 됩니다.  경우는 `SetSite` 메서드가 호출 되 고 프로젝트를 인스턴스화할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|현재 솔루션에 프로젝트를 열거, 새로운 프로젝트를 만들고, 프로젝트에 변경 알림을 수행 하는 등의 IDE의 내부, 기본 개념에 대 한 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>|소스 제어에 참여 하고자 하는 프로젝트에서 호출 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>|프로젝트 항목 중 하나 이상이 이미 열려 있는지 여부를 확인 하려면 열려 있는 문서를 테이블을 유지 관리 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellOpenDocument>|실제로 특정 편집기 또는 표준 편집기를 사용 하 여 프로젝트 항목을 여는 호출 메서드와 인터페이스가 들어 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>|추가, 제거 하거나 해당 항목의 이름을 변경 하면 모든 프로젝트에서 호출 하는 데 필요한.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx>|파일 또는 디렉터리에 대 한 변경 내용을 관리 하 고 선택한 파일이 디스크에서 변경 된 경우 클라이언트에 게 알립니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>|이러한 항목을 변경 하거나 저장 하기 전에 호출 되는 모든 프로젝트와 편집기입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionBuildManager>|프로젝트 구성에 대 한 빌드 및 배포 작업의 순서를 관리합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellDebugger>|대부분의 디버깅 컨트롤에 사용 되는 하위 수준의 디버거 서비스 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>|VSPackages 액세스 현재 선택 항목에 대 한 정보를 사용 하 고 통신할 수 있도록 해당  **속성** 창입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|기본 UI와 관련 된 IDE 기능을 만들어 windows 도구 또는 문서 창 열거 하거나 사용자에 게 오류를 보고 하는 기능 등을 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar>|IDE의 상태 표시줄에 대 한 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibility3>|자동화 모델을 구현 하는 데 사용 됩니다.  프로젝트 모델에서 반환 됩니다 수 있도록 하는 속성 개체 개체의 인스턴스를 만듭니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIHierWinClipboardHelper>|프로젝트 계층 구조에서 개체를 클립보드 이벤트를 구현 했습니다.  `SVsUIHierWinClipboardHelper`올바르게 핸들 잘라내기, 복사 및 붙여넣기 작업 수 있습니다.|  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Not in Build: Using HierUtil7 Project Classes to Implement a Project Type \(C\+\+\)](http://msdn.microsoft.com/ko-kr/a5c16a09-94a2-46ef-87b5-35b815e2f346)   
 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [프로젝트 모델의 요소](../../extensibility/internals/elements-of-a-project-model.md)