---
title: Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- user interfaces, adding elements
- UI element design [Visual Studio SDK], VSPackages
- VSPackages, contributing UI elements
ms.assetid: abc5d9d9-b267-48a1-92ad-75fbf2f4c1b9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 930ab9e741b2fd5bbc0ca2954192fe5e2c4313d4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-vspackages-add-user-interface-elements"></a>Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법
VSPackage는 사용자 인터페이스 (UI) 요소, 예를 들어, 메뉴, 도구 모음을 추가할 수 있으며 도구 창은.vsct 파일을 사용 하 여 Visual Studio로.  
  
 UI 요소에 대 한 디자인 지침을 찾을 수 있습니다 [Visual Studio 사용자 환경 지침](../../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)합니다.  
  
## <a name="the-visual-studio-command-table-architecture"></a>Visual Studio 명령 테이블 아키텍처  
 에서 설명한 것 처럼 명령 테이블 아키텍처 위 아키텍처 원칙을 지원 합니다. 추상화, 데이터 구조 및 명령 테이블 아키텍처의 도구 개념은 다음과 같습니다.  
  
-   세 가지 기본의 종류가 항목: 메뉴, 명령 및 그룹입니다. 메뉴는 메뉴, 하위 메뉴, 도구 모음 또는 도구 창으로 UI에 노출 될 수 있습니다. 명령은 프로시저가 사용자 IDE에서 실행할 수 있고 메뉴 항목, 단추, 목록 상자 또는 기타 컨트롤으로 노출 될 수 있습니다. 그룹은 메뉴 및 명령을 모두에 대 한 컨테이너입니다.  
  
-   각 항목은 항목, 동작을 수정 하는 플래그 및 기타 항목을 기준으로 해당 우선 순위를 설명 하는 정의 의해 지정 됩니다.  
  
-   각 항목에는 항목의 부모에 설명 하는 배치 합니다. 항목 UI의 여러 위치에 나타날 수 있도록 여러 부모를 가질 수 있습니다.  
  
     해당 그룹의 유일한 자식인 경우에 모든 명령, 부모과 그룹을 가져야 합니다. 모든 표준 메뉴에는 상위 그룹이 있어야 합니다. 도구 모음 및 도구 창의 자신의 부모로 작동합니다. 그룹 부모 주 Visual Studio 메뉴 모음, 메뉴, 도구 모음 또는 도구 창이 될 수 있습니다.  
  
### <a name="how-items-are-defined"></a>항목을 정의 하는 방법  
 . Vsct 파일 XML 형식이 지정 됩니다. .Vsct 파일 패키지에 대 한 UI 요소를 정의 하 고 해당 요소는 IDE에서 표시 되는 위치를 결정 합니다. 모든 메뉴, 그룹 또는 명령 패키지의 GUID 및 ID를 처음 할당 되는 `Symbols` 섹션. .Vsct의 나머지 부분 전체에서 파일, 각 메뉴, 명령 및 그룹의 GUID 및 ID 조합으로 식별 됩니다. 다음 예제에서는 일반적인 `Symbols` 대로 Visual Studio 패키지 템플릿을 의해 생성 된 경우는 **메뉴 명령** 서식 파일에서 선택 합니다.  
  
```xml  
<Symbols>  
  <!-- This is the package guid. -->  
  <GuidSymbol name="guidMenuTextPkg" value="{b1253bc6-d266-402b-89e7-5e3d3b22c746}" />  
  
  <!-- This is the guid used to group the menu commands together -->  
  <GuidSymbol name="guidMenuTextCmdSet" value="{a633d4e4-6c65-4436-a138-1abeba7c9a69}">  
  
    <IDSymbol name="MyMenuGroup" value="0x1020" />  
    <IDSymbol name="cmdidMyCommand" value="0x0100" />  
  </GuidSymbol>  
  
  <GuidSymbol name="guidImages" value="{53323d9a-972d-4671-bb5b-9e418480922f}" >  
    <IDSymbol name="bmpPic1" value="1" />  
    <IDSymbol name="bmpPic2" value="2" />  
    <IDSymbol name="bmpPicSearch" value="3" />  
    <IDSymbol name="bmpPicX" value="4" />  
    <IDSymbol name="bmpPicArrows" value="5" />  
  </GuidSymbol>  
</Symbols>  
```  
  
 최상위 요소는 `Symbols` 섹션은는 [GuidSymbol 요소](../../extensibility/guidsymbol-element.md)합니다. `GuidSymbol` 요소를 패키지 및 해당 구성 요소 부분을 식별 하는 IDE에서 사용 되는 Guid 이름을 매핑합니다.  
  
> [!NOTE]
>  Guid는 Visual Studio 패키지 템플릿에 의해 자동으로 생성 됩니다. 클릭 하 여 고유 GUID를 만들 수도 있습니다 **GUID 만들기** 에 **도구** 메뉴.  
  
 첫 번째 `GuidSymbol` 요소인 "guid [PackageName] Pkg", 패키지 자체의 GUID입니다. 이것이 Visual Studio에서 패키지를 로드 하는 데 사용 되는 GUID입니다. 일반적으로 자식 요소가 없는지 않습니다.  
  
 아래 두 번째 메뉴 및 명령을 규칙에 따라 그룹화 `GuidSymbol` 요소인 "guid [PackageName] CmdSet", 비트맵은 아래에서 세 번째 및 `GuidSymbol` 요소, "guidImages"입니다. 이 규칙을 따르는 필요는 없지만 각 메뉴, 그룹, 명령 및 비트맵의 자식 이어야 합니다는 `GuidSymbol` 요소입니다.  
  
 두 번째에서 `GuidSymbol` 패키지 명령 집합을 나타내는 요소를 일부의 `IDSymbol` 요소입니다. 각 [IDSymbol 요소](../../extensibility/idsymbol-element.md) 숫자 값으로 이름을 매핑하고 메뉴, 그룹 또는 명령 집합의 일부인 명령을 나타낼 수 있습니다. `IDSymbol` 세 번째에서 요소 `GuidSymbol` 명령에 대 한 아이콘으로 사용할 수 있는 요소 나타내는 비트맵입니다. GUID/i D 쌍 동일한 두 명의 자식이 없는 응용 프로그램에서 고유 해야 하므로 `GuidSymbol` 요소는 동일한 값을 가질 수 있습니다.  
  
### <a name="menus-groups-and-commands"></a>메뉴, 그룹 및 명령  
 메뉴, 그룹 또는 명령에 GUID 및 ID, IDE에 추가할 수 있습니다. 모든 UI 요소에는 다음 사항이 있어야 합니다.  
  
-   A `guid` 특성의 이름과 일치 하는 `GuidSymbol` UI 요소에서 정의 된 요소입니다.  
  
-   `id` 관련 된 이름과 일치 하는 특성 `IDSymbol` 요소입니다.  
  
     함께 `guid` 및 `id` 특성 작성는 *서명* UI 요소입니다.  
  
-   A `priority` 특성을 해당 부모 메뉴 또는 그룹에 있는 UI 요소의 위치를 결정 합니다.  
  
-   A [부모 요소](../../extensibility/parent-element.md) 올려진 `guid` 및 `id` 부모 메뉴 또는 그룹의 서명을 지정 하는 특성입니다.  
  
#### <a name="menus"></a>메뉴  
 로 정의 된 각 메뉴는 [메뉴 요소](../../extensibility/menu-element.md) 에 `Menus` 섹션. 메뉴 있어야 `guid`, `id`, 및 `priority` 특성 및 `Parent` , 또한 다음 추가 특성 및 자식 요소를:  
  
-   A `type` 메뉴 종류의 메뉴 또는 도구 모음으로 IDE에 표시될지 여부를 지정 하는 특성입니다.  
  
-   A [Strings 요소](../../extensibility/strings-element.md) 를 포함 하는 [ButtonText 요소](../../extensibility/buttontext-element.md), IDE에서 메뉴의 제목을 지정 하는 및 [CommandName 요소](../../extensibility/commandname-element.md), 되는 이름을 지정 하는 사용 되는 **명령** 메뉴에 액세스 하는 창입니다.  
  
-   선택적 플래그입니다. A [명령 플래그 요소](../../extensibility/command-flag-element.md) 의 모양이 나 IDE에서 동작을 변경 하려면 메뉴 정의에 나타날 수 있습니다.  
  
 모든 `Menu` 요소 그룹이 있어야 해당 부모와 같은 도구 모음 도킹 가능한 요소가 아닌 경우. 도킹 가능한 메뉴 자체 부모 도메인입니다. 메뉴 및에 대 한 값에 대 한 자세한 내용은 `type` 특성을 참조 하십시오.는 [메뉴 요소](../../extensibility/menu-element.md) 설명서입니다.  
  
 다음 예제에서는 Visual Studio 메뉴 모음에서 다음에 표시 되는 메뉴는 **도구** 메뉴.  
  
```xml  
<Menu guid="guidTopLevelMenuCmdSet"  
id="TopLevelMenu" priority="0x700" type="Menu">  
  <Parent guid="guidSHLMainMenu"  
          id="IDG_VS_MM_TOOLSADDINS" />  
  <Strings>  
    <ButtonText>TestMenu</ButtonText>  
    <CommandName>TestMenu</CommandName>  
  </Strings>  
</Menu>  
```  
  
#### <a name="groups"></a>그룹  
 그룹에 정의 된 항목은는 `Groups` .vsct 파일의 섹션입니다. 그룹은 단지 컨테이너입니다. 메뉴에 구분선으로 되지 제외 하 고 IDE에 표시지 않습니다. 따라서 한 [그룹 요소](../../extensibility/group-element.md) 의 서명, 우선 순위 및 부모를 통해서만 정의 됩니다.  
  
 그룹은 부모도 메뉴, 다른 그룹 또는 자체 가질 수 있습니다. 그러나 부모는 일반적으로 메뉴 또는 도구 모음. 앞의 예제에서 메뉴의 자식인는 `IDG_VS_MM_TOOLSADDINS` 그룹과 해당 그룹에는 Visual Studio 메뉴 모음의 자식입니다. 다음 예제에서 그룹에는 앞의 예제에서 메뉴의 자식입니다.  
  
```  
 <Group guid="guidTopLevelMenuCmdSet" id="MyMenuGroup"  
priority="0x0600">  
   <Parent guid="guidTopLevelMenuCmdSet" id="TopLevelMenu"/>  
 </Group>  
```  
  
 메뉴의 일부 이기 때문에이 그룹에 명령 하는 일반적으로 포함 됩니다. 그러나 다른 메뉴도 포함 될 수 있습니다. 다음 예제와 같이 하위 메뉴 정의 하는 방법입니다.  
  
```xml  
<Menu guid="guidTopLevelMenuCmdSet" id="SubMenu"  
priority="0x0100" type="Menu">  
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup"/>  
  <Strings>  
    <ButtonText>Sub Menu</ButtonText>  
    <CommandName>Sub Menu</CommandName>  
  </Strings>  
</Menu>  
```  
  
#### <a name="commands"></a>명령  
 IDE에 제공 되는 명령으로 정의 된 한 [Button 요소](../../extensibility/button-element.md) 또는 [콤보 요소](../../extensibility/combo-element.md)합니다. 메뉴 또는 도구 모음에 나타내려면 명령을 상위 그룹이 있어야 합니다.  
  
##### <a name="buttons"></a>단추  
 단추에 정의 된는 `Buttons` 섹션. 모든 메뉴 항목, 단추 또는 단일 명령을 실행 하는 사용자가 클릭 하는 기타 요소의 단추를 간주 됩니다. 일부 단추 형식 목록 기능을 포함할 수도 있습니다. 단추에 필요한 동일 및 메뉴에는 선택적 특성 포함 할당할 수 있습니다는 [아이콘 요소](../../extensibility/icon-element.md) GUID와 IDE에서 단추를 나타내는 비트맵의 ID를 지정 하는 합니다. 단추와 해당 특성에 대 한 자세한 내용은 참조는 [단추 요소](../../extensibility/buttons-element.md) 설명서입니다.  
  
 다음 예제에 있는 단추는 앞의 예에 있는 그룹의 자식이 고 해당 그룹의 부모 메뉴에서 메뉴 항목으로 IDE에 표시 되는 합니다.  
  
```  
<Button guid="guidTopLevelMenuCmdSet" id="cmdidTestCommand" priority="0x0100" type="Button">  
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup" />  
  <Icon guid="guidImages" id="bmpPic1" />  
  <Strings>  
    <CommandName>cmdidTestCommand</CommandName>  
    <ButtonText>Test Command</ButtonText>  
  </Strings>  
</Button>  
```  
  
##### <a name="combos"></a>바로 가기 단축키 +  
 에 정의 된 바로 가기 단축키 +는 `Combos` 섹션. 각 `Combo` IDE에서 드롭 다운 목록 상자 요소를 나타냅니다. 목록 상자 되거나 값에 따라 사용자가 쓰기 가능 되지 않을 수 있습니다는 `type` 콤보의 특성입니다. 바로 가기 단축키 +에 같은 요소가 있고 단추 동작 있으며 다음 추가 특성을 가질 수도 수 있습니다.  
  
-   A `defaultWidth` 픽셀 너비를 지정 하는 특성입니다.  
  
-   `idCommandList` 목록 상자에 표시 되는 항목을 포함 하는 목록을 지정 하는 특성입니다. 명령 목록에 동일한 선언 해야 `GuidSymbol` 콤보 들어 있는 노드입니다.  
  
 다음 예제에서는 콤보 요소를 정의합니다.  
  
```xml  
<Combos>  
  <Combo guid="guidFirstToolWinCmdSet"  
         id="cmdidWindowsMediaFilename"  
         priority="0x0100" type="DynamicCombo"  
         idCommandList="cmdidWindowsMediaFilenameGetList"  
         defaultWidth="130">  
    <Parent guid="guidFirstToolWinCmdSet"  
            id="ToolbarGroupID" />  
    <CommandFlag>IconAndText</CommandFlag>  
    <CommandFlag>CommandWellOnly</CommandFlag>  
    <CommandFlag>StretchHorizontally</CommandFlag>  
    <Strings>  
      <CommandName>Filename</CommandName>  
      <ButtonText>Enter a Filename</ButtonText>  
    </Strings>  
  </Combo>  
</Combos>  
```  
  
##### <a name="bitmaps"></a>비트맵  
 아이콘과 함께 표시 되는 명령에 포함 해야 합니다는 `Icon` 해당 GUID 및 ID를 사용 하 여 비트맵을 참조 하는 요소 각 비트맵으로 정의 되는 [비트맵 요소](../../extensibility/bitmap-element.md) 에 `Bitmaps` 섹션. 특성에 대 한 유일한 필수는 `Bitmap` 정의 `guid` 및 `href`, 소스 파일을 가리키는 합니다. 소스 파일이 리소스 스트립 하는 경우는 **usedList** 특성은도 스트립에서 사용 가능한 이미지를 나열 하려면 필요 합니다. 자세한 내용은 참조는 [비트맵 요소](../../extensibility/bitmap-element.md) 설명서입니다.  
  
### <a name="parenting"></a>부모/자식 관리  
 다음 규칙 항목 부모와 다른 항목을 호출 하는 방법을 제어 합니다.  
  
|요소|명령 테이블의이 섹션에 정의 된|포함 될 수 있습니다 (한 부모 또는 위치에 의해는 `CommandPlacements` 섹션 또는 둘 다)|포함 될 수 있습니다 (부모 라고도 함)|  
|-------------|--------------------------------------------------|---------------------------------------------------------------------------------------------------|---------------------------------------------|  
|그룹화|[Groups 요소](../../extensibility/groups-element.md), IDE, 다른 Vspackage|메뉴에서 그룹을 항목 자체|메뉴, 그룹 및 명령|  
|메뉴|[메뉴 요소](../../extensibility/menus-element.md), IDE, 다른 Vspackage|1 ~ *n* 그룹|0 ~ *n* 그룹|  
|Toolbar|[메뉴 요소](../../extensibility/menus-element.md), IDE, 다른 Vspackage|항목 자체가|0 ~ *n* 그룹|  
|메뉴 항목|[요소는 단추](../../extensibility/buttons-element.md), IDE, 다른 Vspackage|1 ~ *n* 항목 자체를 그룹화|-0 ~ *n* 그룹|  
|단추|[요소는 단추](../../extensibility/buttons-element.md), IDE, 다른 Vspackage|1 ~ *n* 항목 자체를 그룹화||  
|콤보|[바로 가기 단축키 + 요소](../../extensibility/combos-element.md), IDE, 다른 Vspackage|1 ~ *n* 항목 자체를 그룹화||  
  
### <a name="menu-command-and-group-placement"></a>메뉴, 명령 및 그룹 배치  
 메뉴, 그룹 또는 명령 IDE에서 둘 이상의 위치에 나타날 수 있습니다. 여러 위치에 표시 되도록 항목을 추가 해야 하는 `CommandPlacements` 섹션으로 [CommandPlacement 요소](../../extensibility/commandplacement-element.md)합니다. 모든 메뉴, 그룹 또는 명령 명령 배치도 추가할 수 있습니다. 그러나 상황에 맞는 여러 위치에 나타날 수 없습니다 있기 때문에 도구 모음 이런이 방식으로 배치할 수 없습니다.  
  
 명령 배치를가 `guid`, `id`, 및 `priority` 특성입니다. GUID 및 ID에 배치 되는 항목의 일치 해야 합니다. `priority` 특성의 다른 항목을 고려 하 여 항목 배치를 제어 합니다. IDE 동일한 우선 순위를 가진 두 개 이상의 항목을 병합 하는 경우에 IDE 확정 되어 있지 않으므로 빌드될 때마다 패키지 리소스 동일한 순서로 읽기는 해당 위치 정의 되지 않습니다.  
  
 메뉴 또는 그룹을 여러 위치에 있으면 해당 메뉴 또는 그룹의 모든 자식 인스턴스마다에 표시 됩니다.  
  
## <a name="command-visibility-and-context"></a>명령 표시 유형 및 컨텍스트  
 여러 Vspackage 설치 되 면 메뉴, 메뉴 항목 및 도구 모음 수많은 IDE 복잡 수 있습니다. 이 문제를 방지 하려면 사용 하 여 개별 UI 요소의 표시 여부를 제어할 수 있습니다 *표시 제약 조건은* 및 명령 플래그입니다.  
  
##### <a name="visibility-constraints"></a>표시 유형 제약 조건  
 표시 유형 제약 조건으로 설정 됩니다는 [VisibilityItem 요소](../../extensibility/visibilityitem-element.md) 에 `VisibilityConstraints` 섹션. 표시 유형 제약 조건을 대상 항목이 표시 되는 특정 UI 컨텍스트를 정의 합니다. 메뉴 또는이 섹션에 포함 된 명령을 정의 된 컨텍스트 중 하나가 활성화 되어 있는 경우에 표시 됩니다. 이 섹션에서는 메뉴 또는 명령을 참조 하지 않은 경우 항상 이므로 기본적으로 표시 합니다. 이 섹션 그룹에 적용 되지 않습니다.  
  
 `VisibilityItem` 요소에 있어야 세 개의 특성이 다음과 같이:는 `guid` 및 `id` 대상 UI 요소의 및 `context`합니다. `context` 특성 시기를 지정 된 대상 항목을 볼 수는 해당 값으로 유효한 모든 UI 컨텍스트를 사용 합니다. Visual Studio에 대 한 UI 컨텍스트 상수는의 멤버는 <xref:Microsoft.VisualStudio.VSConstants> 클래스입니다. 모든 `VisibilityItem` 요소 하나의 컨텍스트 값을 사용할 수 있습니다. 두 번째 컨텍스트를 적용 하려면 두 번째 만들 `VisibilityItem` 다음 예제와 같이 동일한 항목을 가리키는 요소입니다.  
  
```xml  
<VisibilityConstraints>  
  <VisibilityItem guid="guidSolutionToolbarCmdSet"  
        id="cmdidTestCmd"  
        context="UICONTEXT_SolutionHasSingleProject" />  
  <VisibilityItem guid="guidSolutionToolbarCmdSet"  
        id="cmdidTestCmd"  
        context="UICONTEXT_SolutionHasMultipleProjects" />  
</VisibilityConstraints>  
```  
  
##### <a name="command-flags"></a>명령 플래그  
 다음 명령 플래그 메뉴 및 명령을 적용할 때의 표시 여부에 영향을 줄 수입니다.  
  
 AlwaysCreate  
 메뉴 단추 또는 그룹이 아니면 경우에 만들어집니다.  
  
 에 대해 유효 합니다. `Menu`  
  
 CommandWellOnly  
 적용이 플래그는 명령이 최상위 메뉴에 표시 되지 않는 추가 셸 사용자 지정에 사용할 수 있도록 하려는 경우 예를 들어를 키에 바인딩. 사용자가 열어 이러한 명령을 사용자 지정할 수는 VSPackage를 설치한 후는 **옵션** 대화 상자에서 명령 배치를 편집 하 고는 **키보드 환경** 범주입니다. 바로 가기 메뉴, 도구 모음, 메뉴 컨트롤러 또는 하위 메뉴에서 배치 영향을 주지 않습니다.  
  
 에 대 한 유효한: `Button`, `Combo`  
  
 DefaultDisabled  
 기본적으로이 명령은 명령을 구현 하는 VSPackage이 로드 되지 않았거나 QueryStatus 메서드가 호출 되지 않은 경우 비활성화 됩니다.  
  
 에 대 한 유효한: `Button`, `Combo`  
  
 DefaultInvisible  
 기본적으로이 명령은 표시 되지 않습니다 명령을 구현 하는 VSPackage이 로드 되지 않았거나 QueryStatus 메서드가 호출 되지 않은 경우.  
  
 와 함께 사용할 해야는 `DynamicVisibility` 플래그입니다.  
  
 에 대 한 유효한: `Button`, `Combo`, `Menu`  
  
 DynamicVisibility  
 QueryStatus 메서드 또는에 포함 된 GUID의 컨텍스트를 사용 하 여 명령의 표시 유형을 변경할 수 있습니다는 `VisibilityConstraints` 섹션.  
  
 도구 모음에 없는 메뉴에 표시 되는 명령에 적용 됩니다. 최상위 도구 모음 항목을 사용할 수는 있지만 숨겨져 있지 않으면이 QueryStatus 메서드에서 OLECMDF_INVISIBLE 플래그를 반환 하는 경우.  
  
 메뉴에서이 플래그도 것 해야 자동으로 숨김을 나타냅니다 해당 멤버가 숨겨져 있습니다. 최상위 메뉴에 이미이 동작은 있기 때문에이 플래그는 일반적으로 하위 메뉴에 할당 됩니다.  
  
 와 함께 사용할 해야는 `DefaultInvisible` 플래그입니다.  
  
 에 대 한 유효한: `Button`, `Combo`, `Menu`  
  
 NoShowOnMenuController  
 메뉴 컨트롤러 등이 플래그가 있는 명령이 있을 경우이 명령은 드롭 다운 목록에 나타나지 않습니다.  
  
 에 대해 유효 합니다. `Button`  
  
 명령 플래그에 대 한 자세한 내용은 참조는 [명령 플래그 요소](../../extensibility/command-flag-element.md) 설명서입니다.  
  
##### <a name="general-requirements"></a>일반 요구 사항  
 명령 그 수를 표시 하 고 사용 하도록 설정 하기 전에 다음과 같은 일련의 테스트를 통과 해야:  
  
-   명령은 올바르게 배치 됩니다.  
  
-   `DefaultInvisible` 플래그가 설정 되지 않았습니다.  
  
-   부모 메뉴 또는 도구 모음에 표시 됩니다.  
  
-   컨텍스트 항목으로 인해 명령이 표시 되지 않습니다는 [VisibilityConstraints 요소](../../extensibility/visibilityconstraints-element.md) 섹션.  
  
-   VSPackage 구현 하는 코드는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스 표시 하며 명령을 수 있습니다. 인터페이스 코드가 없습니다 것을 차단 하 고 작업 것입니다.  
  
-   에 설명 된 절차에 따라 막대로 명령을 클릭할 때 [라우팅 알고리즘](../../extensibility/internals/command-routing-algorithm.md)합니다.  
  
## <a name="calling-pre-defined-commands"></a>미리 정의 된 명령 호출  
 [UsedCommands 요소](../../extensibility/usedcommands-element.md) 명령에 액세스할 때 다른 Vspackage에서 또는 IDE에 의해 제공 되는 Vspackage를 사용 하도록 설정 합니다. 이 작업을 수행 하려면 만듭니다는 [UsedCommand 요소](../../extensibility/usedcommand-element.md) 된 GUID 및 명령 사용의 ID입니다. 이렇게 하면 현재 Visual Studio 구성의에 속하지 않은 경우에 Visual Studio에서 명령을 로드는. 자세한 내용은 참조 [UsedCommand 요소](../../extensibility/usedcommand-element.md)합니다.  
  
## <a name="interface-element-appearance"></a>인터페이스 요소 모양  
 선택 하 고 명령 요소 위치 지정에 대 한 고려 사항은 다음과 같습니다.  
  
-   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 배치에 따라 다르게 표시 되는 많은 UI 요소를 제공 합니다.  
  
-   사용 하 여 정의 하는 UI 요소는 `DefaultInvisible` VSPackage 구현 하 여 표시 하지 않은 플래그 IDE에서 표시 되지 것입니다는 <xref:EnvDTE.IDTCommandTarget.QueryStatus%2A> 메서드를 특정 UI 컨텍스트와 관련 된는 `VisibilityConstraints` 섹션.  
  
-   명령은 성공적으로 위치 지정된도 표시 될 수 있습니다. 이 IDE 자동으로 숨기 거 나 VSPackage에 (또는 하지 않았으면) 하는 인터페이스에 따라 일부 명령을 표시 하기 때문에 구현 됩니다. 예를 들어 일부 VSPackage 구현 자동으로 표시 되도록 원인을 빌드 관련 메뉴 항목 인터페이스를 빌드합니다.  
  
-   적용 된 `CommandWellOnly` 플래그 UI 요소의 정의에 의미 명령을 사용자 지정 하 여만 추가할 수 있습니다.  
  
-   IDE가 디자인 보기에는 대화 상자가 표시 되는 경우에 명령은 예를 들어 특정 UI 컨텍스트에만 사용할 수 있습니다.  
  
-   IDE에 표시할 특정 UI 요소를 하나 이상의 인터페이스를 구현 하거나 일부 코드를 작성 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메뉴 및 명령 확장](../../extensibility/extending-menus-and-commands.md)