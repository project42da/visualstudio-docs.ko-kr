---
title: 명령을 사용할 수 있도록 | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus [Visual Studio SDK], commands
- best practices, menu and toolbar commands
- toolbars [Visual Studio], best practices
- menu commands, best practices
ms.assetid: 3ffc4312-c6db-4759-a946-a4bb85f4a17a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5e20fd9b1b13dfc8159181ee2cb8f5d8966f6faf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="making-commands-available"></a>명령을 사용 가능
Visual Studio에 여러 Vspackage를 추가 하는 경우 사용자 인터페이스 (UI) 명령을 사용 하 여 들어오지 될 수 있습니다. 다음과 같이이 문제를 줄이기 위해 패키지를 프로그래밍할 수 있습니다.

-   패키지 프로그램 사용자 경우에 로드 되도록 사용 해야 합니다.

-   명령을 컨텍스트의 통합된 개발 환경 (IDE)의 현재 상태에서 필요할 수 있습니다 하는 경우에 표시 되도록 패키지를 프로그래밍 합니다.

## <a name="delayed-loading"></a>지연 로드
 사용 하도록 설정 하는 일반적인 방법은 해당 명령이 UI에 표시 됩니다. 그러나 사용자가 명령 중 하나를 클릭할 때까지 패키지 자체 로드 되지는 있도록 VSPackage를 디자인 하는 지연 로드 합니다. 이를 위해,.vsct 파일에 없는 명령 플래그를 있는 명령을 만듭니다.

 다음 예제에서는.vsct 파일에서 메뉴 명령 정의 보여줍니다. Visual Studio 패키지 템플릿에서 생성 되는 명령 때는 **메뉴 명령을** 서식 파일에 대 한 옵션을 선택 합니다.

```xml
<Button guid="guidTopLevelMenuCmdSet" id="cmdidTestCommand" priority="0x0100" type="Button">
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup" />
  <Icon guid="guidImages" id="bmpPic1" />
  <Strings>
    <CommandName>cmdidTestCommand</CommandName>
    <ButtonText>Test Command</ButtonText>
  </Strings>
</Button>

```

 예제에서는 경우 부모 그룹 `MyMenuGroup`의 자식인 최상위 메뉴와 같은 **도구** 메뉴 명령이 해당 메뉴에 표시 됩니다. 하지만 명령을 클릭할 때까지 명령을 실행 하는 패키지를 로드 하지 것입니다 사용자입니다. 그러나 프로그래밍을 구현 하는 명령으로는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스를 패키지 명령이 포함 된 메뉴 먼저 확장 하는 경우 로드를 사용할 수 있습니다.

 지연된 로드 시작 시 성능이 향상 될 수 있습니다를 확인 합니다.

## <a name="current-context-and-the-visibility-of-commands"></a>현재 컨텍스트 및 명령 표시
 VSPackage 명령을 표시 / 숨김 VSPackage 데이터 또는 현재 관련이 있는 작업의 현재 상태에 따라 수를 프로그래밍할 수 있습니다. 구현을 사용 하 여 일반적으로 해당 명령의 상태를 설정 하기 위해 VSPackage를 사용 하도록 설정할 수는 <xref:EnvDTE.IDTCommandTarget.QueryStatus%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스 되지만이 코드를 실행 하기 전에 로드할 VSPackage 필요 합니다. 대신 패키지를 로드 하지 않고 명령의 표시 유형을 관리 하는 IDE를 사용 하는 것이 좋습니다. .Vsct 파일에서이 작업을 수행 하려면 하나 이상의 특수 UI 컨텍스트 명령을 연결 합니다. 이러한 UI 컨텍스트가 라고 하는 GUID로 식별 되는 *명령 컨텍스트부터 GUID*합니다.

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트를 로드 하거나 편집 하 여 빌드 하려는 등의 사용자 작업에 따른 변경 내용을 모니터링 합니다. 변경 사항이 있을 때 IDE의 모양은 자동으로 수정 됩니다. IDE의 네 가지 주요 컨텍스트를 변경 하는 다음 표에 나와 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 모니터입니다.

|컨텍스트 유형|설명|
|---------------------|-----------------|
|현재 프로젝트 형식|대부분의 프로젝트 형식에 대 한이 `GUID` 값은 프로젝트를 구현 하는 VSPackage의 GUID와 같습니다. 그러나 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 프로젝트 프로젝트 형식을 사용 하 여 `GUID` 값으로.|
|활성 창|일반적으로 키 바인딩에 대 한 현재 UI 컨텍스트를 설정 하는 마지막 현재 문서 창입니다. 그러나 내부 웹 브라우저를 유사한 키 바인딩을 두 테이블이 있는 도구 창 수 있습니다. HTML 편집기와 같은 다중 탭 문서 창에 대 한 모든 탭에는 다른 명령 컨텍스트부터 `GUID`합니다.|
|현재 언어 서비스|텍스트 편집기에 현재 표시 되는 파일와 연결 된 언어 서비스입니다.|
|활성 도구 창|가 열려 있고 여기에 포커스가 있는 도구 창입니다.|

 다섯 번째 주요 컨텍스트 영역에는 IDE의 UI 상태입니다. UI 컨텍스트 활성 명령 컨텍스트부터 공백과 `GUID`다음과 같이 s:

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionBuilding_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.Debugging_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.Dragging_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.FullScreenMode_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.DesignMode_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.NoSolution_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExists_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.EmptySolution_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionHasSingleProject_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionHasMultipleProjects_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.CodeWindow_guid>

 이러한 Guid는 활성 또는 IDE의 현재 상태에 따라 비활성으로 표시 됩니다. 여러 UI 컨텍스트는 동시에 활성화할 수 있습니다.

### <a name="hiding-and-displaying-commands-based-on-context"></a>숨기기 및 컨텍스트에 따라 명령 표시
 표시 하거나 패키지 자체를 로드 하지 않고 IDE에서 패키지 명령을 숨길 수 있습니다. 이 수행 하려면 명령을 패키지의.vsct 파일에서 사용 하 여 정의 `DefaultDisabled`, `DefaultInvisible`, 및 `DynamicVisibility` 플래그와 추가 하나 이상의 명령을 [VisibilityItem](../../extensibility/visibilityitem-element.md) 요소를 사용 하 여 [ VisibilityConstraints](../../extensibility/visibilityconstraints-element.md) 섹션. 지정 된 명령 컨텍스트 `GUID` 됩니다 활성 상태 이면 해당 명령을 패키지를 로드 하지 않고 표시 됩니다.

### <a name="custom-context-guids"></a>사용자 지정 컨텍스트 Guid
 적절 한 명령 컨텍스트부터 GUID 아직 정의 되지 않은 경우에 VSPackage의 하나를 정의 수 있으며 활성 또는 비활성으로 명령을 표시 유형을 제어 하는 데 필요한 되도록를 프로그래밍할 수 있습니다. 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 서비스:

-   컨텍스트 Guid 등록 (호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCmdUIContextCookie%2A> 메서드).

-   컨텍스트의 상태를 가져오기 `GUID` (호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> 메서드).

-   컨텍스트를 설정 `GUID`s 및 해제 (호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.SetCmdUIContext%2A> 메서드).

    > [!CAUTION]
    > 다른 Vspackage에 종속 될 수 있으므로 VSPackage가 모든 기존 컨텍스트 GUID의 상태를 영향을 주지 않는지 확인 합니다.

## <a name="example"></a>예제
 VSPackage 명령의 다음 예제에서 VSPackage를 로드 하지 않고 명령 컨텍스트에서 관리 되는 명령의 동적 표시 유형입니다.

 이 명령은 설정 되 고 솔루션이 있습니다; 때마다 표시로 설정 되어 즉, 다음 명령 컨텍스트부터 Guid 중 하나가 활성화 될 때마다:

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_EmptySolution>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasMultipleProjects>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasSingleProject>

예제에서는 모든 명령 플래그는 별도 것을 확인할 [명령 플래그](../../extensibility/command-flag-element.md) 요소입니다.

```xml
<Button guid="guidDynamicVisibilityCmdSet" id="cmdidMyCommand"
        priority="0x0100" type="Button">
  <Parent guid="guidDynamicVisibilityCmdSet" id="MyMenuGroup" />
  <Icon guid="guidImages" id="bmpPic1" />
  <CommandFlag>DefaultDisabled</CommandFlag>
  <CommandFlag>DefaultInvisible</CommandFlag>
  <CommandFlag>DynamicVisibility</CommandFlag>
  <Strings>
    <CommandName>cmdidMyCommand</CommandName>
    <ButtonText>My Command name</ButtonText>
  </Strings>
</Button>
```

또한 별개의 모든 UI 컨텍스트를 제공 해야 하는 확인 `VisibilityItem` 요소를 다음과 같이 합니다.

```xml
<VisibilityConstraints>
  <VisibilityItem guid="guidDynamicVisibilityCmdSet"
                  id="cmdidMyCommand" context="UICONTEXT_EmptySolution" />
  <VisibilityItem guid="guidDynamicVisibilityCmdSet"
                      id="cmdidMyCommand" context="UICONTEXT_SolutionHasSingleProject" />
  <VisibilityItem guid="guidDynamicVisibilityCmdSet"
                  id="cmdidMyCommand" context="UICONTEXT_SolutionHasMultipleProjects" />
</VisibilityConstraints>
```

## <a name="see-also"></a>참고자료

- [MenuCommand 및 OleMenuCommand](../../extensibility/menucommands-vs-olemenucommands.md)
- [VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [VSPackage의 명령 라우팅](../../extensibility/internals/command-routing-in-vspackages.md)
- [메뉴 항목 동적 추가](../../extensibility/dynamically-adding-menu-items.md)