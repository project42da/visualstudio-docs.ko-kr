---
title: "Menu 요소 | Microsoft Docs"
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
  - "VSCT XML 스키마 요소, 메뉴"
  - "메뉴 요소 (VSCT XML 스키마)"
ms.assetid: ce0560f3-b4c9-4ab2-a99c-d4e10f37b9e0
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# Menu 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

메뉴 항목을 정의합니다. 이들은 메뉴의 6 개 종류: 컨텍스트, 메뉴, MenuController, MenuControllerLatched, 도구 모음 및 ToolWindowToolbar 합니다.  
  
## 구문  
  
```  
<Menu guid=”guidMyCommandSet” id=”MyCommand” priority=”0x100” type=”button”>  
  <Parent>... </Parent>  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</Menu>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|guid|필수 요소. GUID\/ID 명령 식별자의 GUID입니다.|  
|ID|필수 요소. ID는 GUID\/ID 명령 식별자입니다.|  
|priority|선택적 요소. 메뉴의 그룹에 메뉴의 상대 위치를 지정 하는 숫자 값입니다.|  
|ToolbarPriorityInBand|선택적 요소. 창을 도킹 한 경우 밴드에는 도구 모음의 상대 위치를 지정 하는 숫자 값입니다.|  
|type|선택적 요소. 요소의 종류를 지정 하는 열거형된 값입니다.<br /><br /> 없는 경우 기본 유형은 메뉴입니다.<br /><br /> 컨텍스트<br /> 사용자가 창을 마우스 오른쪽 단추로 클릭할 때 표시 되는 바로 가기 메뉴. 바로 가기 메뉴에는 다음과 같은 특징이 있습니다.<br /><br /> -   메뉴 바로 가기 메뉴를 표시 하는 경우에 부모 및 우선 순위 필드를 사용 하지 않습니다.<br />-   하위 메뉴로 및 바로 가기 메뉴로 사용할 수 있습니다. 그룹 ID 및 우선 순위 필드 모두 적용 되는 경우.<br />-   항상 사용할 수 없는 경우<br /><br /> 바로 가기 메뉴에는 다음 조건이 true 인 경우에 표시 됩니다.<br /><br /> -   호스팅하고 있는 창이 표시 됩니다.<br />-   VSPackage에서 마우스 처리기 검색 창에서 마우스 오른쪽 단추로 클릭 하 고 명령을 처리 하는 메서드를 호출 합니다.<br />-   바로 가기 메뉴를 호출 하 여 표시 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager.ShowContextMenu%2A> 메서드 \(권장된 하는 방법\) 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A> 메서드.<br /><br /> 메뉴<br /> 드롭다운 메뉴를 제공합니다. 드롭다운 메뉴에는 다음과 같은 특징이 있습니다.<br /><br /> -   해당 정의에서 부모를 따릅니다.<br />-   부모 그룹 또는 그룹에 CommandPlacement 있어야 합니다.<br />-   다른 모든 종류의 메뉴의 하위 메뉴를 수 있습니다.<br />-   부모 메뉴에 표시 될 때마다 자동으로 표시 됩니다.<br />-   표시 하도록 모든 VSPackage 코드를 구현 하지 않아도 됩니다.<br /><br /> MenuController<br /> 도구 모음에서 일반적으로 사용 되는 분할 단추 드롭다운 메뉴를 제공 합니다. MenuController 메뉴에는 다음과 같은 특징이 있습니다.<br /><br /> -   부모 또는 CommandPlacement를 통해 다른 메뉴에 포함 되어야 합니다.<br />-   해당 정의에서 부모를 따릅니다.<br />-   부모 메뉴의 모든 종류를 가질 수 있습니다.<br />-   자동으로 사용할 수 때마다 부모 메뉴에 표시 됩니다.<br />-   표시 되는 메뉴를 확인 하 여 프로그래밍 방식으로 지원 하지 않아도 됩니다.<br /><br /> 분할 단추 메뉴의 명령은 메뉴 단추에 표시 됩니다. 표시 된 명령은 다음과 같은 특징 중 하나에 있습니다.<br /><br /> -   마지막 명령은 명령을 계속 표시 되 고 사용 하도록 설정 하는 경우에 사용 된 경우<br />-   표시 되는 첫 번째 명령 이며<br /><br /> MenuControllerLatched<br /> 명령을 지정할 수 있습니다 기본으로 선택 걸려 있는지 확인 하는 대로 명령을 표시 하 여 분할 단추 드롭다운 메뉴를 제공 합니다.<br /><br /> 래치 명령에 확인 표시를 표시 하 여 일반적으로, 선택 된 것으로 메뉴에 표시 된 명령이입니다. 명령을 OLECMDF\_LATCHED 있으면 걸려 있는지 확인 하는 것으로 표시 수 플래그의 구현에 대해 설정은 `QueryStatus` 의 메서드는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스. MenuControllerLatched 메뉴에는 다음과 같은 특징이 있습니다.<br /><br /> -   부모 그룹 또는 CommandPlacement를 통해 다른 메뉴에 포함 되어야 합니다.<br />-   해당 정의에서 부모를 따릅니다.<br />-   부모 메뉴의 모든 종류를 가질 수 있습니다.<br />-   부모 메뉴에 표시 될 때마다 사용할 수는 있습니다.<br />-   표시 되는 메뉴를 확인 하 여 프로그래밍 방식으로 지원 하지 않아도 됩니다.<br /><br /> 분할 단추 메뉴의 명령은 메뉴 단추에 표시 됩니다. 표시 된 명령은 다음과 같은 특징 중 하나에 있습니다.<br /><br /> -   그는 첫 번째 표시 된 명령은입니다.<br />-   표시 되는 첫 번째 명령 이며<br /><br /> Toolbar<br /> 도구 모음을 제공 합니다. 도구 모음에는 다음과 같은 특징이 있습니다.<br /><br /> -   해당 정의에서 부모를 무시합니다.<br />-   CommandPlacement를 사용 하 여도 모든 그룹의 하위 메뉴를 만들 수 없습니다.<br />-   클릭 하 여 항상 표시가 가능 **도구 모음** 에 **보기** 메뉴.<br />-   사용 하 여 표시할 수는 [VisibilityItem](0932f551-972d-4194-84bb-426e3e4375e4Vis)합니다.<br />-   만드는 코드가 필요 하지 않습니다. 도구 모음을 만드는 방법에 대 한 예제를 참조 하십시오. [도구 모음 추가](../extensibility/adding-a-toolbar.md)합니다.<br /><br /> ToolWindowToolbar<br /> 도구 모음 개발 환경에 연결 된 것 처럼 특정 도구 창에 연결 된 도구 모음을 제공 합니다.<br /><br /> -   해당 정의에서 부모를 무시합니다.<br />-   CommandPlacement를 사용 하 여도 모든 그룹의 하위 메뉴를 만들 수 없습니다.<br />-   도구 모음을 호스팅하는 도구 창이 표시 되 고 VSPackage 도구 창으로 도구 모음을 명시적으로 추가 하는 경우에 표시 됩니다. 도구 창 도구 모음 호스트 속성을 가져오는 방법으로 만들어질 때 이루어집니다 \(여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolWindowToolbarHost> 인터페이스\) 도구 창 프레임 및 호출에서는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolWindowToolbarHost.AddToolbar%2A> 메서드.|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|부모|선택적 요소. 메뉴 항목의 부모 요소입니다.|  
|CommandFlag|필수 요소.[명령 플래그 요소](../extensibility/command-flag-element.md)을 참조하세요. 메뉴에 대해 유효한 CommandFlag 값은 다음과 같습니다.<br /><br /> -   **AlwaysCreate**<br />-   **DefaultDocked**<br />-   **DefaultInvisible** \-이 플래그는 도구 모음 표시에 영향을 주지 않습니다.<br />-   **DontCache**<br />-   **DynamicVisibility** \-이 플래그는 도구 모음 표시에 영향을 주지 않습니다.<br />-   **IconAndText**<br />-   **NoCustomize**<br />-   **NotInTBList**<br />-   **NoToolbarClose**<br />-   **TextChanges**<br />-   **TextIsAnchorCommand**|  
|문자열|필수 요소.[문자열 요소](../extensibility/strings-element.md)을 참조하세요. 자식 `ButtonText` 요소를 정의 해야 합니다.|  
|주석|선택적 설명입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[메뉴 요소](../extensibility/menus-element.md)|VSPackage를 구현 하는 모든 메뉴를 정의 합니다.|  
  
## 예제  
  
```  
<Menu guid="cmdGuidWidgetCommands" id="menuIDEditWidget" priority="0x0002" type="Menu"> <Parent guid="cmdSetGuidWidgetCommands" id="groupIDFileEdit"> <CommandFlag>AlwaysCreate</CommandFlag> <Strings> <ButtonText>Edit Widget</ButtonText> </Strings> </Parent> </Menu>  
```  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)