---
title: "명령을 사용 가능 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "메뉴 [Visual Studio SDK] 명령"
  - "모범 사례, 메뉴 및 도구 모음 명령"
  - "도구 모음 [Visual Studio] 모범 사례"
  - "메뉴 명령, 모범 사례"
ms.assetid: 3ffc4312-c6db-4759-a946-a4bb85f4a17a
caps.latest.revision: 35
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 35
---
# 명령을 사용 가능
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

여러 Vspackage Visual Studio에 추가 되 면 하는 경우 사용자 인터페이스 \(UI\) 명령을 사용 하 여 들어오지 될 수 있습니다. 이 문제를 다음과 같이 줄일 수 있도록 패키지를 프로그래밍할 수 있습니다.  
  
-   패키지 프로그램 사용자 경우에 로드 되도록 필요한 합니다.  
  
-   패키지를 프로그래밍 하는 통합된 개발 환경 \(IDE\)의 현재 상태의 컨텍스트에서 해야 할 수 있습니다 하는 경우에 해당 명령이 표시 됩니다.  
  
## 지연 로드  
 사용 하도록 설정 하는 일반적인 방법을 않도록 해당 명령이 UI에 표시 됩니다. 그러나 사용자가 명령 중 하나를 클릭할 때까지 패키지 자체 로드 되지는 VSPackage를 디자인 하는 지연 로드. 이를 위해,.vsct 파일에 없는 명령 플래그를 있는 명령을 만듭니다.  
  
 다음 예제에서는.vsct 파일에서 메뉴 명령 정의 보여 줍니다. 이것은 Visual Studio 패키지 템플릿에서 생성 되는 명령 때는 **메뉴 명령** 서식 파일에 대 한 옵션을 선택 합니다.  
  
 [!CODE [TopLevelMenu#03](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#03)]  
  
 예제에서는 하는 경우 부모 그룹 `MyMenuGroup`, 의 자식인 최상위 메뉴와 같은 **도구** 메뉴 명령이 해당 메뉴에 표시 됩니다. 하지만 사용자가 명령을 클릭할 때까지 명령을 실행 하는 패키지를 로드 하지 것입니다. 그러나 프로그래밍을 구현 하는 명령으로는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스를 패키지 명령이 포함 된 메뉴를 처음으로 확장 하는 경우 로드를 사용할 수 있습니다.  
  
 확인 지연된 로드 시작 시 성능이 향상 될 수 있습니다.  
  
## 현재 컨텍스트 및 명령 표시  
 VSPackage 명령을 표시 하거나 숨기도록 VSPackage 데이터 또는 현재와 관련 된 작업의 현재 상태에 따라 프로그래밍할 수 있습니다. 구현을 사용 하 여 일반적으로 해당 명령의 상태를 설정 하려면 VSPackage를 사용 하도록 설정할 수는 <xref:EnvDTE.IDTCommandTarget.QueryStatus%2A> 메서드에서 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스, 하지만이 코드를 실행 하기 전에 로드할 VSPackage 필요 합니다. 대신, 패키지를 로드 하지 않고 명령의 표시 유형을 관리 하는 IDE를 사용 하는 것이 좋습니다. 이렇게 하려면,.vsct 파일에 명령을 하나 이상의 특수 UI 컨텍스트 연관 시킵니다. 이러한 UI 컨텍스트 라고 GUID로 식별 되는 *명령 컨텍스트 GUID*합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트를 로드 하거나 편집 하 여 구축 하려는 같은 사용자 동작에서 발생 하는 변경 내용을 모니터링 합니다. 변경 될 때 IDE의 모양이 자동으로 수정 됩니다. 다음 표에서 IDE의 네 가지 주요 컨텍스트를 변경 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 모니터입니다.  
  
|컨텍스트 유형|설명|  
|-------------|--------|  
|현재 프로젝트 형식|대부분의 프로젝트 형식에 대 한이 `GUID` 값은 프로젝트를 구현 하는 VSPackage의 GUID와 동일 합니다. 그러나 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트에 프로젝트 형식을 사용 하 여 `GUID` 값입니다.|  
|활성 창|일반적으로이 키 바인딩에 대 한 현재 UI 컨텍스트를 설정 하는 마지막 현재 문서 창입니다. 그러나 내부 웹 브라우저를 유사한 키 바인딩을 두 테이블이 있는 도구 창 수도 있습니다. HTML 편집기와 같은 다중 탭 문서 창에 대 한 모든 탭에는 다른 명령 컨텍스트가 `GUID`합니다.|  
|현재 언어 서비스|연결 된 파일을 텍스트 편집기에 현재 표시 되는 언어 서비스.|  
|활성 도구 창|열려 있고 포커스가 있는 도구 창입니다.|  
  
 다섯 번째 주요 컨텍스트 영역에는 IDE의 UI 상태입니다. UI 컨텍스트 활성 명령 컨텍스트로 식별 됩니다 `GUID`s, 다음과 같이 합니다.  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionBuilding>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_Debugging>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_Dragging>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_FullScreenMode>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_DesignMode>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_NoSolution>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionExists>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_EmptySolution>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasSingleProject>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasMultipleProjects>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_CodeWindow>  
  
 이러한 Guid는 활성 또는 IDE의 현재 상태에 따라 비활성으로 표시 됩니다. 여러 UI 컨텍스트 동시에 활성화 될 수 있습니다.  
  
### 숨기기 및 컨텍스트를 기반으로 하는 명령 표시  
 표시 하거나 IDE의 패키지 명령과 패키지 자체를 로드 하지 않고 숨길 수 있습니다. 이렇게 하려면 명령 패키지의.vsct 파일에서 사용 하 여 정의 `DefaultDisabled`, `DefaultInvisible`, 및 `DynamicVisibility` 플래그 및 추가 하나 이상의 명령 [VisibilityItem](../../extensibility/visibilityitem-element.md) 하는 요소는 [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md) 섹션. 지정 된 명령 컨텍스트 `GUID` 가 활성 상태 이면 해당 명령을 패키지를 로드 하지 않고 표시 됩니다.  
  
### 사용자 지정 컨텍스트 Guid  
 적절 한 명령 컨텍스트 GUID 아직 정의 되지 않은 경우 VSPackage에서 하나를 정의할 수 있으며 활성 또는 비활성 명령의 표시 유형을 제어 하려면 필요에 따라 되도록를 프로그래밍할 수 있습니다. 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 서비스:  
  
-   컨텍스트 Guid 등록 \(호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCmdUIContextCookie%2A> 메서드\).  
  
-   컨텍스트 상태 가져오기 `GUID` \(호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> 메서드\).  
  
-   컨텍스트 설정 `GUID`s 및 해제 \(호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.SetCmdUIContext%2A> 메서드\).  
  
    > [!CAUTION]
    >  다른 Vspackage에 종속 될 수 있으므로 VSPackage 않습니다 모든 기존 컨텍스트 GUID의 상태를 영향을 주지 않는지 확인 합니다.  
  
## 예제  
 VSPackage command의 다음 예제에서는 동적 VSPackage를 로드 하지 않고 명령 컨텍스트에서 관리 되는 명령 표시 유형을 보여 줍니다.  
  
 이 명령은 사용 하도록 설정 되어 솔루션이 있습니다; 때마다 표시로 설정 되어 즉, 때마다 활성화가 명령 컨텍스트 Guid는 다음 중 하나:  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_EmptySolution>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasMultipleProjects>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasSingleProject>  
  
 예제에서는 모든 명령 플래그는 별도 임을 알 수 [명령 플래그](../../extensibility/command-flag-element.md) 요소입니다.  
  
 [!CODE [DynamicVisibility#01](DynamicVisibility#01)]  
  
 또한 구성 요소 개발자는 별도의 모든 UI 컨텍스트를 제공 해야 `VisibilityItem` 요소를 다음과 같이 합니다.  
  
 [!CODE [DynamicVisibility#02](DynamicVisibility#02)]  
  
## 참고 항목  
 [MenuCommand 및 OleMenuCommand](../../misc/menucommands-vs-olemenucommands.md)   
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Vspackage의 명령 라우팅](../../extensibility/internals/command-routing-in-vspackages.md)   
 [동적으로 메뉴 항목 추가](../../extensibility/dynamically-adding-menu-items.md)