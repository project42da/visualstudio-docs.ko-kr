---
title: 메뉴 항목을 추가 하는 동적으로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- DYNAMICITEMSTART
- menu items, adding dynamically
- menus, adding dynamic items
ms.assetid: d281e9c9-b289-4d64-8d0a-094bac6c333c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bf7c9f8da800e827ac4b1993c55d4d96c8ca9d89
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="dynamically-adding-menu-items"></a>동적으로 메뉴 항목 추가
지정 하 여 런타임에 메뉴 항목을 추가할 수는 `DynamicItemStart` 표시 및 처리 명령에 항목을 코드에서 메뉴의 번호를 정의 하는 다음 Visual Studio 명령 테이블 (.vsct) 파일에 있는 자리 표시자 단추 정의에서 플래그를 명령입니다. VSPackage 로드 될 때 자리 표시자 동적 메뉴 항목으로 바뀝니다.  
  
 Visual Studio에서의 동적 목록을 사용 하는 **가장 최근에 사용한** 최근에 연 문서의 이름을 표시 합니다 (MRU) 목록 및 **Windows** 창의 이름을 표시 하는 목록 현재 열려 있습니다.   `DynamicItemStart` 플래그 명령 정의를 VSPackage 열릴 때까지 명령이 자리 표시자를 지정 합니다. VSPackage를 열 때 자리 표시자는 0 또는 런타임 시 생성 되 고 동적 목록에 추가 하는 더 많은 명령이으로 대체 됩니다. VSPackage 열릴 때까지 동적 목록이 나타나는 메뉴에서 위치를 확인 하려면 못할 수 있습니다.  Visual Studio 동적 목록으로 채우려면 ID 인 첫 번째 문자 자리 표시자의 ID와 동일 인 명령에 대 한 확인 하기 위해 VSPackage를 요청 합니다. Visual Studio에서 일치 하는 명령을 찾으면 명령의 이름을 동적 목록에 추가 합니다. 다음 ID 증가 하 고 더 이상 동적 명령 없을 때까지 동적 목록에 추가할 다른 일치 하는 명령을 찾습니다.  
  
 이 연습에서는에서 명령 사용 하 여 Visual Studio 솔루션에서 시작 프로젝트로 설정 하는 방법을 보여 줍니다.는 **솔루션 탐색기** 도구 모음입니다. 활성 솔루션의 프로젝트가 동적 드롭다운 목록에 있는 메뉴 컨트롤러를 사용 합니다. 이 명령은 솔루션이 없을 때 표시 되지 않도록 하려면 현재 열려 있거나 VSPackage는 솔루션에 여러 프로젝트가 있는 경우에 로드 되는 열려 있는 솔루션에 프로젝트를 하나만 있는 경우.  
  
 .Vsct 파일에 대 한 자세한 내용은 참조 [Visual Studio 명령 테이블 (합니다. Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)합니다.  
  
## <a name="creating-an-extension-with-a-menu-command"></a>메뉴 명령을 사용 하 여 확장 만들기  
  
1.  라는 VSIX 프로젝트 `DynamicMenuItems`합니다.  
  
2.  프로젝트를 열 때 사용자 지정 명령 항목 템플릿을 추가 하 고 이름을 **DynamicMenu**합니다. 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
## <a name="setting-up-the-elements-in-the-vsct-file"></a>.Vsct 파일에서 요소를 설정합니다.  
 메뉴 컨트롤러는 도구 모음에서 동적 메뉴 항목을 만들려면 다음 요소를 지정 합니다.  
  
-   그룹, 메뉴 컨트롤러 포함 된 및의 드롭다운 메뉴 항목을 포함 하는 다른 두 개의 명령  
  
-   형식의 메뉴 요소 `MenuController`  
  
-   두 개의 단추, 아이콘 및 도구 모음에서 도구를 제공 하는 메뉴 항목과 다른에 대 한 자리 표시자 역할을 하는 하나입니다.  
  
1.  DynamicMenuPackage.vsct, 명령 Id를 정의 합니다. 기호 섹션으로 이동 하 고 IDSymbol 요소에 대체는 **guidDynamicMenuPackageCmdSet** GuidSymbol 블록입니다. 두 개의 그룹, 메뉴 컨트롤러, 자리 표시자 명령 및 앵커 명령에 대 한 IDSymbol 요소를 정의 해야 합니다.  
  
    ```csharp  
    <GuidSymbol name="guidDynamicMenuPackageCmdSet" value="{ your GUID here }">  
        <IDSymbol name="MyToolbarItemGroup" value="0x1020" />  
        <IDSymbol name="MyMenuControllerGroup" value="0x1025" />  
        <IDSymbol name="MyMenuController" value ="0x1030"/>  
        <IDSymbol name="cmdidMyAnchorCommand" value="0x0103" />  
        <!-- NOTE: The following command expands at run time to some number of ids.  
         Try not to place command ids after it (e.g. 0x0105, 0x0106).  
         If you must add a command id after it, make the gap very large (e.g. 0x200) -->  
        <IDSymbol name="cmdidMyDynamicStartCommand" value="0x0104" />  
    </GuidSymbol>    
    ```  
  
2.  그룹 섹션에서 기존 그룹을 삭제 하 고 방금 정의한 두 그룹을 추가:  
  
    ```  
    <Groups>  
        <!-- The group that adds the MenuController on the Solution Explorer toolbar.   
             The 0x4000 priority adds this group after the group that contains the  
             Preview Selected Items button, which is normally at the far right of the toolbar. -->  
        <Group guid="guidDynamicMenuPackageCmdSet" id="MyToolbarItemGroup" priority="0x4000" >  
            <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN" />  
        </Group>  
        <!-- The group for the items on the MenuController drop-down. It is added to the MenuController submenu. -->  
        <Group guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" priority="0x4000" >  
            <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" />  
        </Group>  
    </Groups>  
    ```  
  
     MenuController를 추가 합니다. 항상 표시 되지 않으므로 DynamicVisibility 명령 플래그를 설정 합니다. ButtonText 표시 되지 않습니다.  
  
    ```  
    <Menus>  
        <!-- The MenuController to display on the Solution Explorer toolbar.  
             Place it in the ToolbarItemGroup.-->  
        <Menu guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" priority="0x1000" type="MenuController">  
            <Parent guid="guidDynamicMenuPackageCmdSet" id="MyToolbarItemGroup" />  
            <CommandFlag>DynamicVisibility</CommandFlag>  
            <Strings>  
               <ButtonText></ButtonText>  
           </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
3.  MenuController에 대 한 두 개의 단추 동적 메뉴 항목에 대 한 자리 표시자로 하나 만들고 하나는 앵커를 추가 합니다.  
  
     자리 표시자 단추의 부모는 **MyMenuControllerGroup**합니다. 자리 표시자 단추에 DynamicItemStart, DynamicVisibility, 및 TextChanges 명령 플래그를 추가 합니다. ButtonText 표시 되지 않습니다.  
  
     앵커 단추 아이콘 및 도구 설명 텍스트를 저장합니다. 앵커 단추의 부모 이기도 **MyMenuControllerGroup**합니다. 단추 메뉴 컨트롤러 드롭다운에 실제로 표시 되지 않으면 되도록 NoShowOnMenuController 명령 플래그 및 영구 앵커 있도록 FixMenuController 명령 플래그 추가.  
  
    ```  
    <!-- The placeholder for the dynamic items that expand to N items at runtime. -->  
    <Buttons>  
        <Button guid="guidDynamicMenuPackageCmdSet" id="cmdidMyDynamicStartCommand" priority="0x1000" >  
          <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" />  
          <CommandFlag>DynamicItemStart</CommandFlag>  
          <CommandFlag>DynamicVisibility</CommandFlag>  
          <CommandFlag>TextChanges</CommandFlag>  
          <!-- This text does not appear. -->  
          <Strings>  
            <ButtonText>Project</ButtonText>  
          </Strings>  
        </Button>  
  
        <!-- The anchor item to supply the icon/tooltip for the MenuController -->  
        <Button guid="guidDynamicMenuPackageCmdSet" id="cmdidMyAnchorCommand" priority="0x0000" >  
          <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" />  
          <!-- This is the icon that appears on the Solution Explorer toolbar. -->  
          <Icon guid="guidImages" id="bmpPicArrows"/>  
          <!-- Do not show on the menu controller's drop down list-->  
          <CommandFlag>NoShowOnMenuController</CommandFlag>  
          <!-- Become the permanent anchor item for the menu controller -->  
          <CommandFlag>FixMenuController</CommandFlag>  
          <!-- The text that appears in the tooltip.-->  
          <Strings>  
            <ButtonText>Set Startup Project</ButtonText>  
          </Strings>  
        </Button>  
    </Buttons>  
    ```  
  
4.  아이콘 (Resources 폴더)에서 프로젝트를 추가 하 고.vsct 파일에서에 대 한 참조를 추가 합니다. 이 연습에서는 프로젝트 템플릿에 포함 되어 있는 화살표 아이콘을 사용 합니다.  
  
5.  외부 기호 섹션 바로 앞의 명령 섹션 VisibilityConstraints 섹션을 추가 합니다. (경우 발생할 수 있습니다 경고를 기호 뒤에 추가 합니다.) 이 섹션에서는 메뉴 컨트롤러 여러 프로젝트와 솔루션 로드 될 때에 표시 됩니다.  
  
    ```  
    <VisibilityConstraints>  
         <!--Make the MenuController show up only when there is a solution with more than one project loaded-->  
        <VisibilityItem guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" context="UICONTEXT_SolutionHasMultipleProjects"/>  
    </VisibilityConstraints>  
    ```  
  
## <a name="implementing-the-dynamic-menu-command"></a>동적 메뉴 명령 구현  
 상속 되는 동적 메뉴 명령 클래스를 만들면 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>합니다. 이 구현에서 생성자 명령을 일치에 사용 하기 위한 조건자를 지정 합니다. 재정의 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.DynamicItemMatch%2A> 이 조건자를 사용 하는 메서드는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.MatchedCommandId%2A> 속성 호출 될 명령을 식별 합니다.  
  
1.  새 C# 클래스 파일인 DynamicItemMenuCommand.cs을 만들고 라는 클래스를 추가 **DynamicItemMenuCommand** 에서 상속 되는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>:  
  
    ```csharp  
    class DynamicItemMenuCommand : OleMenuCommand  
    {  
  
    }  
  
    ```  
  
2.  다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    using System.ComponentModel.Design;  
    ```  
  
3.  일치 항목이 조건자를 저장 하는 private 필드를 추가 합니다.  
  
    ```csharp  
    private Predicate<int> matches;  
  
    ```  
  
4.  상속 되는 생성자를 추가 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 생성자 명령 처리기를 지정 하 고 및 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> 처리기입니다. 이 명령은 일치 하는 조건자를 추가 합니다.  
  
    ```csharp  
    public DynamicItemMenuCommand(CommandID rootId, Predicate<int> matches, EventHandler invokeHandler, EventHandler beforeQueryStatusHandler)  
        : base(invokeHandler, null /*changeHandler*/, beforeQueryStatusHandler, rootId)  
    {  
        if (matches == null)  
        {  
            throw new ArgumentNullException("matches");  
        }  
  
        this.matches = matches;  
    }  
    ```  
  
5.  재정의 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.DynamicItemMatch%2A> 조건자 및 집합에서 일치 항목 호출한 메서드는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.MatchedCommandId%2A> 속성:  
  
    ```csharp  
    public override bool DynamicItemMatch(int cmdId)  
    {  
        // Call the supplied predicate to test whether the given cmdId is a match.  
        // If it is, store the command id in MatchedCommandid   
        // for use by any BeforeQueryStatus handlers, and then return that it is a match.  
        // Otherwise clear any previously stored matched cmdId and return that it is not a match.  
        if (this.matches(cmdId))  
        {  
            this.MatchedCommandId = cmdId;  
            return true;  
        }  
  
        this.MatchedCommandId = 0;  
        return false;  
    }  
    ```  
  
## <a name="adding-the-command"></a>명령 추가  
 DynamicMenu 생성자는 메뉴 명령, 동적 메뉴 및 메뉴 항목을 포함 하 여 설정할 수 있습니다.  
  
1.  DynamicMenuPackage.cs, 명령 집합의 GUID 및 명령 ID를 추가 합니다.  
  
    ```csharp  
    public const string guidDynamicMenuPackageCmdSet = "00000000-0000-0000-0000-00000000";  // get the GUID from the .vsct file  
    public const uint cmdidMyCommand = 0x104;  
    ```  
  
2.  DynamicMenu.cs 파일에 다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using System.ComponentModel.Design;  
    ```  
  
3.  DynamicMenu 클래스에서 private 필드를 추가 **dte2**합니다.  
  
    ```csharp  
    private DTE2 dte2;  
    ```  
  
4.  개인 rootItemId 필드를 추가 합니다.  
  
    ```csharp  
    private int rootItemId = 0;  
    ```  
  
5.  DynamicMenu 생성자에서 메뉴 명령을 추가 합니다. 다음 섹션의 명령 처리기 정의 하겠습니다는 `BeforeQueryStatus` 이벤트 처리기 및 일치 조건자입니다.  
  
    ```csharp  
    private DynamicMenu(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            // Add the DynamicItemMenuCommand for the expansion of the root item into N items at run time.   
            CommandID dynamicItemRootId = new CommandID(new Guid(DynamicMenuPackageGuids.guidDynamicMenuPackageCmdSet), (int)DynamicMenuPackageGuids.cmdidMyCommand);  
            DynamicItemMenuCommand dynamicMenuCommand = new DynamicItemMenuCommand(dynamicItemRootId,  
                IsValidDynamicItem,  
                OnInvokedDynamicItem,  
                OnBeforeQueryStatusDynamicItem);  
                commandService.AddCommand(dynamicMenuCommand);  
                }  
  
        dte2 = (DTE2)this.ServiceProvider.GetService(typeof(DTE));  
    }  
    ```  
  
## <a name="implementing-the-handlers"></a>처리기 구현  
 동적 메뉴 항목에 메뉴 컨트롤러를 구현 하려면 동적 항목을 클릭할 때 명령을 처리 해야 합니다. 메뉴 항목의 상태를 설정 하는 논리를 구현 해야 합니다. DynamicMenu 클래스에는 처리기를 추가 합니다.  
  
1.  구현 하는 **시작 프로젝트 설정** 명령에 추가 된 **OnInvokedDynamicItem** 이벤트 처리기. 호출 된 및의 절대 경로 설정 하 여 시작 프로젝트로 설정 하는 명령 텍스트와 같은 이름이 프로젝트를 찾습니다는 <xref:EnvDTE.SolutionBuild.StartupProjects%2A> 속성입니다.  
  
    ```csharp  
    private void OnInvokedDynamicItem(object sender, EventArgs args)  
    {  
        DynamicItemMenuCommand invokedCommand = (DynamicItemMenuCommand)sender;  
        // If the command is already checked, we don't need to do anything  
        if (invokedCommand.Checked)  
            return;  
  
        // Find the project that corresponds to the command text and set it as the startup project  
        var projects = dte2.Solution.Projects;  
        foreach (Project proj in projects)  
        {  
            if (invokedCommand.Text.Equals(proj.Name))  
            {  
                dte2.Solution.SolutionBuild.StartupProjects = proj.FullName;  
                return;  
            }  
        }  
    }  
    ```  
  
2.  추가 된 `OnBeforeQueryStatusDynamicItem` 이벤트 처리기입니다. 이 이전에 호출 처리기는 `QueryStatus` 이벤트입니다. 메뉴 항목 즉, 하지 자리 표시자 항목을 "실제" 항목을 인지 결정 및 여부는 항목을 이미 검사 했습니다 (프로젝트가 시작 프로젝트로 이미 설정 되어 있는지를 의미).  
  
    ```csharp  
    private void OnBeforeQueryStatusDynamicItem(object sender, EventArgs args)  
    {  
        DynamicItemMenuCommand matchedCommand = (DynamicItemMenuCommand)sender;  
        matchedCommand.Enabled = true;  
        matchedCommand.Visible = true;  
  
        // Find out whether the command ID is 0, which is the ID of the root item.  
        // If it is the root item, it matches the constructed DynamicItemMenuCommand,  
         // and IsValidDynamicItem won't be called.  
        bool isRootItem = (matchedCommand.MatchedCommandId == 0);  
  
        // The index is set to 1 rather than 0 because the Solution.Projects collection is 1-based.  
        int indexForDisplay = (isRootItem ? 1 : (matchedCommand.MatchedCommandId - (int) DynamicMenuPackageGuids.cmdidMyCommand) + 1);  
  
        matchedCommand.Text = dte2.Solution.Projects.Item(indexForDisplay).Name;  
  
        Array startupProjects = (Array)dte2.Solution.SolutionBuild.StartupProjects;  
        string startupProject = System.IO.Path.GetFileNameWithoutExtension((string)startupProjects.GetValue(0));  
  
        // Check the command if it isn't checked already selected  
        matchedCommand.Checked = (matchedCommand.Text == startupProject);  
  
        // Clear the ID because we are done with this item.  
        matchedCommand.MatchedCommandId = 0;  
    }  
    ```  
  
## <a name="implementing-the-command-id-match-predicate"></a>명령 ID 일치 조건자를 구현합니다.  
  
1.  이제 일치 조건자를 구현 합니다. 두 가지를 확인 해야: 먼저 여부 명령 ID가 잘못 되었습니다 (이 선언 된 명령 ID 보다 크거나 같음), 두 번째 (이 솔루션의 프로젝트 수보다 작은) 가능한 프로젝트를 지정 하는지 여부를 합니다.  
  
    ```csharp  
    private bool IsValidDynamicItem(int commandId)  
    {  
        // The match is valid if the command ID is >= the id of our root dynamic start item   
        // and the command ID minus the ID of our root dynamic start item  
        // is less than or equal to the number of projects in the solution.  
        return (commandId >= (int)DynamicMenuPackageGuids.cmdidMyCommand) && ((commandId - (int)DynamicMenuPackageGuids.cmdidMyCommand) < dte2.Solution.Projects.Count);  
    }  
    ```  
  
## <a name="setting-the-vspackage-to-load-only-when-a-solution-has-multiple-projects"></a>솔루션에 여러 프로젝트가 있는 경우에 로드 하기 위해 VSPackage를 설정 합니다.  
 때문에 **시작 프로젝트 설정** 명령 타당성을 활성 솔루션에 둘 이상의 프로젝트를 자동으로 로드 하 여 사용할 경우에만 VSPackage를 설정할 수 있습니다. 사용 하면 <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> UI 컨텍스트와 함께 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids.SolutionHasMultipleProjects>합니다. DynamicMenuPackage.cs 파일에서 DynamicMenuPackage 클래스에 다음 특성을 추가 합니다.  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]  
[ProvideMenuResource("Menus.ctmenu", 1)]  
[ProvideAutoLoad(UIContextGuids.SolutionHasMultipleProjects)]  
[Guid(DynamicMenuPackage.PackageGuidString)]  
public sealed class DynamicMenuItemsPackage : Package  
{}  
```  
  
## <a name="testing-the-set-startup-project-command"></a>테스트 시작 프로젝트 설정 명령  
 이제 코드를 테스트할 수 있습니다.  
  
1.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스 표시 되어야 합니다.  
  
2.  실험적 인스턴스를 여러 개의 프로젝트가 포함 된 솔루션을 엽니다.  
  
     에 있는 화살표 아이콘을 표시 됩니다는 **솔루션 탐색기** 도구 모음입니다. 확장 하면 솔루션의 다른 프로젝트를 나타내는 메뉴 항목이 표시 됩니다.  
  
3.  프로젝트 중 하나를 확인할 때 시작 프로젝트 됩니다.  
  
4.  솔루션을 닫거나 하나의 프로젝트만 포함 된 솔루션을 열고 도구 모음 아이콘이 사라집니다.  
  
## <a name="see-also"></a>참고 항목  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)   
 [VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)