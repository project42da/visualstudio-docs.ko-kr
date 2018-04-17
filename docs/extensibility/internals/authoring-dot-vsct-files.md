---
title: 제작 합니다. Vsct 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, manual authoring
ms.assetid: e9f715dc-12b7-439b-bdf3-f3dc75e62f1c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 65fc62d5685ca7c81b3ebb7f524db3cdbebe72c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="authoring-vsct-files"></a>제작 합니다. Vsct 파일
이 문서에는 Visual Studio 통합된 개발 환경 (IDE)에 메뉴 항목, 도구 모음 및 기타 사용자 인터페이스 (UI) 요소를 추가 하려면.vsct 파일을 작성 하는 방법을 보여 줍니다. 이미.vsct 파일을 맺지 않은 Visual Studio 패키지 (VSPackage)에 UI 요소를 추가 하는 경우 다음이 단계를 사용 합니다.  
  
 새 프로젝트에 대 한 선택 항목에 따라 이미 메뉴 명령, 도구 창 또는 사용자 지정 편집기에 대 한 필수 요소가 있는.vsct 파일을 생성 하기 때문에 Visual Studio 패키지 템플릿을 사용 하는 것이 좋습니다. VSPackage의 요구 사항에 맞게이.vsct 파일을 수정할 수 있습니다. .Vsct 파일을 수정 하는 방법에 대 한 자세한 내용은 참조의 예제에서는 [확장 메뉴 및 명령을](../../extensibility/extending-menus-and-commands.md)합니다.  
  
## <a name="authoring-the-file"></a>파일 작성  
 이러한 단계에서.vsct 파일을 작성: 파일 및 리소스에 대 한 구조 만들기, UI 요소를 선언, IDE에서 UI 요소를 삽입할 및 모든 특수 동작을 추가 합니다.  
  
### <a name="file-structure"></a>파일 구조  
 .Vsct 파일의 기본 구조는 한 [CommandTable](../../extensibility/commandtable-element.md) 루트 요소를 포함 하는 [명령을](../../extensibility/commands-element.md) 요소와 [기호](../../extensibility/symbols-element.md) 요소입니다.  
  
##### <a name="to-create-the-file-structure"></a>파일 구조를 만들려면  
  
1.  단계를 수행 하 여.vsct 파일을 프로젝트에 추가 [하는 방법: 만들기는 합니다. Vsct 파일](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)합니다.  
  
2.  필요한 네임 스페이스에 추가 `CommandTable` 요소를 다음 예제와 같이 합니다.  
  
    ```xml  
    <CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable"   
        xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
    ```  
  
3.  에 `CommandTable` 요소를 추가 `Commands` 요소 호스트의 모든 사용자 지정 메뉴, 도구 모음, 명령 그룹 및 명령입니다. 사용자 지정 UI 요소를 로드할 수 있도록는 `Commands` 요소 있어야 해당 `Package` 특성 패키지의 이름으로 설정 합니다.  
  
     후의 `Commands` 요소를 추가 `Symbols` 요소 이름과 패키지에 대 한 Guid를 정의 하 고 UI 요소에 대 한 명령 Id입니다.  
  
### <a name="including-visual-studio-resources"></a>Visual Studio 리소스를 포함 하 여  
 사용 하 여는 [Extern](../../extensibility/extern-element.md) Visual Studio 명령 및 IDE에서 UI 요소를 배치 하는 데 필요한 메뉴를 정의 하는 파일에 액세스 하는 요소입니다. 패키지 외부에서 정의 하는 명령을 사용 하는 경우 사용 하 여는 [UsedCommands](../../extensibility/usedcommands-element.md) 요소를 Visual Studio에 게 알립니다.  
  
##### <a name="to-include-visual-studio-resources"></a>Visual Studio 리소스를 포함 하려면  
  
1.  맨 위에 있는 `CommandTable` 요소를 하나 추가 `Extern` 각 외부 파일 참조 하 고 설정에 대 한 요소는 `href` 특성을 파일의 이름입니다. Visual Studio 리소스에 액세스 하려면 다음 헤더 파일을 참조할 수 있습니다.  
  
    -   Stdidcmd.h, Visual Studio에서 노출 하는 모든 명령에 대 한 Id를 정의 합니다.  
  
    -   Vsshlids.h, Visual Studio 메뉴에 대 한 명령 Id를 포함 합니다.  
  
2.  Visual Studio에서 또는 다른 패키지에 의해 정의 된 모든 명령을 호출 하는 패키지를 하는 경우 추가 `UsedCommands` 요소 뒤의 `Commands` 요소입니다. 이 요소와 채우기는 [UsedCommand](../../extensibility/usedcommand-element.md) 패키지의 일부가 아닌 호출 즉 각 명령에 대 한 요소입니다. 설정의 `guid` 및 `id` 의 특성은 `UsedCommand` 요소를 호출 하는 명령의 GUID 및 ID 값입니다. Guid 및 Id의 Visual Studio 명령을 확인 하는 방법에 대 한 자세한 내용은 참조 [Guid 및 Visual Studio 명령 Id](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)합니다. 명령에서 다른 패키지를 호출 하려면 GUID 및 이러한 패키지에 대 한.vsct 파일에 정의 된 대로 명령의 ID를 사용 합니다.  
  
### <a name="declaring-ui-elements"></a>UI 요소를 선언합니다.  
 모든 새로운 UI 요소에 선언 된 `Symbols` .vsct 파일의 섹션입니다.  
  
##### <a name="to-declare-ui-elements"></a>UI 요소를 선언 하려면  
  
1.  에 `Symbols` 요소를 3 개의 추가 [GuidSymbol](../../extensibility/guidsymbol-element.md) 요소입니다. 각 `GuidSymbol` 요소에는 `name` 특성 및 `value` 특성입니다. 설정 된 `name` 특성 요소의 용도 반영 합니다. `value` 특성은 GUID를 사용 합니다. (에 GUID를 생성 하는 **도구** 메뉴에서 클릭 **GUID 만들기**를 선택한 후 **레지스트리 형식**.)  
  
     첫 번째 `GuidSymbol` 요소 패키지를 나타내며 일반적으로 자식이 없습니다. 두 번째 `GuidSymbol` 명령 집합과 모든 메뉴, 그룹 및 명령을 정의 하는 기호는 포함 될 요소를 나타냅니다. 세 번째 `GuidSymbol` 요소 이미지 저장소를 나타내고의 모든 사용자 명령에 대 한 아이콘에 대 한 기호를 포함 합니다. 세 번째 아이콘을 사용 하는 명령이 없거나를 설정한 경우 생략할 수 있습니다 `GuidSymbol` 요소입니다.  
  
2.  에 `GuidSymbol` 명령 집합을 나타내는 요소는 하나 이상 추가 [IDSymbol](../../extensibility/idsymbol-element.md) 요소입니다. 이러한 각 메뉴, 도구 모음, 그룹 또는 UI에 추가 하는 명령을 나타냅니다.  
  
     각각에 대해 `IDSymbol` 요소를 설정의 `name` 특성 이름에 해당 하는 메뉴, 그룹 또는 명령 참조는 데 사용 되며 다음 설정으로 `value` 요소 명령 id를 나타내는 16 진수 숫자입니다. 두 `IDSymbol` 같은 부모를 가진 요소에 동일한 값을 가질 수 있습니다.  
  
3.  추가 아이콘을 요구 하는 UI 요소 중 하나는 `IDSymbol` 에 각 아이콘에 대 한 요소는 `GuidSymbol` 이미지 저장소를 나타내는 요소입니다.  
  
### <a name="putting-ui-elements-in-the-ide"></a>IDE에서 UI 요소를 배치합니다.  
 [메뉴](../../extensibility/menus-element.md) 요소 [그룹](../../extensibility/groups-element.md) 요소 및 [단추](../../extensibility/buttons-element.md) 요소는 모든 메뉴, 그룹 및 패키지에 정의 된 명령에 대 한 정의 포함 합니다. 사용 하 여 IDE에서 이러한 메뉴, 그룹 및 명령 배치를 [부모](../../extensibility/parent-element.md) 요소를 사용 하 여 또는 UI 요소 정의의 일부인는 [CommandPlacement](../../extensibility/commandplacement-element.md) 다른 위치에 요소를 정의 합니다.  
  
 각 `Menu`, `Group`, 및 `Button` 요소에는 `guid` 특성 및 `id` 특성입니다. 항상 설정는 `guid` 특성의 이름과 일치 하도록는 `GuidSymbol` 명령을 나타내는 요소를 설정 하 고 설정의 `id` 특성의 이름으로는 `IDSymbol` 메뉴, 그룹 또는 명령에는 나타내는요소`Symbols`섹션.  
  
##### <a name="to-define-ui-elements"></a>UI 요소를 정의 하려면  
  
1.  새 메뉴, 하위 메뉴, 바로 가기 메뉴 또는 도구 모음을 정의 하는 경우 추가 `Menus` 요소는 `Commands` 요소입니다. 그런 다음 만들려는 각 메뉴에 대 한 추가 [메뉴](../../extensibility/menu-element.md) 요소를는 `Menus` 요소입니다.  
  
     설정의 `guid` 및 `id` 의 특성은 `Menu` 요소를 제거한 다음 설정의 `type` 특성을 원하는 메뉴의 종류입니다. 설정할 수도 있습니다는 `priority` 특성을 상위 그룹의 메뉴의 상대적 위치를 설정 합니다.  
  
    > [!NOTE]
    >  `priority` 특성 도구 모음과 상황에 맞는 메뉴에 적용 되지 않습니다.  
  
2.  Visual Studio IDE에서 모든 명령은 명령 그룹 메뉴 및 도구 모음의 직계 자식은 의해 호스팅되어야 합니다. 를 추가 하는 새 메뉴 또는 도구 모음 IDE에 이러한 새 명령 그룹을 포함 해야 합니다. 명령을 시각적으로 그룹화 할 수 있도록 명령 그룹 기존 메뉴 및 도구 모음에 추가할 수도 있습니다.  
  
     새 명령 그룹을 추가 하는 경우 먼저 만들어야 합니다는 `Groups` 요소를 추가 하 고는 [그룹](../../extensibility/group-element.md) 각 명령 그룹에 대 한 요소입니다.  
  
     설정의 `guid` 및 `id` 각 특성 `Group` 요소를 제거한 다음 설정의 `priority` 부모 메뉴에서 그룹의 상대 위치를 설정 하는 특성입니다. 자세한 내용은 참조 [단추의 다시 사용할 수 있는 그룹 만들기](../../extensibility/creating-reusable-groups-of-buttons.md)합니다.  
  
3.  IDE에 새 명령을 추가 하는 경우 추가 `Buttons` 요소는 `Commands` 요소입니다. 그런 다음 각 명령에 대 한 추가 [단추](../../extensibility/button-element.md) 요소는 `Buttons` 요소입니다.  
  
    1.  설정의 `guid` 및 `id` 각 특성 `Button` 요소를 제거한 다음 설정의 `type` 특성을 원하는 단추 종류입니다. 설정할 수도 있습니다는 `priority` 특성을 상위 그룹의 명령의 상대 위치를 설정 합니다.  
  
        > [!NOTE]
        >  사용 하 여 `type="button"` 도구 모음에 표준 메뉴 명령 및 단추에 대 한 합니다.  
  
    2.  에 `Button` 요소를 추가 [문자열](../../extensibility/strings-element.md) 요소를 포함 하는 [ButtonText](../../extensibility/buttontext-element.md) 요소와 [CommandName](../../extensibility/commandname-element.md) 요소입니다. `ButtonText` 요소 메뉴 항목 또는 도구 모음 단추에 대 한 도구 설명에 대 한 텍스트 레이블을 제공 합니다. `CommandName` 요소 명령에서 명령에도 사용의 이름을 제공 합니다.  
  
    3.  명령 아이콘으로 사용할 예정 만듭니다는 [아이콘](../../extensibility/icon-element.md) 요소에는 `Button` 요소, 해당 `guid` 및 `id` 특성을 `Bitmap` 아이콘에 대 한 요소입니다.  
  
        > [!NOTE]
        >  도구 모음 단추에는 아이콘이 있어야 합니다.  
  
     자세한 내용은 참조 [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md)합니다.  
  
4.  추가 아이콘을 요구 하면 명령 중 하나는 [비트맵](../../extensibility/bitmaps-element.md) 요소를는 `Commands` 요소입니다. 그런 다음 각 아이콘에 대 한 추가 [비트맵](../../extensibility/bitmap-element.md) 요소는 `Bitmaps` 요소입니다. 비트맵 리소스의 위치를 지정 하는 위치입니다. 자세한 내용은 참조 [메뉴 명령에 아이콘 추가](../../extensibility/adding-icons-to-menu-commands.md)합니다.  
  
 대부분의 메뉴, 그룹 및 명령을 올바르게 배치할 부모/자식 관리 구조에 사용할 수 있습니다. 매우 큰 명령 집합, 데이터 집합 또는 여러 위치에서 메뉴, 그룹 또는 명령 해야 표시 되 면 명령 배치를 지정 하는 것이 좋습니다.  
  
##### <a name="to-rely-on-parenting-to-place-ui-elements-in-the-ide"></a>IDE에서 UI 요소를 배치 하는 부모/자식 관리를 사용 하려면  
  
1.  일반적인 부모 지정에 대 한 만들기는 `Parent` 각 요소 `Menu`, `Group`, 및 `Command` 패키지에 정의 된 요소를 합니다.  
  
     대상은 `Parent` 요소는 메뉴 또는 메뉴에 있는 그룹, 그룹 또는 명령입니다.  
  
    1.  설정의 `guid` 특성의 이름으로는 `GuidSymbol` 명령 집합을 정의 하는 요소입니다. 대상 요소에 속하지 않으면 패키지의 경우는 해당.vsct 파일에 정의 된 해당 명령 집합에 대 한 guid를 사용 합니다.  
  
    2.  설정의 `id` 특성에 맞게는 `id` 대상 메뉴 또는 그룹의 특성입니다. 메뉴 및 Visual Studio에 의해 노출 되는 그룹의 목록을 보려면 [Guid 및 Visual Studio 메뉴 Id](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) 또는 [Guid 및 Id의 Visual Studio 도구 모음](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)합니다.  
  
 IDE에 배치할 수 있는 UI 요소의 많은 또는 여러 위치에 나타나야 하는 요소가 있으면 해당 배치에 대 정의 [CommandPlacements](../../extensibility/commandplacements-element.md) 요소를 다음 단계에 나와 있는 것 처럼 합니다.  
  
##### <a name="to-use-command-placement-to-place-ui-elements-in-the-ide"></a>명령 배치를 사용 하 여 IDE에서 UI 요소를 배치 하려면  
  
1.  이후에 `Commands` 요소를 추가 `CommandPlacements` 요소입니다.  
  
2.  에 `CommandPlacements` 요소를 추가 `CommandPlacement` 각 메뉴, 그룹 또는 배치 하는 명령에 대 한 요소입니다.  
  
     각 `CommandPlacement` 요소 또는 `Parent` 요소 하나의 메뉴, 그룹 또는 명령 하나의 IDE 위치에 배치 합니다. UI 요소는 하나의 부모를 하나만 사용할 수 있지만 명령 배치를 여러 개 가질 수 있습니다. 여러 위치에서 UI 요소를 배치 하려면 추가 `CommandPlacement` 각 위치에 대 한 요소입니다.  
  
3.  설정의 `guid` 및 `id` 각 특성 `CommandPlacement` 호스팅 메뉴나와 마찬가지로 그룹 요소에 대 한 것는 `Parent` 요소입니다. 설정할 수도 있습니다는 `priority` UI 요소의 상대 위치를 설정 하는 특성입니다.  
  
 부모/자식 관리 하 여 배치 및 명령 배치를 혼합할 수 있습니다. 그러나 매우 큰 명령 집합만 명령 배치를 사용 하는 것이 좋습니다.  
  
### <a name="adding-specialized-behaviors"></a>특별 한 동작 추가  
 사용할 수 있습니다 [CommandFlag](../../extensibility/command-flag-element.md) 요소 모양과 표시 유형을 변경 하려면, 예를 들어 메뉴 및 명령을의 동작을 수정할 수 있습니다. 또한을 조정할 수 있습니다는 명령을 사용 하 여 표시 되 면 [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md), 바로 가기 키를 사용 하 여 추가 또는 [KeyBindings](../../extensibility/keybindings-element.md)합니다. 특정 종류의 메뉴 및 명령을 이미 특수 기본 제공 동작 합니다.  
  
##### <a name="to-add-specialized-behaviors"></a>특수 동작을 추가 하려면  
  
1.  UI 요소를 표시 하려면 예를 들어 특정 UI 컨텍스트에만 솔루션이 로드 될 때 표시 유형 제약 조건을 사용 합니다.  
  
    1.  이후에 `Commands` 요소를 추가 `VisibilityConstraints` 요소입니다.  
  
    2.  각 UI에 항목을 제한에 대 한 추가 [VisibilityItem](../../extensibility/visibilityitem-element.md) 요소입니다.  
  
    3.  각각에 대해 `VisibilityItem` 요소를 설정는 `guid` 및 `id` 메뉴, 그룹 또는 명령 및 설정에는 특성의 `context` 에 정의 된 대로 특성 UI 컨텍스트를는 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> 클래스입니다. 자세한 내용은 참조 [VisibilityItem 요소](../../extensibility/visibilityitem-element.md)합니다.  
  
2.  코드에서 UI 항목 가용성 또는 표시 유형을 설정 하려면 다음 명령 플래그 중 하나 이상을 사용 합니다.  
  
    -   DefaultDisabled  
  
    -   DefaultInvisible  
  
    -   DynamicItemStart  
  
    -   DynamicVisibility  
  
    -   NoShowOnMenuController  
  
    -   NotInTBList  
  
     자세한 내용은 참조 [명령 플래그 요소](../../extensibility/command-flag-element.md)합니다.  
  
3.  요소가 표시 되 면 또는 모양을 동적으로 변경 방법을 변경 하려면 다음 명령 플래그 중 하나 이상을 사용 합니다.  
  
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
  
     자세한 내용은 참조 [명령 플래그 요소](../../extensibility/command-flag-element.md)합니다.  
  
4.  요소 명령을 받을 때 반응 하는 방식을 변경 하려면 다음 명령 플래그 중 하나 이상을 사용 합니다.  
  
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
  
     자세한 내용은 참조 [명령 플래그 요소](../../extensibility/command-flag-element.md)합니다.  
  
5.  메뉴 또는 메뉴 항목에 종속 메뉴 바로 가기 키를 연결 하려면 추가 앰퍼샌드 문자 ('& ')에 `ButtonText` 메뉴 또는 메뉴 항목에 대 한 요소입니다. 앰퍼샌드 뒤의 문자가 부모 메뉴 열려 있을 때 활성 바로 가기 키입니다.  
  
6.  명령에 독립적인 메뉴 바로 가기 키를 연결 하려면 사용 하 여 [KeyBindings](../../extensibility/keybindings-element.md)합니다. 자세한 내용은 참조 [KeyBinding 요소](../../extensibility/keybinding-element.md)합니다.  
  
7.  메뉴 텍스트 필드를 지역화를 사용 하 여는 `LocCanonicalName` 요소입니다. 자세한 내용은 참조 [Strings 요소](../../extensibility/strings-element.md)합니다.  
  
 메뉴 및 단추 유형도 특수 동작을 포함합니다. 다음 표에서 몇 가지 특수 한 메뉴 및 단추 종류를 설명합니다. 다른 형식의 참조는 `types` 특성에 대 한 설명을 [메뉴 요소](../../extensibility/menu-element.md), [Button 요소](../../extensibility/button-element.md), 및 [콤보 요소](../../extensibility/combo-element.md)합니다.  
  
 콤보 상자  
 콤보 상자에는 도구 모음에서 사용할 수 있는 드롭다운 목록입니다. 콤보 상자에는 UI를 추가 하려면 만듭니다는 [바로 가기 단축키 +](../../extensibility/combos-element.md) 요소에는 `Commands` 요소입니다. 그런 다음에 추가 `Combos` 요소는 `Combo` 추가할 각 콤보 상자에 대 한 요소입니다. `Combo` 요소에 동일한 특성 및 자식으로 있는 `Button` 요소 또한 `DefaultWidth` 및 `idCommandList` 특성입니다. `DefaultWidth` 너비를 픽셀 단위로 설정 하는 특성 및 `idCommandList` 특성 콤보 상자를 채우는 데 사용 되는 명령 ID를 가리킵니다. 자세한 내용은 참조는 `Combo` 요소 설명서입니다.  
  
 MenuController  
 메뉴 컨트롤러는 옆쪽 화살표가 있는는 단추입니다. 화살표를 클릭 하면 목록이 열립니다. 메뉴 컨트롤러는 UI를 추가 하려면 만듭니다는 `Menu` 요소 집합과 해당 `type` 특성을 **MenuController** 또는 **MenuControllerLatched**원하는 동작에 따라 합니다. 메뉴 컨트롤러를 채우려면의 부모로 설정할는 `Group` 요소입니다. 메뉴 컨트롤러는 해당 그룹의 모든 자식 드롭 다운 목록에 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [확장 메뉴 및 명령](../../extensibility/extending-menus-and-commands.md)   
 [Visual Studio 명령 테이블 (합니다. Vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)