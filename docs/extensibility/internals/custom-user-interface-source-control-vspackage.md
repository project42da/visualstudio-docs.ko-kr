---
title: "사용자 지정 사용자 인터페이스 (소스 제어 VSPackage) | Microsoft Docs"
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
  - "사용자 인터페이스, 소스 제어 패키지"
  - "소스 제어 패키지, 사용자 인터페이스"
ms.assetid: f35ddb24-53bf-461e-b34f-7414f657c082
caps.latest.revision: 28
caps.handback.revision: 28
ms.author: "gregvanl"
manager: "ghogen"
---
# 사용자 지정 사용자 인터페이스 (소스 제어 VSPackage)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

있는 VSPackage 명령 테이블 \(.vsct\) Visual Studio 파일을 통해 해당 메뉴 항목 및 해당 기본 상태를 선언합니다.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)은 VSPackage 로드 될 때까지 기본값 상태에서 메뉴 항목을 표시 합니다.  그 후에 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드가 호출 메뉴 항목을 사용할지 여부.  
  
 있는 VSPackage 있는 Vspackage를 명령 사용자 인터페이스 \(UI\) 상황에 따라 자동으로 로드할 수 있도록 레지스트리 키를 설정할 수 있습니다, 그리고 일반적으로 소스 제어에 있지만 단지 특정 UI 컨텍스트를 전환 하는 대신 필요할 때 VSPackage 로드 해야 합니다.  AutoLoadPackages 레지스트리 키에 대 한 자세한 내용은 참조 하십시오. [Vspackage를 관리합니다.](../../extensibility/managing-vspackages.md).  
  
## VSPackage UI  
 소스 제어 패키지는 Vspackage로 구현 되 고 UI에서 사용 하지 않는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  각 소스 제어 VSPackage 옵션 VSPackage 소스 제어 하려면 특정 설정 하는 필요한 UI, 도구 창, 메뉴 항목, 도구 모음 및 메뉴 그룹 같은 UI 요소를 지정 해야 합니다.  이 UI 요소는 정적 또는 동적으로 사용할 수 있습니다.  정적 UI 요소는.vsct 파일에 정의 된 및 있는 VSPackage 로드 되어 있는지 여부를 표시 합니다.  동적 UI 요소가 있을 수는 특정 명령 UI 상황에 따라 표시 등 <xref:EnvDTE.Constants.vsContextNoSolution>, 또는에 대 한 호출의 결과로 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드.  동적 UI 요소의 표시 여부 Vspackages의 지연된 로드에 대 한 전략을 준수합니다.  
  
## 소스 제어 Vspackages에 UI 제약 조건  
 소스 제어 VSPackage 로드 된 후 IDE에서 제거할 수 없습니다 때문에 있는 VSPackage 비활성 상태로 들어갈 수 있어야 합니다.  알림을 더 이상 활성화 되어 있음을 Vspackage를 받으면 있는 VSPackage UI를 사용 하지 않도록 설정 하 고 외부 IDE의 개입을 무시 합니다.  Vspackage의 구현에 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> Vspackage를 사용 하지 않으면 명령을 숨기 해야 합니다.  
  
 모든 소스 제어 VSPackage 구현 해야 하는 `IVsSccProvider` 인터페이스입니다.  두 메서드는 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetActive%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetInactive%2A>, Vspackage에서 구현 해야 합니다.  
  
 Vspackage로 구현 되어 다양 한 IDE 이벤트 구독 있을 수 있습니다 원본 컨트롤의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>등.  또한 있는 VSPackage 레지스트리 설정 콜백 인터페이스 같은 구현 될 수 있습니다 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>.  이러한 모든 비활성 상태일 때 무시 해야 합니다.  
  
 다음은 VSPackage 원본 컨트롤의 현재 상태에 영향을 받는 인터페이스입니다.  
  
-   프로젝트 문서 이벤트를 추적 합니다.  
  
-   솔루션 이벤트입니다.  
  
-   지 속성 인터페이스 솔루션입니다.  비활성 상태일 때 패키지.sln과.suo 파일에 기록할 수 없습니다.  
  
-   Extender가 속성입니다.  
  
 필수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>를 하 고 또한 소스 제어와 연결 된 선택적 인터페이스 호출 되지 않습니다 VSPackage 소스 제어를 사용 하지 않으면 됩니다.  
  
 경우는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 시작 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackage id가 현재 기본 원본 컨트롤의 ID를 설정 하는 명령 UI 컨텍스트  이 정적 UI 활성 소스 제어 VSPackage 실제로 있는 Vspackage를 로드 하지 않고 IDE에 표시 됩니다.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]등록할 Vspackage를 일시 중지 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통해에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider> 에 있는 VSPackage 호출 하기 전에.  
  
 다음 표에서 특정 세부 정보에 대 한 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 다른 UI 항목을 숨깁니다.  
  
|UI 항목|설명|  
|-----------|--------|  
|메뉴 및 도구 모음|소스 제어 패키지 초기 메뉴 및 도구 모음 표시 상태에서 소스 제어 패키지 ID를 설정 합니다는  [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md) .vsct 파일의 섹션입니다.  이렇게는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE는 VSPackage 로드 하 고 구현 하는 호출 하지 않고 메뉴 항목의 상태를 적절 하 게 설정 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드.|  
|도구 창|소스 제어 VSPackage 비활성화 될 때 소유 하 고 모든 도구 창을 숨깁니다.|  
|소스 제어 VSPackage 특정 페이지 옵션|HKLM\\SOFTWARE\\Microsoft\\VisualStudio\\X.Y\\ToolsOptionsPages\\VisibilityCmdUIContexts 레지스트리 키에 있는 Vspackage를 나타나는 해당 옵션 페이지를 요구 하는 컨텍스트를 설정할 수 있습니다.  이 키 아래에 레지스트리 항목은 DWORD 값 1 할당 및 서비스 식별자 \(SID\)의 소스 제어 서비스를 사용 하 여 만들 수 할 것입니다.  UI 이벤트 VSPackage 등록 되어 있는 소스 제어의 컨텍스트에서 발생할 때마다 있는 VSPackage 활성화 된 경우 호출 됩니다.|  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider>   
 <xref:EnvDTE.Constants.vsContextNoSolution>   
 [Vspackage를 관리합니다.](../../extensibility/managing-vspackages.md)