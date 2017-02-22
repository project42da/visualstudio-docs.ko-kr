---
title: "Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법 | Microsoft Docs"
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
  - "요소를 추가 하는 사용자 인터페이스"
  - "Vspackage UI 요소 디자인 [Visual Studio SDK]"
  - "Vspackage를 UI 요소를 기여 합니다."
ms.assetid: abc5d9d9-b267-48a1-92ad-75fbf2f4c1b9
caps.latest.revision: 60
caps.handback.revision: 60
ms.author: "gregvanl"
manager: "ghogen"
---
# Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

VSPackage는 사용자 인터페이스 \(UI\) 요소, 예를 들어, 메뉴, 도구 모음을 추가 하 고 도구.vsct 파일을 사용 하 여 Visual studio 창을 수 있습니다.  
  
 UI 요소에 대 한 디자인 지침을 찾을 수 있습니다 [Visual Studio 사용자 환경 지침](../../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)합니다.  
  
## Visual Studio 명령 테이블 아키텍처  
 앞에서 설명한 것 처럼 명령 테이블 아키텍처는 앞서 언급 한 아키텍처 원칙을 지원 합니다. 추상화, 데이터 구조 및 도구 명령 테이블 아키텍처의 개념은 다음과 같습니다.  
  
-   항목의 세 기본 종류: 메뉴, 명령 및 그룹입니다. 메뉴는 메뉴, 하위 메뉴, 도구 모음 또는 도구 창으로 UI에 노출 될 수 있습니다. 주석은 프로시저를 사용자 IDE에서 실행할 수 있고 메뉴 항목, 단추, 목록 상자 또는 기타 컨트롤으로 노출 될 수 있습니다. 그룹은 메뉴 및 명령을 모두에 대 한 컨테이너입니다.  
  
-   각 항목은 항목, 다른 항목 및 해당 동작을 수정 하는 플래그를 기준으로 우선 순위를 설명 하는 정의 의해 지정 됩니다.  
  
-   각 항목에는 항목의 부모에 설명 하는 배치 합니다. 항목 UI의 여러 위치에서 사용 될 수 있도록 여러 부모를 가질 수 있습니다.  
  
     모든 명령 있어야 그룹 부모, 해당 그룹의 유일한 자식인 경우에 합니다. 모든 표준 메뉴에는 부모 그룹이 있어야 합니다. 도구 모음 및 도구 창을 직접 부모로 적용 됩니다. 그룹은 부모 주 Visual Studio 메뉴 모음에서 메뉴, 도구 모음 또는 도구 창으로 가질 수 있습니다.  
  
### 항목 정의 되는 방법  
 . Vsct 파일은 XML 형식이 지정 됩니다. .Vsct 파일 패키지에 대 한 UI 요소를 정의 하 고 IDE에서 이러한 요소가 표시 되는 위치를 결정 합니다. 모든 메뉴, 그룹 또는 패키지에 명령 GUID 및 ID를 처음 할당 되는 `Symbols` 섹션입니다. .vsct의 나머지 부분에서 파일, 각 메뉴, 명령 및 그룹의 GUID 및 ID 조합으로 식별 됩니다. 다음 예제에서는 일반적인 `Symbols` Visual Studio 패키지 템플릿에 의해 생성 섹션 때는 **메뉴 명령** 서식 파일에서를 선택 합니다.  
  
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
  
 최상위 요소는 `Symbols` 섹션은는 [GuidSymbol 요소](../../extensibility/guidsymbol-element.md)합니다.`GuidSymbol` 요소를 패키지 및 해당 구성 요소를 식별 하는 IDE에서 사용 되는 Guid 이름을 매핑합니다.  
  
> [!NOTE]
>  Guid는 Visual Studio 패키지 템플릿에 의해 자동으로 생성 됩니다. 고유 GUID를 클릭 하 여 만들 수도 있습니다 **GUID 만들기** 에 **도구** 메뉴.  
  
 첫 번째 `GuidSymbol` 요소를 "\[패키지 이름\] guid Pkg", 패키지 자체의 GUID입니다. Visual Studio에서 패키지를 로드 하는 데 사용 되는 GUID입니다. 일반적으로 하지 않은 자식 요소입니다.  
  
 아래 두 번째 메뉴 및 명령을 규칙에 따라 그룹화 `GuidSymbol` 요소를 "guid \[패키지 이름\] CmdSet", 비트맵은 아래에서 세 번째 및 `GuidSymbol` 요소, "guidImages"입니다. 이 규칙을 따르는 필요는 없지만 각 메뉴, 그룹, 명령 및 비트맵의 자식 이어야 합니다는 `GuidSymbol` 요소입니다.  
  
 두 번째에서 `GuidSymbol` 패키지 명령 집합을 나타내는 요소는 여러 `IDSymbol` 요소입니다. 각 [IDSymbol 요소](../../extensibility/idsymbol-element.md) 을 숫자 값으로 이름을 매핑하고 메뉴, 그룹 또는 명령을 명령 집합의 일부인 나타낼 수 있습니다.`IDSymbol` 세 번째에서 요소 `GuidSymbol` 명령에 대 한 아이콘으로 사용할 수 있는 요소 나타내는 비트맵입니다. GUID\/ID 쌍 동일한 두 명의 자식이 없는 응용 프로그램에서 고유 해야 하므로 `GuidSymbol` 요소는 동일한 값을 가질 수 있습니다.  
  
### 메뉴, 그룹 및 명령  
 메뉴, 그룹 또는 명령 GUID 및 ID에 있는 경우에 IDE에 추가할 수 있습니다. 모든 UI 요소에는 다음 작업이 있어야 합니다.  
  
-   A `guid` 특성의 이름과 일치 하는 `GuidSymbol` UI 요소에서 정의 된 요소입니다.  
  
-   `id` 관련 된 이름과 일치 하는 특성 `IDSymbol` 요소입니다.  
  
     함께 `guid` 및 `id` 특성 작성은 *서명* UI 요소입니다.  
  
-   A `priority` 해당 부모 메뉴 또는 그룹에 있는 UI 요소의 위치를 결정 하는 특성입니다.  
  
-   A [부모 요소](../../extensibility/parent-element.md) 있는 `guid` 및 `id` 부모 메뉴 또는 그룹의 시그니처를 지정 하는 특성입니다.  
  
#### 메뉴  
 각 메뉴로 정의 되는 [Menu 요소](../../extensibility/menu-element.md) 에 `Menus` 섹션입니다. 메뉴 있어야 `guid`, `id`, 및 `priority` 특성 및 `Parent` 요소, 고도 다음과 같은 추가 특성 및 자식:  
  
-   A `type` 메뉴 도구 모음 또는 메뉴의 한 종류로 IDE에 표시될지 여부를 지정 하는 특성입니다.  
  
-   A [문자열 요소](../../extensibility/strings-element.md) 를 포함 하는 [요소를 로드 합니다](../../extensibility/buttontext-element.md), IDE에는 메뉴의 제목을 지정 하는 및 [CommandName 요소](../../extensibility/commandname-element.md), 에 사용 되는 이름을 지정 하는 **명령** 메뉴에 액세스 하는 창입니다.  
  
-   선택적 플래그입니다. A [명령 플래그 요소](../../extensibility/command-flag-element.md) 의 모양이 나 IDE에서 동작을 변경 하려면 메뉴 정의에 나타날 수 있습니다.  
  
 모든 `Menu` 하지 않은 경우는 도킹 가능한 요소는 도구 모음과 같은 요소를 부모 그룹 있어야 합니다. 도킹 가능한 메뉴는 자체의 부모입니다. 메뉴 및에 대 한 값에 대 한 자세한 내용은 `type` 특성에서 참조는 [Menu 요소](../../extensibility/menu-element.md) 설명서입니다.  
  
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
  
#### 그룹  
 그룹에 정의 된 항목은는 `Groups` .vsct 파일의 섹션입니다. 그룹은 단순히 컨테이너입니다. 것으로 나타나지 않습니다 제외 하 고 IDE의 메뉴에 경계선을 긋습니다. 따라서 한 [그룹 요소](../../extensibility/group-element.md) 의 서명, 우선 순위 및 부모를 통해서만 정의 됩니다.  
  
 그룹은 부모 메뉴, 다른 그룹 또는 자체 가질 수 있습니다. 그러나 부모는 일반적으로 메뉴 또는 도구 모음. 앞의 예제에는 메뉴의 자식인는 `IDG_VS_MM_TOOLSADDINS` 그룹과 해당 그룹의 자식인 Visual Studio 메뉴 모음입니다. 다음 예제에서 그룹에는 앞의 예제에는 메뉴의 자식입니다.  
  
```  
 <Group guid="guidTopLevelMenuCmdSet" id="MyMenuGroup"  
priority="0x0600">  
   <Parent guid="guidTopLevelMenuCmdSet" id="TopLevelMenu"/>  
 </Group>  
```  
  
 메뉴의 일부 이기 때문에이 그룹에 명령 하는 일반적으로 포함 됩니다. 그러나 다른 메뉴도 포함 될 수 있습니다. 이것이, 다음 예제와 같이 하위 정의 되는 방법입니다.  
  
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
  
#### 명령  
 IDE에 제공 되는 명령으로 정의 된 한 [Button 요소](../../extensibility/button-element.md) 또는 [콤보 요소](../../extensibility/combo-element.md)합니다. 메뉴 또는 도구 모음에 나타내려면 명령은 부모 그룹이 있어야 합니다.  
  
##### 단추  
 단추에 정의 된 `Buttons` 섹션입니다. 모든 메뉴 항목, 단추 또는 단일 명령을 실행 하는 사용자가 클릭 하는 다른 요소는 단추를 간주 됩니다. 일부 단추 종류 목록 기능을 포함할 수도 있습니다. 단추는 필요한 동일한 및 메뉴에는 선택적 특성이 있으며 있을 수도 있습니다는 [Icon 요소](../../extensibility/icon-element.md) GUID와 IDE에서 단추를 나타내는 비트맵의 ID를 지정 하는 합니다. 단추와 해당 특성에 대 한 자세한 내용은 참조는 [단추 요소](../../extensibility/buttons-element.md) 설명서입니다.  
  
 다음 예제에 있는 단추는 앞의 예에 있는 그룹의 자식이 고 해당 그룹의 부모 메뉴에서 메뉴 항목으로 IDE에 나타납니다.  
  
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
  
##### 바로 가기 단축키 \+  
 바로 가기 단축키 \+에 정의 된 `Combos` 섹션입니다. 각 `Combo` 요소 IDE에서 드롭다운 목록 상자를 나타냅니다. 목록 상자 수도 아닐 수의 값에 따라 사용자가 쓸 수는 `type` 콤보의 특성입니다. 바로 가기 단축키 \+에 같은 요소가 있으며, 단추 동작 있으며 다음과 같은 추가 특성을 가질 수도 수 있습니다.  
  
-   A `defaultWidth` 픽셀 너비를 지정 하는 특성입니다.  
  
-   `idCommandList` 목록 상자에 표시 되는 항목을 포함 하는 목록을 지정 하는 특성입니다. 동일한 명령 목록 선언 해야 `GuidSymbol` 콤보 들어 있는 노드입니다.  
  
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
  
##### 비트맵  
 아이콘과 함께 표시 되는 명령을 포함 해야는 `Icon` 해당 GUID 및 ID를 사용 하 여 비트맵을 참조 하는 요소 각 비트맵으로 정의 되는 [비트맵 요소](../../extensibility/bitmap-element.md) 에 `Bitmaps` 섹션입니다. 에 대 한 특성에 필요한 유일한는 `Bitmap` 정의 `guid` 및 `href`, 소스 파일을 가리키는 합니다. 소스 파일은는 리소스 모음인 경우는 **usedList** 특성은도 스트립에서 사용 가능한 이미지를 나열 하려면 필요 합니다. 자세한 내용은 참조는 [비트맵 요소](../../extensibility/bitmap-element.md) 설명서입니다.  
  
### 부모로 지정  
 다음 규칙 항목 부모 다른 항목을 호출 하는 방법을 제어 합니다.  
  
|요소|명령 테이블의이 섹션에 정의 된|포함 될 수 있습니다 \(한 부모 또는 위치에 의해는 `CommandPlacements` 섹션 중 하나 또는 둘 모두\)|포함 될 수 있습니다 \(부모 라고 함\)|  
|--------|-----------------------|-------------------------------------------------------------------------|-----------------------------|  
|그룹화|[Groups 요소](../../extensibility/groups-element.md), IDE, 다른 Vspackage|메뉴에서 그룹을 항목 자체|메뉴, 그룹 및 명령|  
|메뉴|[메뉴 요소](../../extensibility/menus-element.md), IDE, 다른 Vspackage|1로 *n* 그룹|0 ~ *n* 그룹|  
|Toolbar|[메뉴 요소](../../extensibility/menus-element.md), IDE, 다른 Vspackage|항목 자체|0 ~ *n* 그룹|  
|메뉴 항목|[단추 요소](../../extensibility/buttons-element.md), IDE, 다른 Vspackage|1로 *n* 자체 항목을 그룹화|\-0 ~ *n* 그룹|  
|단추|[단추 요소](../../extensibility/buttons-element.md), IDE, 다른 Vspackage|1로 *n* 자체 항목을 그룹화||  
|콤보|[바로 가기 단축키 \+ 요소](../../extensibility/combos-element.md), IDE, 다른 Vspackage|1로 *n* 자체 항목을 그룹화||  
  
### 메뉴, 명령 및 그룹 배치  
 메뉴, 그룹 또는 명령 IDE에서 둘 이상의 위치에 나타날 수 있습니다. 여러 위치에 표시할 항목을 추가 해야 하는 `CommandPlacements` 섹션으로 [CommandPlacement 요소](../../extensibility/commandplacement-element.md)합니다. 모든 메뉴, 그룹 또는 명령 명령 배치도 추가할 수 있습니다. 그러나 도구 모음 상황에 맞는 여러 위치에 나타날 수 없습니다 때문에이 방식으로 배치할 수 없습니다.  
  
 명령 배치에 대 한 `guid`, `id`, 및 `priority` 특성입니다. GUID 및 ID에 배치 되는 항목의 일치 해야 합니다.`priority` 특성의 다른 항목을 관련 하 여 항목 배치를 제어 합니다. IDE에 동일한 우선 순위를 가진 항목 두 개 이상의 병합 하는 경우에 IDE는 빌드될 때마다 패키지 리소스 동일한 순서로 읽기는 보장 하지 않으므로 해당 배치 정의 되지 않습니다.  
  
 메뉴 또는 그룹을 여러 위치에 나타나면 해당 메뉴 또는 그룹의 모든 자식 인스턴스마다에 표시 됩니다.  
  
## 명령 표시 유형 및 컨텍스트  
 여러 Vspackage 설치 되 면 메뉴, 메뉴 항목 및 도구 모음 어렵게 IDE 복잡해 수 있습니다. 이 문제를 방지 하려면 개별 UI 요소의 표시 유형을 사용 하 여 제어할 수 있습니다 *표시 제약 조건은* 및 명령 플래그입니다.  
  
##### 표시 유형 제약 조건  
 표시 유형 제약 조건으로 설정 된 한 [VisibilityItem 요소](../../extensibility/visibilityitem-element.md) 에 `VisibilityConstraints` 섹션입니다. 표시 유형 제약 조건을 대상 항목이 표시 되는 특정 UI 컨텍스트를 정의 합니다. 메뉴 또는이 섹션에 포함 된 명령 정의 된 컨텍스트 중 하나가 상태인 경우에 표시 됩니다. 이 섹션에서는 메뉴 또는 명령을 참조 하지 않는 경우 기본적으로 표시는 항상 있습니다. 이 섹션 그룹에 적용 되지 않습니다.  
  
 `VisibilityItem` 요소는 다음과 같은 세 가지 특성을가 있어야 합니다:는 `guid` 및 `id` 대상 UI 요소 및 `context`합니다.`context` 특성 시기를 지정 된 대상 항목을 볼 수는 값으로 올바른 UI 컨텍스트를 사용 합니다. Visual Studio에 대 한 UI 컨텍스트 상수는의 멤버는 <xref:Microsoft.VisualStudio.VSConstants> 클래스입니다. 모든 `VisibilityItem` 요소는 하나의 컨텍스트 값을 사용할 수 있습니다. 두 번째 컨텍스트를 적용 하려면 하나 더 만듭니다 `VisibilityItem` 다음 예와에서 같이 동일한 항목을 가리키는 요소가 있습니다.  
  
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
  
##### 명령 플래그  
 다음 명령은 플래그 메뉴와 명령을 적용할 때의 표시 유형을 달라질 수 있습니다.  
  
 AlwaysCreate  
 메뉴 그룹 또는 단추 없는 경우에 만들어집니다.  
  
 유효 기간: `Menu`  
  
 CommandWellOnly  
 이 플래그를 적용이 최상위 메뉴에는 명령이 표시 되지 않습니다 추가 셸 사용자 지정에 사용할 수 있게 하려는 경우 예를 들어 키에 바인딩. 열어 이러한 명령을 사용자 VSPackage를 설치한 후 사용자 지정할 수는 **옵션** 다음 아래 명령 배치를 편집 하 고 대화 상자는 **키보드 환경** 범주입니다. 바로 가기 메뉴, 도구 모음, 메뉴 컨트롤러 또는 하위 메뉴에서 배치 영향을 주지 않습니다.  
  
 에 대 한 유효한: `Button`, `Combo`  
  
 DefaultDisabled  
 기본적으로 명령이 비활성화 되어 있는 명령을 구현 하는 VSPackage가 로드 되지 않거나 QueryStatus 메서드가 호출 되지 않았습니다.  
  
 에 대 한 유효한: `Button`, `Combo`  
  
 DefaultInvisible  
 기본적으로이 명령은 표시 되지 않습니다 명령을 구현 하는 VSPackage가 로드 되지 않거나 QueryStatus 메서드가 호출 되지 않았습니다.  
  
 함께 사용할는 `DynamicVisibility` 플래그입니다.  
  
 에 대 한 유효한: `Button`, `Combo`, `Menu`  
  
 DynamicVisibility  
 QueryStatus 메서드 또는 컨텍스트에 포함 된 GUID 사용 하 여 명령의 표시 여부를 변경할 수는 `VisibilityConstraints` 섹션입니다.  
  
 도구 모음에 없는 메뉴에 표시 되는 명령에 적용 됩니다. 최상위 도구 모음 항목 비활성화 수는 있지만 OLECMDF\_INVISIBLE 플래그 QueryStatus 메서드에서 반환 되 면 숨길 수 없습니다.  
  
 메뉴에서이 플래그도 것 해야 자동으로 숨김을 나타냅니다 해당 멤버를 숨기면 됩니다. 최상위 메뉴에 이미이 문제 때문에이 플래그는 일반적으로 하위 메뉴에 할당 됩니다.  
  
 함께 사용할는 `DefaultInvisible` 플래그입니다.  
  
 에 대 한 유효한: `Button`, `Combo`, `Menu`  
  
 NoShowOnMenuController  
 이 플래그가 있는 명령 메뉴 컨트롤러에 커서가, 명령 드롭 다운 목록에 나타나지 않습니다.  
  
 유효 기간: `Button`  
  
 명령 플래그에 대 한 자세한 내용은 참조는 [명령 플래그 요소](../../extensibility/command-flag-element.md) 설명서입니다.  
  
##### 일반 요구 사항  
 표시 되 고 사용할 수 있습니다 명령 다음과 같은 일련의 테스트를 통과 해야 합니다.  
  
-   명령은 올바르게 배치 됩니다.  
  
-   `DefaultInvisible` 플래그가 설정 되지 않았습니다.  
  
-   부모 메뉴 또는 도구 모음에 표시 됩니다.  
  
-   명령에서 컨텍스트 항목으로 인해 보이지 않는 하지 않은 [VisibilityConstraints 요소](../../extensibility/visibilityconstraints-element.md) 섹션입니다.  
  
-   VSPackage 코드를 구현 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스를 표시 하며 명령을 수 있습니다. 없음 인터페이스 코드 것을 차단 하 고 그에 대응 하 여 합니다.  
  
-   에 설명 된 절차에 따라이 되기 명령을 클릭할 때 [라우팅 알고리즘](../../extensibility/internals/command-routing-algorithm.md)합니다.  
  
## 미리 정의 된 명령 호출  
 [UsedCommands 요소](../../extensibility/usedcommands-element.md) 명령에 액세스할 때 다른 Vspackage 또는 IDE에 의해 제공 되는 VSPackages를 수 있습니다. 이 위해 만들기는 [UsedCommand 요소](../../extensibility/usedcommand-element.md) 에 GUID 및 사용 하 여 명령의 ID입니다. 이렇게 하면 Visual Studio에서 명령을 로드 되는 현재 Visual Studio 구성에 속하지 않은 경우에 합니다. 자세한 내용은 [UsedCommand 요소](../../extensibility/usedcommand-element.md)을 참조하세요.  
  
## 인터페이스 요소 모양  
 선택 하 고 명령 요소 위치 지정에 대 한 고려 사항은 다음과 같습니다.  
  
-   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 배치에 따라 다르게 표시 되는 여러 UI 요소를 제공 합니다.  
  
-   사용 하 여 정의 하는 UI 요소는 `DefaultInvisible` VSPackage 구현 하 여 표시 하지 않은 플래그 IDE에서 표시 되지 것입니다는 <xref:EnvDTE.IDTCommandTarget.QueryStatus%2A> 메서드를 특정 UI 컨텍스트와 관련 된는 `VisibilityConstraints` 섹션입니다.  
  
-   성공적으로 배치 된 명령에도 표시 될 수 있습니다. 이 IDE는 자동으로 숨기 거 나 VSPackage \(또는 되지 않은\) 인터페이스에 따라 몇 가지 명령이 표시 하기 때문에 구현 됩니다. 예를 들어 VSPackage의 구현의 일부 원인을 빌드 관련 메뉴 항목을 자동으로 표시 될 인터페이스를 빌드합니다.  
  
-   적용 된 `CommandWellOnly` UI 요소의 정의에서 플래그 의미 명령을 사용자 지정을 통해만 추가할 수 있습니다.  
  
-   IDE가 디자인 뷰에서 대화 상자를 표시 하는 경우에 명령 예를 들어 특정 UI 컨텍스트에만 사용할 수 있습니다.  
  
-   IDE에 표시할 특정 UI 요소를 발생 하려면 하나 이상의 인터페이스를 구현 하거나 코드를 작성 해야 합니다.  
  
## 참고 항목  
 [확장 메뉴 및 명령](../../extensibility/extending-menus-and-commands.md)