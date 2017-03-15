---
title: "제작 합니다. Vsct 파일 | Microsoft Docs"
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
  - "VSCT 파일을 수동 작성"
ms.assetid: e9f715dc-12b7-439b-bdf3-f3dc75e62f1c
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 제작 합니다. Vsct 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 문서에는 Visual Studio 통합된 개발 환경 \(IDE\)에 메뉴 항목, 도구 모음 및 기타 사용자 인터페이스 \(UI\) 요소를 추가 하려면.vsct 파일을 작성 하는 방법을 보여 줍니다. Visual Studio 패키지 \(VSPackage\)가 없는 이미.vsct 파일에 UI 요소를 추가 하는 경우 다음이 단계를 사용 합니다.  
  
 새 프로젝트에 대 한 선택 항목에 따라 이미 메뉴 명령, 도구 창 또는 사용자 지정 편집기에 대 한 필수 요소가 있는.vsct 파일을 생성 하기 때문에 Visual Studio 패키지 템플릿을 사용 하는 것이 좋습니다. VSPackage의 요구 사항에 맞게이.vsct 파일을 수정할 수 있습니다. .Vsct 파일을 수정 하는 방법에 대 한 자세한 내용은 예제를 참조 [확장 메뉴 및 명령](../../extensibility/extending-menus-and-commands.md)합니다.  
  
## 파일 작성  
 이러한 단계에서.vsct 파일 작성: 파일 및 리소스에 대 한 구조를 만들고, UI 요소를 선언, IDE에서 UI 요소를 배치 및 모든 특수 동작을 추가 합니다.  
  
### 파일 구조  
 .Vsct 파일의 기본 구조는는 [CommandTable](../../extensibility/commandtable-element.md) 루트 요소를 포함 하는 [명령을](../../extensibility/commands-element.md) 요소와 [기호](../../extensibility/symbols-element.md) 요소입니다.  
  
##### 파일 구조를 만들려면  
  
1.  단계를 수행 하 여.vsct 파일을 프로젝트에 추가 [방법: 만들기는 합니다. Vsct 파일](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)합니다.  
  
2.  필요한 네임 스페이스에 추가 `CommandTable` 요소를 다음 예와에서 같이 합니다.  
  
    ```xml  
    <CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable"   
    	xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
    ```  
  
3.  에 `CommandTable` 요소를 추가 `Commands` 요소를 호스트 하는 모든 사용자 지정 메뉴, 도구 모음, 명령 그룹 및 명령. 사용자 지정 UI 요소 로드할 수 있도록는 `Commands` 요소의 해야 해당 `Package` 특성 패키지의 이름으로 설정 합니다.  
  
     이후에 `Commands` 요소를 추가 `Symbols` 요소 이름과 패키지를 실행 하는 것에 대 한 Guid를 정의 하 고 UI 요소에 대 한 명령 Id입니다.  
  
### Visual Studio 리소스를 포함 하 여  
 사용 하 여 [Extern](../../extensibility/extern-element.md) Visual Studio 명령 및 IDE에서 UI 요소를 배치 하는 데 필요한 메뉴를 정의 하는 파일에 액세스 하는 요소입니다. 패키지 외부에 정의 된 명령을 사용 하는 경우 사용 된 [UsedCommands](../../extensibility/usedcommands-element.md) 요소를 Visual Studio 사용자에 게 알립니다.  
  
##### Visual Studio 리소스를 포함 하려면  
  
1.  맨 위에 있는 `CommandTable` 요소를 하나 추가 `Extern` 각 외부 파일 참조 하 고 설정에 대 한 요소는 `href` 특성을 파일의 이름입니다. Visual Studio 리소스에 액세스 하려면 다음 헤더 파일을 참조할 수 있습니다.  
  
    -   Stdidcmd.h, Visual Studio에 의해 노출 되는 모든 명령에 대 한 Id를 정의 합니다.  
  
    -   Vsshlids.h, Visual Studio 메뉴에 대 한 명령 Id를 포함 합니다.  
  
2.  패키지는 Visual Studio에서 또는 다른 패키지에 의해 정의 된 모든 명령을 호출 하는 경우 추가 `UsedCommands` 요소는 `Commands` 요소입니다. 이 요소를 채울는 [UsedCommand](../../extensibility/usedcommand-element.md) 즉 패키지의 일부가 아닌 호출 하면 각 명령에 대 한 요소입니다. 설정는 `guid` 및 `id` 의 특성은 `UsedCommand` 요소를 호출 하 여 명령의 GUID 및 ID 값입니다. Guid 및 Id의 Visual Studio 명령을 찾는 방법에 대 한 자세한 내용은 참조 [Guid 및 Visual Studio 명령 Id](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)합니다. 명령을 다른 패키지에서를 호출 하려면 GUID 및 해당 패키지에 대 한.vsct 파일에 정의 된 대로 명령의 ID를 사용 합니다.  
  
### UI 요소를 선언합니다.  
 모든 새로운 UI 요소에 선언 된 `Symbols` .vsct 파일의 섹션입니다.  
  
##### UI 요소를 선언 하려면  
  
1.  에 `Symbols` 요소를 추가 하는 세 개의 [GuidSymbol](../../extensibility/guidsymbol-element.md) 요소. 각 `GuidSymbol` 요소에는 `name` 특성 및 `value` 특성입니다. 설정의 `name` 특성 요소의 용도 반영 합니다.`value` 특성은 GUID입니다. \(에서 GUID를 생성 하는 **도구** 메뉴를 클릭 하 여 **GUID 만들기**, 선택한 다음 **레지스트리 형식**.\)  
  
     첫 번째 `GuidSymbol` 요소 패키지를 나타내며 일반적으로 자식이 없습니다. 두 번째 `GuidSymbol` 요소 나타냅니다 명령으로 설정 하 고 모든 메뉴, 그룹 및 명령을 정의 하는 기호 포함 됩니다. 세 번째 `GuidSymbol` 요소 이미지 저장소를 나타내며 사용자 명령에 대 한 아이콘을 모두에 대 한 기호를 포함 합니다. 아이콘을 사용 하는 명령이 없는 경우에 세 번째를 생략할 수 있습니다 `GuidSymbol` 요소입니다.  
  
2.  에 `GuidSymbol` 명령 집합을 나타내는 요소 하나 이상 추가 [IDSymbol](../../extensibility/idsymbol-element.md) 요소입니다. 이러한 각 메뉴, 도구 모음, 그룹 또는 UI에 추가 하는 명령을 나타냅니다.  
  
     각 `IDSymbol` 요소를 설정의 `name` 특성을 사용 하는 해당 메뉴, 그룹 또는 명령에서 참조 되며 다음 설정 이름은 `value` 요소 명령 id를 나타내는 16 진수 숫자입니다. 두 `IDSymbol` 동일한 부모를 가진 요소에 동일한 값을 가질 수 있습니다.  
  
3.  UI 요소 중 하나가 필요한 경우 아이콘, 추가 `IDSymbol` 에 각 아이콘에 대 한 요소는 `GuidSymbol` 이미지 저장소를 나타내는 요소입니다.  
  
### IDE에 UI 요소를 삽입합니다.  
 [메뉴](../../extensibility/menus-element.md) 요소인 [그룹](../../extensibility/groups-element.md) 요소 및 [단추](../../extensibility/buttons-element.md) 모든 메뉴, 그룹 및 패키지에 정의 된 명령에 대 한 정의 포함 하는 요소입니다. 이러한 메뉴, 그룹 및 명령을 사용 하 여 IDE에서 배치를 [부모](../../extensibility/parent-element.md) 요소를 사용 하 여 또는 UI 요소 정의의 일부인는 [CommandPlacement](../../extensibility/commandplacement-element.md) 다른 위치에 있는 요소를 정의 합니다.  
  
 각 `Menu`, `Group`, 및 `Button` 요소에는 `guid` 특성 및 `id` 특성입니다. 항상 설정는 `guid` 특성의 이름과 일치 하도록는 `GuidSymbol` 를 설정 하 고 설정 하는 명령을 나타내는 요소는 `id` 특성의 이름으로는 `IDSymbol` 메뉴, 그룹 또는 명령을 나타내는 요소는 `Symbols` 섹션입니다.  
  
##### UI 요소를 정의 하려면  
  
1.  새 메뉴, 하위 메뉴, 바로 가기 메뉴 또는 도구 모음을 정의 하는 경우 추가 `Menus` 요소는 `Commands` 요소입니다. 그런 다음, 만들 각 메뉴에 대 한 추가 [메뉴](../../extensibility/menu-element.md) 요소는 `Menus` 요소입니다.  
  
     설정의 `guid` 및 `id` 의 특성은 `Menu` 요소를 제거한 다음 설정의 `type` 원하는 메뉴의 종류를 특성입니다. 설정할 수도 있습니다는 `priority` 부모 그룹에는 메뉴의 상대 위치를 설정 하는 특성입니다.  
  
    > [!NOTE]
    >  `priority` 특성 도구 모음과 상황에 맞는 메뉴에 적용 되지 않습니다.  
  
2.  Visual Studio IDE에서 모든 명령은 메뉴 및 도구 모음의 직접 자식 하는 명령 그룹으로 호스팅해야 합니다. 를 추가 하는 새 메뉴나 도구 모음을 IDE 이러한 새 명령 그룹을 포함 해야 합니다. 또한 명령을 시각적으로 그룹화 할 수 있도록 기존 메뉴 및 도구 모음 명령 그룹을 추가할 수 있습니다.  
  
     새 명령 그룹을 추가 하면 먼저 만들어야는 `Groups` 요소를 추가 하 고는 [그룹](../../extensibility/group-element.md) 각 명령 그룹에 대 한 요소입니다.  
  
     설정의 `guid` 및 `id` 각 특성 `Group` 요소를 제거한 다음 설정의 `priority` 부모 메뉴에 있는 그룹의 상대 위치를 설정 하는 특성입니다. 자세한 내용은 [단추의 다시 사용할 수 있는 그룹 만들기](../../extensibility/creating-reusable-groups-of-buttons.md)을 참조하십시오.  
  
3.  새로운 명령이 IDE에를 추가 하는 경우 추가 `Buttons` 요소는 `Commands` 요소입니다. 그런 다음 각 명령에 대 한 추가 [단추](../../extensibility/button-element.md) 요소는 `Buttons` 요소입니다.  
  
    1.  설정는 `guid` 및 `id` 각 특성 `Button` 요소를 제거한 다음 설정의 `type` 특성을 원하는 단추의 종류입니다. 설정할 수도 있습니다는 `priority` 특성을 상위 그룹에 있는 명령의 상대 위치를 설정 합니다.  
  
        > [!NOTE]
        >  사용 하 여 `type="button"` 표준 메뉴 명령 및 도구 모음에 단추에 대 한 합니다.  
  
    2.  에 `Button` 요소를 추가 [문자열](../../extensibility/strings-element.md) 요소를 포함 하는 [를 로드 합니다](../../extensibility/buttontext-element.md) 요소와 [CommandName](../../extensibility/commandname-element.md) 요소입니다.`ButtonText` 요소는 메뉴 항목 또는 도구 모음 단추에 대 한 도구 설명에 대 한 텍스트 레이블을 제공 합니다.`CommandName` 요소 잘 명령에서 사용 하 여 명령의 이름을 제공 합니다.  
  
    3.  명령 아이콘, 있는 경우 만들기는 [아이콘](../../extensibility/icon-element.md) 요소에는 `Button` 요소, 해당 `guid` 및 `id` 특성을 `Bitmap` 아이콘에 대 한 요소입니다.  
  
        > [!NOTE]
        >  도구 모음 단추에 아이콘 있어야 합니다.  
  
     자세한 내용은 [MenuCommand 및 OleMenuCommand](../../misc/menucommands-vs-olemenucommands.md)을 참조하십시오.  
  
4.  아이콘을 필요한 명령을 경우 추가 [비트맵](../../extensibility/bitmaps-element.md) 요소는 `Commands` 요소입니다. 그런 다음 각 아이콘에 대 한 추가 [비트맵](../../extensibility/bitmap-element.md) 요소는 `Bitmaps` 요소입니다. 이것은 비트맵 리소스의 위치를 지정할 수 있습니다. 자세한 내용은 [메뉴 명령에 아이콘 추가](../../extensibility/adding-icons-to-menu-commands.md)을 참조하십시오.  
  
 대부분의 메뉴, 그룹 및 명령을 올바르게 배치할 부모 지정 구조에 사용할 수 있습니다. 매우 큰 명령 집합에 대 한 메뉴, 그룹 또는 명령을 여러 곳에 나타나야 하는 경우 명령 배치를 지정 하는 것이 좋습니다.  
  
##### IDE에서 UI 요소를 배치 하는 부모 의존 하 여  
  
1.  일반적인 부모 지정에 대 한 만들기는 `Parent` 각 요소 `Menu`, `Group`, 및 `Command` 패키지에 정의 된 요소입니다.  
  
     대상은 `Parent` 요소는 메뉴 또는 메뉴에 있는 그룹, 그룹 또는 명령입니다.  
  
    1.  설정의 `guid` 특성의 이름으로는 `GuidSymbol` 명령 집합을 정의 하는 요소입니다. 해당 대화 상자가 패키지의 일부가 아닌 경우에 대상 요소는 해당.vsct 파일에 정의 된 대로 해당 명령 집합에 대 한 guid를 사용 합니다.  
  
    2.  설정의 `id` 일치 시킬 특성은 `id` 대상 메뉴 또는 그룹의 특성입니다. 메뉴 및 Visual Studio에 의해 노출 되는 그룹의 목록을 보려면 [Guid 및 Id의 Visual Studio 메뉴](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) 또는 [Guid 및 Visual Studio 도구 모음의 Id](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)합니다.  
  
 IDE에 배치 하는 UI 요소 수가 많은 경우 또는 여러 위치에 나타나야 하는 요소가 있는 경우 정의 배치에 대는 [CommandPlacements](../../extensibility/commandplacements-element.md) 다음 단계에 표시 된 것과 같이 요소입니다.  
  
##### 사용 하 여 명령 배치 IDE에서 UI 요소를 배치 합니다.  
  
1.  이후에 `Commands` 요소를 추가 `CommandPlacements` 요소입니다.  
  
2.  에 `CommandPlacements` 요소를 추가 `CommandPlacement` 각 메뉴, 그룹 또는 배치 하는 명령에 대 한 요소입니다.  
  
     각 `CommandPlacement` 요소 또는 `Parent` 요소 하나의 IDE 위치에 하나의 메뉴, 그룹 또는 명령을 붙여 넣습니다. UI 요소는 하나의 부모를 하나만 사용할 수 있지만 여러 명령 배치 가질 수 있습니다. 여러 위치에서 UI 요소를 배치 하려면 추가 `CommandPlacement` 각 위치에 대 한 요소입니다.  
  
3.  설정의 `guid` 및 `id` 각 특성 `CommandPlacement` 호스팅 메뉴 또는 그룹에서와 마찬가지로 요소에 대 한 것을 `Parent` 요소입니다. 설정할 수도 있습니다는 `priority` UI 요소의 상대 위치를 설정 하는 특성입니다.  
  
 부모 지정 하 여 배치 및 명령 배치를 혼합할 수 있습니다. 그러나 매우 큰 명령 집합에 대 한 명령 배치만을 사용 하는 것이 좋습니다.  
  
### 특별 한 동작 추가  
 사용할 수 있습니다 [CommandFlag](../../extensibility/command-flag-element.md) 요소 모양 및 표시 유형을 변경 하기, 예를 들어 메뉴 및 메뉴 명령에의 동작을 수정할 수 있습니다. 명령을 사용 하 여 표시 되 면 달라질 수 있습니다 [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md), 를 사용 하 여 바로 가기 키를 추가 하거나 [키 바인딩](../../extensibility/keybindings-element.md)합니다. 특정 종류의 메뉴 및 명령을 이미 특수 기본 제공 되는 동작입니다.  
  
##### 특수 동작을 추가 하려면  
  
1.  UI 요소를 표시 하려면 예를 들어 특정 UI 컨텍스트에만 솔루션 로드 되 면 표시 유형 제약 조건을 사용 합니다.  
  
    1.  이후에 `Commands` 요소를 추가 `VisibilityConstraints` 요소입니다.  
  
    2.  제한 하려면 각 UI 항목에 대 한 추가 [VisibilityItem](../../extensibility/visibilityitem-element.md) 요소입니다.  
  
    3.  각각에 대해 `VisibilityItem` 요소를 설정는 `guid` 및 `id` 메뉴, 그룹, 또는 명령을 다음 설정에는 특성의 `context` 에 정의 된 대로 UI 컨텍스트 특성의 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> 클래스. 자세한 내용은 [VisibilityItem 요소](../../extensibility/visibilityitem-element.md)을 참조하세요.  
  
2.  코드에서 표시 유형 또는 UI 항목의 가용성을 설정 하려면 다음 명령 플래그 중 하나 이상을 사용 합니다.  
  
    -   DefaultDisabled  
  
    -   DefaultInvisible  
  
    -   DynamicItemStart  
  
    -   DynamicVisibility  
  
    -   NoShowOnMenuController  
  
    -   NotInTBList  
  
     자세한 내용은 [명령 플래그 요소](../../extensibility/command-flag-element.md)을 참조하세요.  
  
3.  요소 표시 되거나 표시 되는 동적으로 변경 방법을 변경 하려면 다음 명령 플래그 중 하나 이상을 사용 합니다.  
  
    -   AlwaysCreate  
  
    -   CommandWellOnly  
  
    -   DefaultDocked  
  
    -   DontCache  
  
    -   DynamicItemStart  
  
    -   FixMenuController  
  
    -   IconAndText  
  
    -   Pict  
  
    -   StretchHorizontally  
  
    -   TextMenuUseButton  
  
    -   TextChanges  
  
    -   TextOnly  
  
     자세한 내용은 [명령 플래그 요소](../../extensibility/command-flag-element.md)을 참조하십시오.  
  
4.  명령을 받을 때 요소가 어떻게 반응할지를 변경 하려면 다음 명령 플래그 중 하나 이상을 사용 합니다.  
  
    -   AllowParams  
  
    -   CaseSensitive  
  
    -   CommandWellOnly  
  
    -   필터 키  
  
    -   NoAutoComplete  
  
    -   NoButtonCustomize  
  
    -   NoKeyCustomize  
  
    -   NoToolbarClose  
  
    -   PostExec  
  
    -   RouteToDocs  
  
    -   TextIsAnchorCommand  
  
     자세한 내용은 [명령 플래그 요소](../../extensibility/command-flag-element.md)을 참조하세요.  
  
5.  메뉴 또는 메뉴에 있는 항목에 종속 메뉴 바로 가기 키를 연결 하려면 추가 앰퍼샌드 문자 \('& '\)에 `ButtonText` 메뉴 또는 메뉴 항목에 대 한 요소입니다. 앰퍼샌드 다음에 나오는 문자는 부모 메뉴를 열면 현재 바로 가기는.  
  
6.  명령 메뉴와 바로 가기 키를 연결 하려면 사용 하 여 [키 바인딩](../../extensibility/keybindings-element.md)합니다. 자세한 내용은 [키 바인딩 요소](../../extensibility/keybinding-element.md)을 참조하세요.  
  
7.  메뉴 텍스트를 지역화 하려면 사용 된 `LocCanonicalName` 요소입니다. 자세한 내용은 [문자열 요소](../../extensibility/strings-element.md)을 참조하세요.  
  
 메뉴 및 단추 유형도 특수 동작을 포함합니다. 다음 표에서 몇 가지 특수 한 메뉴 및 단추 종류를 설명합니다. 다른 형식에 대 한 참조는 `types` 특성에 대 한 설명 [Menu 요소](../../extensibility/menu-element.md), [Button 요소](../../extensibility/button-element.md), 및 [콤보 요소](../../extensibility/combo-element.md)합니다.  
  
 콤보 상자  
 콤보 상자에 도구 모음에 사용할 수 있는 드롭다운 목록입니다. 콤보 상자에는 UI를 추가 하려면 만들기를 [바로 가기 단축키 \+](../../extensibility/combos-element.md) 요소에는 `Commands` 요소입니다. 그런 다음에 추가 `Combos` 요소는 `Combo` 추가할 각 콤보 상자에 대 한 요소입니다.`Combo` 요소에는 동일한 특성 및 자식으로 `Button` 요소 또한 `DefaultWidth` 및 `idCommandList` 특성입니다.`DefaultWidth` 너비 \(픽셀\)를 설정 하는 특성 및 `idCommandList` 특성 콤보 상자를 채우는 데 사용 되는 명령 ID를 가리킵니다. 자세한 내용은 참조는 `Combo` 요소 설명서입니다.  
  
 MenuController  
 메뉴 컨트롤러인 옆쪽 화살표가 있는 단추입니다. 화살표를 클릭 하면 목록을 엽니다. Ui 메뉴 컨트롤러를 추가 하려면 만듭니다는 `Menu` 요소 집합과 해당 `type` 특성을 **MenuController** 또는 **MenuControllerLatched**, 원하는 동작에 따라 합니다. 메뉴 컨트롤러를 채우려면의 부모로 설정는 `Group` 요소입니다. 메뉴 컨트롤러는 해당 그룹의 모든 자식 드롭다운 목록에 표시 됩니다.  
  
## 참고 항목  
 [확장 메뉴 및 명령](../../extensibility/extending-menus-and-commands.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)