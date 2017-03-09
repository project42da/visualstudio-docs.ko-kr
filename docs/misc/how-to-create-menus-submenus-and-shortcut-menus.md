---
title: "방법: 메뉴, 하위 메뉴 및 바로 가기 메뉴 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령 모음, 아키텍처"
  - "메뉴, 만들기"
  - "메뉴, 아키텍처"
  - "명령, 메뉴 "
  - "메뉴"
ms.assetid: 62004fd9-7f99-4f00-8d01-1dde53e23dbb
caps.latest.revision: 46
caps.handback.revision: 46
manager: "douge"
---
# 방법: 메뉴, 하위 메뉴 및 바로 가기 메뉴 만들기
Visual Studio IDE\(통합 개발 환경\)에 메뉴를 추가하려면 VSPackage가 명령 그룹 메뉴에 대해 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 아키텍처를 사용해야 합니다. 명령 그룹 메뉴에서 구성 요소 및 IDE를 통해 명령을 공유할 수 있습니다. 명령 그룹 메뉴에 대한 자세한 내용은 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)을 참조하세요.  
  
 VSPackage에서 메뉴는 .vsct 파일의 [Menus](../extensibility/menus-element.md) 섹션에 정의되어 있습니다. .vsct 파일은 메뉴, 도구 모음, 그룹 및 명령을 정의합니다. 명령은 사용자가 기능을 수행하기 위해 클릭하는 것입니다. 그룹은 명령의 컨테이너입니다. 메뉴는 그룹의 컨테이너입니다. 기본 메뉴를 만들려면 메뉴, 명령 그룹 및 하나 이상의 명령을 만들어야 합니다.  
  
 세 가지 기본 방법으로 메뉴가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 표시됩니다.  
  
-   주 메뉴 모음의 메뉴로  
  
-   다른 메뉴의 하위 메뉴로  
  
-   바로 가기 메뉴로\(일반적으로 마우스 오른쪽 단추 클릭으로 표시\)  
  
 이 항목은 각 종류의 메뉴를 만드는 방법을 보여 줍니다. 또한 다음 연습은 이를 수행하는 방법을 보여 줍니다.  
  
-   [Visual Studio 메뉴 모음에 메뉴를 추가합니다.](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)  
  
-   [하위 메뉴에 추가](../extensibility/adding-a-submenu-to-a-menu.md)  
  
-   [도구 창의 바로 가기 메뉴를 추가합니다.](../extensibility/adding-a-shortcut-menu-in-a-tool-window.md)  
  
### 메뉴, 하위 메뉴 또는 바로 가기 메뉴를 만들려면  
  
1.  프로젝트에서, 편집기에서 열려는 .vsct 파일을 두 번 클릭합니다.  
  
     프로젝트에 .vsct 파일이 없는 경우 추가합니다. Visual Studio 패키지 템플릿을 사용하여 패키지를 만드는 경우 **메뉴 명령**을 선택합니다. 이를 통해 .vsct 파일을 생성합니다.  
  
2.  `Symbols` 섹션에서 그룹 및 명령이 포함된 [GuidSymbol](../extensibility/guidsymbol-element.md) 요소를 찾습니다.  
  
3.  다음 예제와 같이 추가하려는 각 메뉴, 그룹 또는 명령에 대한 [IDSymbol](../extensibility/idsymbol-element.md) 요소를 만듭니다.  
  
     [!CODE [ButtonGroup#01](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#01)]  
  
     `GuidSymbol` 및 `IDSymbol` 요소의 `name` 특성은 각 새 메뉴, 그룹 또는 명령에 대한 GUID:ID 쌍을 제공합니다.`GUID`는 VSPackage에 대해 정의된 명령 집합을 나타냅니다. 여러 명령 집합을 정의할 수 있습니다. 각 GUID:ID 쌍은 고유해야 합니다.  
  
4.  다음과 같이 `Menus` 섹션에서 새 메뉴를 정의합니다.  
  
    1.  `guid` 및 `id` 필드를 새 메뉴의 GUID:ID와 일치하도록 설정합니다.  
  
    2.  `priority` 특성을 설정합니다.  
  
         `priority` 특성은 .vsct 파일에서 해당 부모 그룹의 다른 개체 간에 메뉴 위치를 결정하는 데 사용됩니다.  
  
         우선 순위 값이 낮은 메뉴는 우선 순위 값이 높은 메뉴 앞에 표시됩니다. 중복 우선 순위 값이 허용되지만 우선 순위가 같은 메뉴의 상대적 위치는 런타임 시 VSPackage가 처리되는 순서에 의해 결정되므로 순서를 미리 결정할 수 없습니다.`priority` 특성을 생략하면 값이 0으로 설정됩니다.  
  
         바로 가기 메뉴의 배치는 호출하는 코드에 의해 결정되기 때문에 이에 대한 우선 순위는 설정하지 마세요.  
  
    3.  메뉴 및 하위 메뉴의 경우 `type` 특성을 일반 메뉴를 설명하는 `Menu`로 설정합니다. 바로 가기 메뉴의 경우 `type` 특성을 `Context`로 설정합니다.  
  
         도구 모음 및 메뉴 컨트롤러와 같은 다른 유효한 메뉴 형식에 대한 설명의 경우 [Menu 요소](../extensibility/menu-element.md)를 참조하세요.  
  
    4.  메뉴 정의에서 [ButtonText](../extensibility/buttontext-element.md) 요소가 포함된 [Strings](../extensibility/strings-element.md) 섹션을 만들어 IDE에 나타나는 메뉴 이름을 포함하고, [CommandName](../extensibility/commandname-element.md) 요소를 만들어 **명령** 창에서 메뉴에 액세스하는 데 사용되는 명령 이름을 포함합니다.  
  
         단추 텍스트 문자열에 '&' 문자가 포함된 경우 Alt 키와 '&' 바로 뒤의 문자를 눌러 메뉴를 열 수 있습니다.  
  
    5.  명령 플래그를 적절하게 추가하여 메뉴의 모양 및 동작을 변경합니다. 이 작업을 수행하려면 메뉴 정의에 [CommandFlag](../extensibility/command-flag-element.md) 요소를 추가합니다. 자세한 내용은 [명령 플래그 요소](../extensibility/command-flag-element.md)을 참조하세요.  
  
5.  메뉴의 부모를 설정합니다. 표준 메뉴 또는 하위 메뉴의 경우 설계에 따라 다음 방법 중 하나에서 이를 수행합니다.  
  
    -   `Menu` 요소에서 [Parent](../extensibility/parent-element.md) 요소를 만들고 해당 `guid` 및 `id` 필드를 메뉴를 호스트할 그룹\(*기본 부모 그룹*\)의 GUID:ID로 설정합니다. 부모 그룹은 `Symbols` 섹션에서 직접 만든 그룹, 다른 패키지의 그룹 또는 IDE의 그룹이 될 수 있습니다. 예를 들어 IDE의 최상위 메뉴 모음에 메뉴를 추가하려면 **도구** 메뉴 근처에서 부모를 guidSHLMainMenu:IDG\_VS\_MM\_TOOLSADDINS로 설정합니다.  
  
         다음 예제에서는 Visual Studio 메뉴 모음에 표시되는 메뉴를 보여 줍니다.  
  
         [!CODE [TopLevelMenu#01](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#01)]  
  
    -   명령 배치를 사용하여 메뉴를 배치할 경우 `Parent` 요소를 생략할 수 있습니다. 다음 예제와 같이 `Symbols` 섹션 전에 [CommandPlacements](../extensibility/commandplacements-element.md) 섹션을 만들고 메뉴의 GUID:ID, 우선 순위 및 부모를 포함하는[CommandPlacement](../extensibility/commandplacement-element.md) 요소를 추가합니다.  
  
         [!CODE [ButtonGroup#04](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#04)]  
  
         GUID:ID가 동일하고 부모가 서로 다른 명령 배치를 여러 개 만들면 메뉴가 여러 위치에 나타납니다. 자세한 내용은 [CommandPlacements 요소](../extensibility/commandplacements-element.md)을 참조하세요.  
  
     표준 메뉴는 그 부모처럼 Visual Studio 메뉴 모음에 그룹이 있어야 합니다. 하위 메뉴의 경우 부모는 다른 메뉴\(또는 도구 모음 또는 다른 메뉴 형식\)에서 그룹이어야 합니다. 표시될 메뉴 또는 하위 메뉴는 하나 이상의 활성 명령이 포함된 그룹을 호스트하거나 `AlwaysCreate` 명령 플래그 집합이 있어야 합니다.  
  
     바로 가기 메뉴에는 부모 또는 명령 배치가 없습니다. 대신 코드에서 활성화되어야 합니다. 일반적으로 바로 가기 메뉴는 컨트롤 화면에서 마우스 오른쪽 단추 클릭에 대한 응답으로 활성화됩니다. 다음 예제에서는 바로 가기 메뉴를 정의합니다.  
  
     [!CODE [ButtonGroup#06](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#06)]  
  
6.  [Groups](../extensibility/groups-element.md) 섹션에서 메뉴에 표시될 명령이 포함된 [Group](../extensibility/group-element.md) 요소를 만듭니다.`Symbols` 섹션은 새 `Group` 요소와 GUID:ID가 동일한 항목을 포함해야 합니다.  
  
    1.  사용 중인 메뉴에서 원하는 위치에 표시되도록 그룹의 우선 순위를 설정합니다.  
  
         메뉴에서 각 그룹의 경계는 가로줄로 표시됩니다.  
  
    2.  이 새 그룹의 부모를 만든 메뉴의 GUID:ID로 설정합니다. 그러면 명령 그룹이 메뉴에 추가됩니다.  
  
     다음 예제에서 그룹은 위의 예제에 나온 최상위 메뉴에 표시됩니다.  
  
     [!CODE [TopLevelMenu#02](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#02)]  
  
     메뉴는 명령 및 하위 메뉴를 모두 포함할 수 있습니다. 하위 메뉴\(계단식 메뉴라고도 함\)는 단지 하나의 메뉴이지만 다른 메뉴 그룹에 추가되어 다른 메뉴를 호출하는 경우에만 노출되는 메뉴입니다. 다음 예제에 나와 있는 메뉴를 최상위 메뉴의 그룹에 넣으면 하위 메뉴가 됩니다.  
  
     [!CODE [TopLevelMenu#06](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#06)]  
  
7.  [Button](../extensibility/buttons-element.md) 섹션에서 명령 항목을 만들고 각 부모를 그룹의 GUID:ID로 설정하여 명령을 메뉴에 추가합니다. 각 [Button](../extensibility/button-element.md) 요소에는 `Symbols` 섹션에서 항목에 해당하는 GUID:ID가 있어야 합니다.  
  
     각 단추 항목의 `priority` 특성을 사용하여 명령이 그룹에 표시되는 순서를 지정합니다.  
  
     다음 예제에서는 최상위 메뉴에 표시될 명령을 정의합니다.  
  
     [!CODE [TopLevelMenu#03](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#03)]  
  
     단추 및 메뉴 항목에 대한 자세한 내용은 [Button 요소](../extensibility/button-element.md)를 참조하세요.  
  
     코드에서 메뉴 명령을 구현하는 방법에 대한 자세한 내용은 이 항목 앞에서 언급한 [MenuCommand 및 OleMenuCommand](../misc/menucommands-vs-olemenucommands.md) 또는 연습을 참조하세요.  
  
### 바로 가기 메뉴를 활성화하려면  
  
1.  바로 가기 메뉴의 GUID:ID를 가져옵니다. 기본적으로 패키지 템플릿은 명령 집합의 GUID를 유지하기 위해 PkgCmdID.cs 파일에서 `GuidList` 클래스를 만듭니다. 또한 템플릿은 템플릿에서 선언된 명령의 정수 ID 값을 유지하기 위해 PkgCmdId.cs 파일에서 `PkgCmdIdList` 클래스를 만듭니다. 바로 가기 메뉴 및 추가 명령은 템플릿이 완료된 후에 선언되어야 합니다. 다음 예제에서는 이러한 선언을 보여 줍니다.  
  
     [!CODE [TWShortcutMenu#12](../CodeSnippet/VS_Snippets_VSSDK/twshortcutmenu#12)]  
  
     GUID 및 ID 값을 직접 사용할 예정이면 이 단계를 생략할 수 있습니다. 그러나 가독성을 위해 여기에서 값을 설정하는 것이 좋습니다.  
  
2.  이벤트 처리기에 연결합니다. 일반적으로 바로 가기 메뉴는 다음 예제와 같이 컨트롤 화면의 마우스 오른쪽 버튼 클릭에 연결됩니다.  
  
     [!CODE [TWShortcutMenu#43](../CodeSnippet/VS_Snippets_VSSDK/twshortcutmenu#43)]  
  
     <xref:System.Windows.Forms.Control.PointToScreen%2A> 메서드는 컨트롤과 관련된 클릭 위치를 화면 위치로 변환합니다.<xref:Microsoft.VisualStudio.Shell.OleMenuCommandService.ShowContextMenu%2A> 메서드가 바로 가기 메뉴를 표시합니다.  
  
     이벤트 처리기를 포함하는 파일은 <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> 클래스에 액세스하려면 <xref:System.ComponentModel.Design> 네임스페이스를 포함해야 하고 <xref:System.ComponentModel.Design.IMenuCommandService> 인터페이스에 액세스하려면 <xref:Microsoft.VisualStudio.Shell> 네임스페이스를 포함해야 합니다.  
  
     [!CODE [TWShortcutMenu#41](../CodeSnippet/VS_Snippets_VSSDK/twshortcutmenu#41)]  
  
## 참고 항목  
 [MenuCommand 및 OleMenuCommand](../misc/menucommands-vs-olemenucommands.md)   
 [VSCT XML 스키마 참조](../extensibility/vsct-xml-schema-reference.md)   
 [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)