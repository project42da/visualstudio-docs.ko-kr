---
title: "하위 메뉴에 추가 | Microsoft Docs"
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
  - "상황에 맞는 메뉴"
  - "하위 메뉴, 연계"
  - "연계 하위 메뉴"
  - "메뉴, 연계 하위 메뉴 만들기"
ms.assetid: 692600cb-d052-40e2-bdae-4354ae7c6c84
caps.latest.revision: 43
caps.handback.revision: 43
ms.author: "gregvanl"
manager: "ghogen"
---
# 하위 메뉴에 추가
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

데모를 기반으로 하는이 연습에서는 [Visual Studio 메뉴 모음에 메뉴를 추가합니다.](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md) 는 하위 메뉴에 추가 하는 방법을 표시 하 여는 **TestMenu** 메뉴.  
  
 하위 메뉴가 다른 메뉴에 표시 되는 보조 메뉴입니다. 하위 메뉴 이름 뒤에 오는 화살표로 식별할 수 있습니다. 이름을 누르면 하위 메뉴 및 명령을 표시 됩니다.  
  
 이 연습에서는 Visual Studio 메뉴 모음에서 메뉴에는 하위 메뉴를 만들고 하위 메뉴에서 새 명령을 설정 합니다. 이 연습에는 또한 새 명령을 구현합니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## 하위 메뉴에 추가  
  
1.  단계에 따라 [Visual Studio 메뉴 모음에 메뉴를 추가합니다.](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md) 프로젝트 및 메뉴 항목을 만듭니다. 이 연습의 단계에에서는 VSIX 프로젝트의 이름 이라고 가정 `TopLevelMenu`합니다.  
  
2.  TestCommandPackage.vsct를 엽니다. 에 `<Symbols>` 섹션을 추가 `<IDSymbol>` 하위 그룹 및에서 모든 명령에 대 한 하위 메뉴에 대 한 요소는 `<GuidSymbol>` "guidTopLevelMenuCmdSet." 라는 노드 이 포함 하는 동일한 노드는 `<IDSymbol>` 최상위 메뉴에 대 한 요소입니다.  
  
    ```xml  
    <IDSymbol name="SubMenu" value="0x1100"/>  
    <IDSymbol name="SubMenuGroup" value="0x1150"/>  
    <IDSymbol name="cmdidTestSubCommand" value="0x0105"/>  
    ```  
  
3.  새로 만든된 하위 메뉴에 추가 된 `<Menus>` 섹션입니다.  
  
    ```xml  
    <Menu guid="guidTestCommandPackageCmdSet" id="SubMenu" priority="0x0100" type="Menu">  
        <Parent guid="guidTestCommandPackageCmdSet" id="MyMenuGroup"/>  
        <Strings>  
            <ButtonText>Sub Menu</ButtonText>  
            <CommandName>Sub Menu</CommandName>  
        </Strings>  
    </Menu>  
    ```  
  
     생성 된 메뉴 그룹을 지정 하는 부모 GUID\/ID 쌍 [Visual Studio 메뉴 모음에 메뉴를 추가합니다.](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md), 최상위 메뉴의 자식 임을 합니다.  
  
4.  2 단계에서 정의 된 메뉴 그룹 추가 `<Groups>` 섹션 및 하위 메뉴의 자식으로 만듭니다.  
  
    ```xml  
    <Group guid="guidTestCommandPackageCmdSet" id="SubMenuGroup" priority="0x0000">  
        <Parent guid="guidTestCommandPackageCmdSet" id="SubMenu"/>  
    </Group>  
    ```  
  
5.  새 추가 `<Button>` 요소는 `<Buttons>` 하위 메뉴 항목으로 2 단계에서 만든 명령을 정의 하는 섹션입니다.  
  
    ```xml  
    <Button guid="guidTestCommandPackageCmdSet" id="cmdidTestSubCommand" priority="0x0000" type="Button">  
        <Parent guid="guidTestCommandPackageCmdSet" id="SubMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic2" />  
        <Strings>  
           <CommandName>cmdidTestSubCommand</CommandName>  
           <ButtonText>Test Sub Command</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
6.  솔루션을 빌드하고 디버깅을 시작 합니다. 실험적 인스턴스에서 표시 됩니다.  
  
7.  클릭 **TestMenu** 라는 새 하위 메뉴를 보려면 **하위 메뉴**합니다. 클릭 **하위 메뉴** 하위 메뉴를 열고 새 명령을 참조 **테스트 하위 명령**합니다. 클릭 하면 확인 **테스트 하위 명령** 는 아무 작업도 수행 합니다.  
  
## 명령 추가  
  
1.  TestCommand.cs를 열고 기존 명령 id입니다. 한 후 다음 명령 ID를 추가 합니다.  
  
    ```c#  
    public const int cmdidTestSubCmd = 0x105;  
    ```  
  
2.  하위 명령을 추가 합니다. 명령 생성자를 찾습니다. 에 대 한 호출 바로 뒤에 다음 줄을 추가 `AddCommand` 메서드.  
  
    ```c#  
    CommandID subCommandID = new CommandID(CommandSet, (int)TestCommandPackageGuids.cmdidTestSubCmd);  
    MenuCommand subItem = new MenuCommand(  
        new EventHandler(SubItemCallback), subCommandID);  
    commandService.AddCommand(subItem);  
  
    ```  
  
     `SubItemCallback` 명령 처리기는 나중에 정의 됩니다. 생성자는 이제 다음과 같이 표시 됩니다.  
  
    ```c#  
    private TestCommand(Package package)  
            {  
                if (package == null)  
                {  
                    throw new ArgumentNullException("package");  
                }  
  
                this.package = package;  
  
                OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
                if (commandService != null)  
                {  
                    var menuCommandID = new CommandID(CommandSet, CommandId);  
                    var menuItem = new MenuCommand(this.MenuItemCallback, menuCommandID);  
                    commandService.AddCommand(menuItem);  
                    CommandID subCommandID = new CommandID(CommandSet, cmdidTestSubCmd);  
                    MenuCommand subItem = new MenuCommand(  
                        new EventHandler(SubItemCallback), subCommandID);  
                    commandService.AddCommand(subItem);  
                }  
    ```  
  
3.  SubItemCallback\(\)를 추가 합니다. 이 방법은 하위 메뉴에 새 명령을 클릭할 때 호출 됩니다.  
  
    ```c#  
    private void SubItemCallback(object sender, EventArgs e)  
    {  
        IVsUIShell uiShell = (IVsUIShell)this.ServiceProvider.GetService(  
            typeof(SVsUIShell));  
        Guid clsid = Guid.Empty;  
        int result;  
        uiShell.ShowMessageBox(  
            0,  
            ref clsid,  
            "TestCommand",  
            string.Format(CultureInfo.CurrentCulture,  
            "Inside TestCommand.SubItemCallback()",  
            this.ToString()),  
            string.Empty,  
            0,  
            OLEMSGBUTTON.OLEMSGBUTTON_OK,  
            OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST,  
            OLEMSGICON.OLEMSGICON_INFO,  
            0,  
            out result);  
    }  
    ```  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 나타납니다.  
  
5.  에 **TestMenu** 메뉴를 클릭 하 여 **하위 메뉴** 클릭 하 고 **테스트 하위 명령**. 메시지 상자 표시 하 고 "테스트 명령 내 TestCommand.SubItemCallback\(\)" 텍스트를 표시 해야 합니다.  
  
## 참고 항목  
 [Visual Studio 메뉴 모음에 메뉴를 추가합니다.](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)   
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)