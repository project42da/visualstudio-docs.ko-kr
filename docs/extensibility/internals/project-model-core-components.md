---
title: "모델의 핵심 구성 요소 프로젝트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project models, objects and interfaces
- project models, services
ms.assetid: b2f572d3-b26d-4846-92d1-84055fac141a
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c7759a2394f2cda19f875a85a22c4a674fee8964
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="project-model-core-components"></a>프로젝트 모델에 대 한 핵심 구성 요소
다음 표에서 프로젝트 모델에서 확장 됩니다. 테이블에는 인터페이스 및 모델, 인터페이스 및 특정 개체와 연결 된 서비스에서 식별 된 서비스에 대 한 간략 한 설명이 제공 합니다. 또한 테이블에는 다른 인터페이스는 프로젝트 생성 및 특정 프로젝트 형식이 요구 사항에 따라 유지 관리에서 선택적 요소를 자세히 설명 합니다.  
  
 자세한 내용은 참조 [기호를 지 원하는 검색 도구](../../extensibility/internals/supporting-symbol-browsing-tools.md)합니다.  
  
### <a name="package-object"></a>패키지 개체  
  
|인터페이스|설명|  
|---------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>|IDE에서 VSPackage를 초기화 하 고 IDE를 해당 서비스를 사용할 수 있게 합니다.|  
  
### <a name="project-factory-object"></a>프로젝트 팩터리 개체  
  
|인터페이스|설명|  
|---------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|새 프로젝트를 만들고 기존 프로젝트를 열기를 관리 합니다.|  
  
### <a name="project-objects"></a>프로젝트 개체  
  
|인터페이스|설명|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>|추가 및 제거 프로젝트 항목의 관리 편집기를 열고 각 문서 모니커 사이의 매핑을 유지 관리 및 `VSITEMID`합니다. 상속 `IVsProject` 및 `IVsProject2`합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|탐색 및 표시 속성을 관리 하 고 이벤트를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>|사용 하도록 설정 명령 실행의 것과 비슷한 `IOleCommandTarget` 포커스가 솔루션 탐색기에서 있을 경우에 적용 되는 잘라내기 / 이름 바꾸기와 같은 명령에 대 한 합니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|프로젝트 계층 구조에 대 한 기본 명령 대상 인터페이스로 사용합니다. 해당 명령 상태 또는 상태와 실행 명령에 대 한 개체를 쿼리 하기 위한 표준 인터페이스입니다. 하지 프로젝트 창에서 포커스를 둘 때 사용할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|프로젝트 상태 지 속성을 조정합니다. 일반적으로 프로젝트 상태 프로젝트 파일로 저장 되어 있지만 파일 기반이 아닌 저장소 시스템에 적용할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2>|디스크 또는 다른 저장소 시스템의 개체에서 파일로 하거나 해당 프로젝트 항목에 대 한 지 속성의 모든 측면을 관리 하는 프로젝트 수 있습니다. `IVsPeristHierarchyItem2` 인터페이스 구현 하지 않는 항목에 사용 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|소스 코드 제어와의 상호 작용을 조정합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfgProvider>|프로젝트를 구성 정보를 관리할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>|디버그/릴리스 구성 등의 프로젝트 구성 개체를 관리합니다. 빌드, 배포 및 디버깅 작업은 프로젝트 구성 개체를 통해 조정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDeleteHandler>|계층 삭제 (파괴적)를 제어 하거나 계층 항목에 대 한 (비파괴) 옵션이 제거을 구현 합니다. 쿼리 인터페이스에서 호출 하는 `IVsHierarchyDeleteHandler` 에서 인터페이스는 `IVsHierarchy` 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsGetCfgProvider>|구현 하도록 지 원하는 개체를 제공는 `IVsCfgProvider2` 인터페이스를 구현 하는 프로젝트 개체와 다른 COM id에는 `IVsHierarchy` 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectStartupServices>|다른 개발자가 프로젝트를 확장할 수 있도록 하기 위해 구현 하는 선택적 인터페이스입니다. `IVsProjectStartupServices` 인터페이스를 사용 하면 프로젝트 파일 및 호출 제 3 자 서비스 GUID를 로드 하는 프로젝트가 로드 될 때마다 않도록 프로젝트 파일에 유지 하는 GUID를 등록 하기 위해 제 3 자 VSPackage `QueryService` 이 GUID에 대 한 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierWinClipboardHelperEvents>|원본 계층에서 구현한는 `UIHierarchy` 잘라내기, 복사 등의 클립보드 작업을 조정 하 여 붙여 넣는 창. 사용 하 여 `AdviseClipboardHelperEvents` 클립보드 이벤트를 등록 하는 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDropDataSource2>|UI 계층 구조 창에서 끌어서 놓기 작업 동안 해당 데이터 원본 기준으로 끌어 온된 항목에 대 한 정보를 제공합니다. 호출 된 `IVsHierarchy` 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDropDataTarget>|UI 계층 구조 창에서 끌어서 놓기 작업 동안 기준 놓기 대상으로 끌어 온된 항목에 대 한 정보를 제공합니다. 호출 된 `IVsHierarchy` 인터페이스입니다.|  
  
### <a name="configuration-object"></a>구성 개체  
  
|인터페이스|설명|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg>|구성에 대 한 정보를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2>|프로젝트를 구성 정보를 관리할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|디버거에서 제어할에서 실행 되도록 프로젝트를 사용 하도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg>|다른 프로젝트에 대 한 배포 작업을 수행 하는 배포 프로젝트에 의해 구현 됩니다.|  
  
### <a name="configuration-builder-object"></a>구성 작성기 개체  
  
|인터페이스|설명|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg>|프로젝트 구성의 빌드 작업을 관리 합니다.|  
  
### <a name="additional-project-objects"></a>추가 프로젝트 개체  
  
|인터페이스|설명|  
|----------------|--------------|  
|`IDispatch`<br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.ISpecifyPropertyPages>|표시 항목 속성에는 **속성** 창.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs>|배포에 대 한 출력을 표시합니다.|  
  
 다음 표에 나와 프로젝트 모델에서 식별 된 서비스에 간략하게 설명 합니다.  
  
### <a name="services"></a>서비스  
  
|서비스|설명|  
|-------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterProjectTypes>|해당 프로젝트 팩터리와 IDE 있는지 등록 하려면 프로젝트 형식을 구현 하는 Vspackage에서 사용 합니다. VSPackage를 호출 해야 `QueryService` 이 서비스 및 해당 프로젝트 팩터리를 등록할 때 `IVsPackage::SetSite` 메서드를 호출 합니다. 경우는 `SetSite` 프로젝트는 인스턴스화되지, 메서드가 호출 되지 않습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|현재 솔루션의 프로젝트를 열거할 새 프로젝트를 만들고 프로젝트 변경 사항에 유의 하 고 등 하는 등의 IDE의 내부, 기본 제공 개념에 대 한 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>|소스 제어에 참가 하려면 프로젝트에서 호출 됩니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>|프로젝트 항목 중 하나 이상이 이미 열려 있는지 여부를 확인 하려면 열려 있는 문서의 테이블 유지 관리 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellOpenDocument>|인터페이스와 표준 편집기 또는 특정 편집기를 사용 하 여 프로젝트 항목을 열려면 실제로 호출 메서드를 포함 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>|추가, 제거 하거나 해당 항목의 이름을 바꿀 때 모든 프로젝트에서 호출 하는 데 필요 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx>|선택한 파일이 디스크에서 변경 된 경우 클라이언트에 알리는 및 변경 내용이 파일 또는 디렉터리를 관리 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>|항목을 변경 하거나 저장 하기 전에 모든 프로젝트와 편집기에서 호출할 수 하는 데 필요 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionBuildManager>|프로젝트 구성에 대 한 빌드 및 배포 작업 순서를 관리합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellDebugger>|대부분의 디버깅 컨트롤에 사용 되는 하위 수준 디버거 서비스에 대 한 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>|현재 선택 항목에 대 한 정보를 Vspackage 액세스할 수 있도록 하 고 통신할 수 있습니다는 **속성** 창.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|만들고 열거 도구 창 또는 문서 창 또는 사용자에 게 오류를 보고 하는 기능과 같은 기본 UI와 관련 된 IDE 기능을 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar>|IDE의 상태 표시줄에 대 한 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibility3>|자동화 모델을 구현 하는 데 사용 합니다. 프로젝트 모델에서 반환 됩니다 수 있는 속성 개체를 해당 개체의 인스턴스를 만듭니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIHierWinClipboardHelper>|프로젝트 개체 계층 구조에서 클립보드 이벤트를 구현 하는 데 사용 합니다. `SVsUIHierWinClipboardHelper`하면 올바르게 핸들 잘라내기, 복사 및 붙여넣기 작업.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [빌드에 없음: HierUtil7 프로젝트 클래스를 사용 하 여 프로젝트 형식 (c + +)를 구현 하려면](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346)   
 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [프로젝트 모델의 요소](../../extensibility/internals/elements-of-a-project-model.md)