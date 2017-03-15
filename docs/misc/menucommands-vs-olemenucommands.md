---
title: "MenuCommand 및 OleMenuCommand | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령, VSPackage에서 만들기"
  - "명령 단추, 만들기 및 배치"
  - "메뉴, 명령 만들기"
ms.assetid: 553d5e07-3e19-4aba-b490-6c7dd05fd82e
caps.latest.revision: 46
caps.handback.revision: 46
manager: "douge"
---
# MenuCommand 및 OleMenuCommand
<xref:System.ComponentModel.Design.MenuCommand> 또는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체에서 파생하고 적절한 이벤트 처리기를 구현하여 메뉴 명령을 만들 수 있습니다. 대부분의 경우 <xref:System.ComponentModel.Design.MenuCommand>를 VSPackage 프로젝트 템플릿으로 사용할 수 있지만 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>를 사용해야 할 때가 있습니다.  
  
 사용자가 VSPackage를 사용하려면 IDE에서 VSPackage를 사용할 수 있는 명령이 표시되어야 하고 사용하도록 설정되어야 합니다. Visual Studio Package 프로젝트 템플릿을 사용하여 .vsct 파일에서 명령이 만들어지면 기본적으로 표시되고 사용하도록 설정됩니다.`DynamicItemStart` 등의 일부 명령 플래그를 설정하면 기본 동작을 변경할 수 있습니다. 표시 여부, 사용 설정 상태 및 명령의 기타 속성은 명령과 관련된 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체에 액세스하여 런타임 시 코드에서 변경할 수도 있습니다.  
  
## 사전 요구 사항  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)을 참조하세요.  
  
## Visual Studio 패키지 템플릿의 템플릿 위치  
 **새 프로젝트** 대화 상자의 **Visual Basic\/확장성**, **C\#\/확장성** 또는 **기타 프로젝트 형식\/확장성**에서 Visual Studio 패키지 템플릿을 찾을 수 있습니다.  
  
## 명령 만들기  
 모든 명령, 명령 그룹, 메뉴, 도구 모음 및 도구 창은 .vsct 파일에서 정의됩니다. 자세한 내용은 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)을 참조하세요.  
  
 패키지 템플릿을 사용하여 VSPackage를 만드는 경우 **메뉴 명령**을 선택하여 .vsct 파일을 만들고 기본 메뉴 명령을 정의합니다. 자세한 내용은 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)을 참조하세요.  
  
#### IDE에 명령을 추가하려면  
  
1.  .vsct 파일을 엽니다.  
  
2.  `Symbols` 섹션에서 그룹 및 명령이 포함된 [GuidSymbol](../extensibility/guidsymbol-element.md) 요소를 찾습니다.  
  
3.  다음 예제와 같이 추가하려는 각 메뉴, 그룹 또는 명령에 대한 [IDSymbol](../extensibility/idsymbol-element.md) 요소를 만듭니다.  
  
     [!CODE [ButtonGroup#01](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#01)]  
  
     `GuidSymbol` 및 `IDSymbol` 요소의 `name` 특성은 각 새 메뉴, 그룹 또는 명령에 대한 GUID:ID 쌍을 제공합니다.`guid`는 VSPackage에 대해 정의된 명령 집합을 나타냅니다. 여러 명령 집합을 정의할 수 있습니다. 각 GUID:ID 쌍은 고유해야 합니다.  
  
4.  다음 예제에서처럼 [Buttons](../extensibility/buttons-element.md) 섹션에 [Button](../extensibility/button-element.md) 요소를 만들어 명령을 정의합니다.  
  
     [!CODE [ButtonGroup#03](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#03)]  
  
    1.  `guid` 및 `id` 필드를 새 명령의 GUID:ID와 일치하도록 설정합니다.  
  
    2.  `priority` 특성을 설정합니다.  
  
         `priority` 특성은 .vsct에서 해당 부모 그룹의 다른 개체 간에 단추 위치를 결정하는 데 사용됩니다.  
  
         우선 순위 값이 낮은 명령은 우선 순위 값이 높은 명령의 위 또는 왼쪽에 표시됩니다. 중복 우선 순위 값이 허용되지만 우선 순위가 같은 명령의 상대적 위치는 런타임 시 VSPackage가 처리되는 순서에 의해 결정되므로 순서를 미리 결정할 수 없습니다.  
  
         `priority` 특성을 생략하면 값이 0으로 설정됩니다.  
  
    3.  `type` 특성을 설정합니다. 대부분의 경우 값은 `"Button"`으로 설정됩니다. 다른 유효한 단추 형식에 대한 설명은 [Button 요소](../extensibility/button-element.md)를 참조하세요.  
  
5.  단추 정의에서 [ButtonText](../extensibility/buttontext-element.md) 요소가 포함된 [Strings](../extensibility/strings-element.md) 요소를 만들어 IDE에 나타나는 메뉴 이름을 포함하고, [CommandName](../extensibility/commandname-element.md) 요소를 만들어 **명령** 창에서 메뉴에 액세스하는 데 사용되는 명령 이름을 포함합니다.  
  
     단추 텍스트 문자열에 '&' 문자가 포함된 경우 Alt 키와 '&' 바로 뒤의 문자를 눌러 메뉴를 열 수 있습니다.  
  
     `Tooltip` 요소를 추가하면 사용자가 해당 단추를 포인터로 가리킬 때 포함된 텍스트가 표시됩니다.  
  
6.  명령으로 아이콘\(있는 경우\)을 표시하려면 [Icon](../extensibility/icon-element.md) 요소를 추가하여 해당 아이콘을 지정합니다. 아이콘은 도구 모음의 단추에는 필요하지만 메뉴 항목에는 필요하지 않습니다.`Icon` 요소의 `guid` 및 `id`는 `Bitmaps` 섹션에 정의된 [Bitmap](../extensibility/bitmap-element.md) 요소와 일치해야 합니다.  
  
7.  명령 플래그를 적절하게 추가하여 단추의 모양 및 동작을 변경합니다. 이 작업을 수행하려면 메뉴 정의에 [CommandFlag](../extensibility/command-flag-element.md) 요소를 추가합니다.  
  
8.  명령의 부모 그룹을 설정합니다. 부모 그룹은 직접 만든 그룹, 다른 패키지의 그룹 또는 IDE의 그룹이 될 수 있습니다. 예를 들어 Visual Studio 편집 도구 모음의 **주석** 및 **주석 제거** 단추 옆에 명령을 추가하려면 부모를 guidStdEditor:IDG\_VS\_EDITTOOLBAR\_COMMENT로 설정합니다. 부모가 사용자 정의 그룹인 경우 IDE에 나타나는 메뉴, 도구 모음 또는 도구 창의 자식이어야 합니다.  
  
     디자인에 따라 두 가지 방법 중 하나로 이 작업을 수행할 수 있습니다.  
  
    -   `Button` 요소에서 [Parent](../extensibility/parent-element.md) 요소를 만들고 해당 `guid` 및 `id` 필드를 명령을 호스트할 그룹\(*기본 부모 그룹*\)의 GUID 및 ID로 설정합니다.  
  
         다음 예제에서는 사용자 정의 메뉴에 표시될 명령을 정의합니다.  
  
         [!CODE [TopLevelMenu#03](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#03)]  
  
    -   명령 배치를 사용하여 명령을 배치할 경우 `Parent` 요소를 생략할 수 있습니다. 다음 예제와 같이 `Symbols` 섹션 전에 [CommandPlacements](../extensibility/commandplacements-element.md) 요소를 만들고 명령의 `guid` 및 `id`, `priority` 및 부모를 포함하는[CommandPlacement](../extensibility/commandplacement-element.md) 요소를 추가합니다.  
  
         [!CODE [ButtonGroup#04](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#04)]  
  
         GUID:ID가 동일하고 부모가 서로 다른 명령 배치를 여러 개 만들면 메뉴가 여러 위치에 나타납니다. 자세한 내용은 [CommandPlacements](../extensibility/commandplacements-element.md) 요소를 참조하세요.  
  
     명령 그룹 및 부모\/자식 관리에 대한 자세한 내용은 [단추의 다시 사용할 수 있는 그룹 만들기](../extensibility/creating-reusable-groups-of-buttons.md)를 참조하세요.  
  
 이 시점에서는 명령이 IDE에 표시되지만 작동하지는 않습니다. 명령이 패키지 템플릿에 의해 만들어진 경우 기본적으로 클릭 처리기에 메시지가 표시됩니다.  
  
## 새 명령 처리  
 관리 코드의 명령은 대부분 <xref:System.ComponentModel.Design.MenuCommand> 개체 또는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체와 명령을 연결하고 해당 이벤트 처리기를 구현하여 MPF\(관리되는 패키지 프레임워크\)를 통해 처리할 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스를 사용하여 직접 명령을 처리하는 코드의 경우 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스 및 해당 메서드를 구현해야 합니다. 두 개의 가장 중요한 메서드는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 및 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>입니다.  
  
1.  다음 예제와 같이 <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> 인스턴스를 가져옵니다.  
  
     [!code-cs[ButtonGroup#21](../misc/codesnippet/CSharp/menucommands-vs-olemenucommands_5.cs)]  
  
2.  다음 예제와 같이 처리할 명령의 GUID 및 ID를 해당 매개 변수로 사용하는 <xref:System.ComponentModel.Design.CommandID> 개체를 만듭니다.  
  
     [!code-cs[ButtonGroup#22](../misc/codesnippet/CSharp/menucommands-vs-olemenucommands_6.cs)]  
  
     Visual Studio 패키지 템플릿은 명령의 GUID 및 ID를 저장하는 `GuidList` 및 `PkgCmdIDList` 컬렉션을 제공합니다. 이러한 컬렉션은 템플릿을 통해 추가된 명령에 자동으로 채워지지만 수동으로 추가한 명령의 경우 ID 항목을 `PkgCmdIdList` 클래스에 추가해야 합니다.  
  
     또는 GUID의 원시 문자열 값 및 ID의 정수 값을 사용하여 <xref:System.ComponentModel.Design.CommandID> 개체를 채울 수 있습니다.  
  
3.  다음 예제에서처럼 <xref:System.ComponentModel.Design.MenuCommand> 또는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체를 인스턴스화합니다. 이 개체들은 <xref:System.ComponentModel.Design.CommandID>와 함께 명령을 처리하는 메서드를 지정합니다.  
  
     [!code-cs[ButtonGroup#23](../misc/codesnippet/CSharp/menucommands-vs-olemenucommands_7.cs)]  
  
     <xref:System.ComponentModel.Design.MenuCommand>는 정적 명령에 적합합니다. 동적 메뉴 항목 표시에는 QueryStatus 이벤트 처리기가 필요합니다.<xref:Microsoft.VisualStudio.Shell.OleMenuCommand>는 명령의 호스트 메뉴가 열릴 때 발생하는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> 이벤트와 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A> 등의 다른 일부 속성을 추가합니다.  
  
     패키지 템플릿으로 만든 명령은 기본적으로 패키지 클래스에 있는 `Initialize()` 메서드의 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체에 전달됩니다.  
  
4.  <xref:System.ComponentModel.Design.MenuCommand>는 정적 명령에 적합합니다. 동적 메뉴 항목 표시에는 QueryStatus 이벤트 처리기가 필요합니다.<xref:Microsoft.VisualStudio.Shell.OleMenuCommand>는 명령의 호스트 메뉴가 열릴 때 발생하는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> 이벤트와 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A> 등의 다른 일부 속성을 추가합니다.  
  
     패키지 템플릿으로 만든 명령은 기본적으로 패키지 클래스에 있는 `Initialize()` 메서드의 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체에 전달됩니다. Visual Studio 마법사는 `MenuCommand`를 사용하여 `Initialize` 메서드를 구현합니다. 동적 메뉴 항목 표시의 경우 다음 단계와 같이 `OleMenuCommand`로 변경해야 합니다. 또한 메뉴 항목의 텍스트를 변경하려면 다음 예제와 같이 .vsct 파일의 메뉴 명령 단추에 TextChanges 명령 플래그를 추가해야 합니다.  
  
     [!CODE [MenuText#02](../CodeSnippet/VS_Snippets_VSSDK/menutext#02)]  
  
5.  새 메뉴 명령을 <xref:System.ComponentModel.Design.IMenuCommandService> 인터페이스의 <xref:System.ComponentModel.Design.IMenuCommandService.AddCommand%2A> 메서드에 전달합니다. 이 작업은 다음 예제와 같이 패키지 템플릿으로 만든 명령에 대해 기본적으로 수행됩니다.  
  
     [!code-cs[ButtonGroup#24](../misc/codesnippet/CSharp/menucommands-vs-olemenucommands_9.cs)]  
  
6.  명령을 처리하는 메서드를 구현합니다.  
  
#### QueryStatus를 구현하려면  
  
1.  QueryStatus 이벤트는 명령이 표시되기 전에 발생합니다. 이렇게 하면 사용자에게 전달되기 전에 이벤트 처리기에서 해당 명령의 속성을 설정할 수 있습니다.<xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체로 추가된 명령만 이 메서드에 액세스할 수 있습니다.  
  
     다음 예제와 같이 명령 처리를 위해 만든 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체의 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> 이벤트에 `EventHandler` 개체를 추가합니다\(`menuItem`은 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 인스턴스임\).  
  
     [!code-cs[MenuText#14](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_10.cs)]
     [!code-vb[MenuText#14](../extensibility/codesnippet/VisualBasic/menucommands-vs-olemenucommands_10.vb)]  
  
     `EventHandler` 개체에 메뉴 명령의 상태를 쿼리할 때 호출되는 메서드의 이름을 지정합니다.  
  
2.  명령에 대한 쿼리 상태 처리기 메서드를 구현합니다. 텍스트를 포함하여 메뉴 명령에 대한 다양한 특성을 설정하는 데 사용되는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체에 `object` `sender` 매개 변수를 캐스트할 수 있습니다. 다음 표에서는 <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> 플래그에 해당하는 <xref:System.ComponentModel.Design.MenuCommand> 클래스\(MPF 클래스 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>가 파생됨\)의 속성을 보여 줍니다.  
  
    |MenuCommand 속성|OLECMDF 플래그|  
    |--------------------|-----------------|  
    |<xref:System.ComponentModel.Design.MenuCommand.Checked%2A> \= `true`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
    |<xref:System.ComponentModel.Design.MenuCommand.Visible%2A> \= `false`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
    |<xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> \= `true`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
  
     메뉴 명령의 텍스트를 변경하려면 다음 예제와 같이 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체에 대해 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A> 속성을 사용합니다.  
  
     [!code-cs[MenuText#11](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_11.cs)]
     [!code-vb[MenuText#11](../extensibility/codesnippet/VisualBasic/menucommands-vs-olemenucommands_11.vb)]  
  
 MPF는 지원되지 않거나 알 수 없는 그룹의 사례를 자동으로 처리합니다.<xref:System.ComponentModel.Design.IMenuCommandService.AddCommand%2A> 메서드를 사용하여 <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService>에 추가하지 않는 한 명령은 지원되지 않습니다.  
  
### IOleCommandTarget 인터페이스를 사용하여 명령 처리  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스를 직접 사용하는 코드의 경우 VSPackage는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스의 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 및 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>의 메서드를 모두 구현해야 합니다. VSPackage가 프로젝트 계층 구조를 구현하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A> 메서드를 대신 구현해야 합니다.  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 및 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 메서드는 모두 단일 명령 집합 `GUID` 및 명령 ID의 배열을 입력으로 사용하도록 디자인되었습니다. Vspackage에서 한 번의 호출로 여러 ID를 제공하는 이 개념을 완벽하게 지원하는 것이 좋습니다. 그러나 다른 VSPackage에서 Vspackage를 호출하지 않으면 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 및 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 메서드가 잘 정의된 순서대로 실행되므로 명령 배열에 하나의 명령 ID만 포함된 것으로 간주할 수 있습니다. 라우팅에 대한 자세한 내용은 [Vspackage의 명령 라우팅](../extensibility/internals/command-routing-in-vspackages.md)을 참조하세요.  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스를 사용하여 직접 명령을 처리하는 코드의 경우 VSPackage에서 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드를 구현하여 다음과 같이 명령을 처리해야 합니다.  
  
##### QueryStatus 메서드를 구현하려면  
  
1.  유효한 명령에 대해 <xref:Microsoft.VisualStudio.VSConstants.S_OK>를 반환합니다.  
  
2.  `prgCmds` 매개 변수의 `cmdf` 요소를 설정합니다.  
  
     `cmdf` 요소의 값은 논리적 OR\(`|`\) 연산자를 사용하여 결합한 <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> 열거형 값의 논리적 공용 구조체입니다.  
  
     명령 상태를 기반으로 적절한 열거형을 사용합니다.  
  
    -   명령이 지원되는 경우:  
  
         `prgCmds[0].cmdf = OLECMDF_SUPPORTED;`  
  
    -   현재 명령이 표시되지 않아야 하는 경우:  
  
         `prgCmds[0].cmdf |= OLECMDF_INVISIBLE;`  
  
    -   명령이 설정되어 클릭한 것처럼 나타나는 경우:  
  
         `prgCmds[0].cmdf |= OLECMDF_LATCHED;`  
  
         `MenuControllerLatched` 형식의 메뉴에서 호스트되는 처리 명령의 경우 `OLECMDF_LATCHED` 플래그로 표시된 첫 번째 명령이 시작 시 메뉴에 표시되는 기본 명령입니다.`MenuController` 메뉴 형식에 대한 자세한 내용은 [Menu 요소](../extensibility/menu-element.md)를 참조하세요.  
  
    -   명령이 현재 사용되는 경우:  
  
         `prgCmds[0].cmdf |= OLECMDF_ENABLED;`  
  
    -   명령이 바로 가기 메뉴의 일부이고 기본적으로 숨겨져 있는 경우:  
  
         `prgCmds[0] cmdf |= OLECMDF_DEFHIDEONCTXMENU`  
  
    -   명령에서 `TEXTCHANGES` 플래그를 사용하는 경우 `pCmdText` 매개 변수의 `rgwz` 요소를 명령의 새 텍스트로 설정하고 `pCmdText` 매개 변수의 `cwActual` 요소를 명령 문자열의 크기로 설정합니다.  
  
     오류 조건의 경우 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드는 다음과 같은 오류 사례를 처리해야 합니다.  
  
    -   GUID를 알 수 없거나 지원되지 않는 경우 `OLECMDERR_E_UNKNOWNGROUP`을 반환합니다.  
  
    -   GUID를 알 수 있지만 명령 ID를 알 수 없거나 지원되지 않는 경우 `OLECMDERR_E_NOTSUPPORTED`을 반환합니다.  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 메서드의 VSPackage 구현은 명령이 지원되는지 여부와 성공적으로 처리되었는지 여부에 따라 특정 오류 코드도 반환해야 합니다.  
  
##### Exec 메서드를 구현하려면  
  
-   `GUID` 명령을 알 수 없는 경우 `OLECMDERR_E_UNKNOWNGROUP`을 반환합니다.  
  
-   `GUID`가 알려졌지만 명령 ID를 알 수 없는 경우 `OLECMDERR_E_NOTSUPPORTED`를 반환합니다.  
  
-   `GUID` 및 명령 ID가 .vsct 파일의 명령에 사용되는 GUID:ID 쌍과 일치하는 경우 명령과 연결된 코드를 실행하고 <xref:Microsoft.VisualStudio.VSConstants.S_OK>를 반환합니다.  
  
## 참고 항목  
 [VSCT XML 스키마 참조](../extensibility/vsct-xml-schema-reference.md)   
 [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)