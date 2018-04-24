---
title: 도구 창에서 바로 가기 메뉴를 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- context menus, adding to tool windows
- menus, context menus
- shortcut menus, adding to tool windows
- tool windows, adding context menus
ms.assetid: 50234537-9e95-4b7e-9cb7-e5cf26d6e9d2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e4b36800ea291c6f1bc0948a46b67c4e3549f349
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="adding-a-shortcut-menu-in-a-tool-window"></a>도구 창에서 바로 가기 메뉴를 추가합니다.
이 연습에서는 도구 창에서 바로 가기 메뉴를 넣습니다. 바로 가기 메뉴에 단추, 텍스트 상자 또는 창 배경 단추로 클릭할 때 표시 되는 메뉴가입니다. 바로 가기 메뉴에 명령을 다른 메뉴나 도구 모음에서 명령과 동일 하 게 동작 합니다. 바로 가기 메뉴를 지원 하려면.vsct 파일에서 지정 하 고 마우스 오른쪽 단추로 클릭에 대 한 응답에 표시 합니다.  
  
 도구 창에서 상속 되는 사용자 지정 도구 창 클래스에 WPF 사용자 정의 컨트롤 이루어져 <xref:Microsoft.VisualStudio.Shell.ToolWindowPane>합니다.  
  
 이 연습에.vsct 파일의 메뉴 항목을 선언 하 고 다음 관리 되는 패키지 프레임 워크를 사용 하 여 도구 창을 정의 하는 클래스에 구현 하 여 Visual Studio 메뉴와 바로 가기 메뉴를 만드는 방법을 보여 줍니다. 이 방법은 Visual Studio 명령, UI 요소 및 자동화 개체 모델에 대 한 액세스를 지원합니다.  
  
 또는 바로 가기 메뉴에 Visual Studio 기능을 액세스 하지 않는 경우 있습니다 사용할 수는 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 사용자 정의 컨트롤에 있는 XAML 요소의 속성입니다. 자세한 내용은 참조 [ContextMenu](/dotnet/framework/wpf/controls/contextmenu)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-the-tool-window-shortcut-menu-package"></a>도구 창 바로 가기 메뉴 패키지 만들기  
  
1.  라는 VSIX 프로젝트를 `TWShortcutMenu` 라는 도구 창이 서식 파일을 추가 하 고 **ShortcutMenu** 를 합니다. 도구 창을 만드는 방법에 대 한 자세한 내용은 참조 [도구 창을 사용 된 확장을 만드는](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
## <a name="specifying-the-shortcut-menu"></a>바로 가기 메뉴를 지정합니다.  
 이 연습에 표시 된 것의 사용자 수와 같은 바로 가기 메뉴 도구 창의 배경을 채우는 데 사용 되는 색의 목록에서 선택 합니다.  
  
1.  ShortcutMenuPackage.vsct, guidShortcutMenuPackageCmdSet, 라는 GuidSymbol 요소에서 찾아 바로 가기 메뉴, 바로 가기 메뉴 그룹 및 메뉴 옵션을 선언 합니다. GuidSymbol 요소는 이제 다음과 같이 표시 됩니다.  
  
    ```xml  
    <GuidSymbol name="guidShortcutMenuPackageCmdSet" value="{00000000-0000-0000-0000-0000}"> // your GUID here  
        <IDSymbol name="ShortcutMenuCommandId" value="0x0100" />  
        <IDSymbol name="ColorMenu" value="0x1000"/>  
        <IDSymbol name="ColorGroup" value="0x1100"/>  
        <IDSymbol name="cmdidRed" value="0x102"/>  
        <IDSymbol name="cmdidYellow" value="0x103"/>  
        <IDSymbol name="cmdidBlue" value="0x104"/>  
    </GuidSymbol>  
    ```  
  
2.  단추 요소 바로 앞 메뉴 요소를 만들고에 바로 가기 메뉴를 정의 합니다.  
  
    ```vb  
    <Menus>  
      <Menu guid="guidShortcutMenuPackageCmdSet" id="ColorMenu" type="Context">  
        <Strings>  
          <ButtonText>Color change</ButtonText>  
          <CommandName>ColorChange</CommandName>  
        </Strings>  
      </Menu>  
    </Menus>  
    ```  
  
     바로 가기 메뉴 메뉴 또는 도구 모음의 일부 이기 때문에 부모 릴리스 레코드가 되지 않습니다.  
  
3.  바로 가기 메뉴 항목을 포함 하는 그룹 요소가 포함 된 그룹 요소를 생성 하 고 바로 가기 메뉴 그룹 연결 합니다.  
  
    ```xml  
    <Groups>  
        <Group guid="guidShortcutMenuPackageCmdSet" id="ColorGroup">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorMenu"/>  
        </Group>  
    </Groups>  
    ```  
  
4.  단추 요소에 바로 가기 메뉴에 표시 되는 각 명령을 정의 합니다. 단추 요소가 다음과 같이 표시 됩니다.  
  
    ```xml  
    <Buttons>  
        <Button guid="guidShortcutMenuPackageCmdSet" id="ShortcutMenuCommandId" priority="0x0100" type="Button">  
            <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
            <Icon guid="guidImages" id="bmpPic1" />  
            <Strings>  
                <ButtonText>ShortcutMenu</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidRed" priority="1" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Red</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidYellow" priority="3" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Yellow</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidBlue" priority="5" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Blue</ButtonText>  
            </Strings>  
        </Button>  
    </Buttons>  
    ```  
  
5.  ShortcutMenuCommand.cs, GUID, 바로 가기 메뉴 및 메뉴 항목을 설정 하는 명령에 대 한 정의 추가 합니다.  
  
    ```csharp  
    public const string guidShortcutMenuPackageCmdSet = "00000000-0000-0000-0000-00000000"; // your GUID will differ  
    public const int ColorMenu = 0x1000;  
    public const int cmdidRed = 0x102;  
    public const int cmdidYellow = 0x103;  
    public const int cmdidBlue = 0x104;  
    ```  
  
     이들은 ShortcutMenuPackage.vsct 파일의 기호 섹션에 정의 된 동일한 명령 Id입니다. 상황에 맞는 그룹 포함 되지 않습니다 여기는.vsct 파일에만 필요 하므로.  
  
## <a name="implementing-the-shortcut-menu"></a>바로 가기 메뉴를 구현합니다.  
 이 섹션에는 바로 가기 메뉴와 해당 명령을 구현합니다.  
  
1.  ShortcutMenu.cs, 도구 창 메뉴 명령 서비스를 가져올 수 있지만 포함 된 컨트롤 수 없습니다. 다음 단계에는 메뉴 명령 서비스를 사용자 정의 컨트롤에 사용할 수 있도록 하는 방법을 보여 줍니다.  
  
2.  ShortcutMenu.cs에 다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    using System.ComponentModel.Design;  
    ```  
  
3.  메뉴 명령 서비스를 가져오고 메뉴 명령 서비스는 있는 생성자에 전달 하는 컨트롤을 추가 하려면 도구 창 initialize () 메서드를 재정의:  
  
    ```csharp  
    protected override void Initialize()  
    {  
        var commandService = (OleMenuCommandService)GetService(typeof(IMenuCommandService));  
        Content = new ShortcutMenuControl(commandService);  
    }  
    ```  
  
4.  ShortcutMenu 도구 창 생성자에서 컨트롤을 추가 하는 행을 제거 합니다. 생성자는 이제 다음과 같이 표시 됩니다.  
  
    ```csharp  
    public ShortcutMenu() : base(null)  
    {  
        this.Caption = "ShortcutMenu";  
        this.BitmapResourceID = 301;  
        this.BitmapIndex = 1;  
    }  
    ```  
  
5.  ShortcutMenuControl.xaml.cs에서 메뉴 명령 서비스에 대 한 전용 필드를 추가 하 고 메뉴 명령 서비스를 수행 하는 제어 생성자를 변경 합니다. 다음 메뉴 명령 서비스를 사용 하 여 상황에 맞는 메뉴 명령을 추가할 수 있습니다. 다음 코드 처럼 ShortcutMenuControl 생성자는 이제 찾아야 합니다. 명령 처리기는 나중에 정의 됩니다.  
  
    ```csharp  
    public ShortcutMenuControl(OleMenuCommandService service)  
    {  
        this.InitializeComponent();  
        commandService = service;  
  
        if (null !=commandService)  
        {  
            // Create an alias for the command set guid.  
            Guid guid = new Guid(ShortcutMenuCommand.guidShortcutMenuPackageCmdSet);  
  
            // Create the command IDs.   
            var red = new CommandID(guid, ShortcutMenuCommand.cmdidRed);  
            var yellow = new CommandID(guid, ShortcutMenuCommand.cmdidYellow);  
            var blue = new CommandID(guid, ShortcutMenuCommand.cmdidBlue);  
  
            // Add a command for each command ID.  
            commandService.AddCommand(new MenuCommand(ChangeColor, red));  
            commandService.AddCommand(new MenuCommand(ChangeColor, yellow));  
            commandService.AddCommand(new MenuCommand(ChangeColor, blue));  
        }  
    }  
    ```  
  
6.  ShortcutMenuControl.xaml에 추가 <xref:System.Windows.UIElement.MouseRightButtonDown> 최상위 이벤트 <xref:System.Windows.Controls.UserControl> 요소입니다. XAML 파일은 이제 다음과 같이 표시 됩니다.  
  
    ```vb  
    <UserControl x:Class="TWShortcutMenu.ShortcutMenuControl"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
            Background="{DynamicResource VsBrush.Window}"  
            Foreground="{DynamicResource VsBrush.WindowText}"  
            mc:Ignorable="d"  
            d:DesignHeight="300" d:DesignWidth="300"  
            Name="MyToolWindow"  
            MouseRightButtonDown="MyToolWindow_MouseRightButtonDown">  
        <Grid>  
            <StackPanel Orientation="Vertical">  
                <TextBlock Margin="10" HorizontalAlignment="Center">ShortcutMenu</TextBlock>  
            </StackPanel>  
        </Grid>  
    </UserControl>  
    ```  
  
7.  ShortcutMenuControl.xaml.cs, 이벤트 처리기에 대 한 스텁을 추가 합니다.  
  
    ```csharp  
    private void MyToolWindow_MouseRightButtonDown(object sender, MouseButtonEventArgs e)  
    {  
    . . .  
    }  
    ```  
  
8.  다음 추가 문을 사용 하 여 동일한 파일에:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    using System.ComponentModel.Design;  
    using System;  
    using System.Windows.Input;  
    using System.Windows.Media;  
    ```  
  
9. 구현 된 `MyToolWindowMouseRightButtonDown` 다음과 같이 이벤트입니다.  
  
    ```csharp  
    private void MyToolWindow_MouseRightButtonDown(object sender, MouseButtonEventArgs e)  
    {  
        if (null != commandService)  
        {  
            CommandID menuID = new CommandID(  
                new Guid(ShortcutMenuCommand.guidShortcutMenuPackageCmdSet),  
                ShortcutMenuCommand.ColorMenu);  
            Point p = this.PointToScreen(e.GetPosition(this));  
            commandService.ShowContextMenu(menuID, (int)p.X, (int)p.Y);  
        }  
    }  
    ```  
  
     그렇기 때문에 <xref:System.ComponentModel.Design.CommandID> 바로 가기 메뉴에 대 한 개체 마우스 클릭 위치를 식별 하 고 바로 가기 메뉴를 사용 하 여 해당 위치에 열립니다는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService.ShowContextMenu%2A> 메서드.  
  
10. 명령 처리기를 구현 합니다.  
  
    ```csharp  
    private void ChangeColor(object sender, EventArgs e)  
    {  
        var mc = sender as MenuCommand;  
  
        switch (mc.CommandID.ID)  
        {  
            case ShortcutMenuCommand.cmdidRed:  
                MyToolWindow.Background = Brushes.Red;  
                break;  
            case ShortcutMenuCommand.cmdidYellow:  
                MyToolWindow.Background = Brushes.Yellow;  
                break;  
            case ShortcutMenuCommand.cmdidBlue:  
                MyToolWindow.Background = Brushes.Blue;  
                break;  
        }  
    }  
    ```  
  
     단 하나의 메서드를 식별 하 여 모든 메뉴 항목에 대 한 이벤트를 처리 하는 경우에 <xref:System.ComponentModel.Design.CommandID> 하 고 그에 따라 명령 프롬프트 창의 배경색을 설정 합니다. 메뉴 항목에 관련 되지 않은 명령으로 포함 하는 경우 각 명령에 대 한 별도 이벤트 처리기를 만든 것입니다.  
  
## <a name="testing-the-tool-window-features"></a>도구 창 기능 테스트  
  
1.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
2.  실험적 인스턴스에서 클릭 **보기 / 다른 창**, 클릭 하 고 **ShortcutMenu**합니다. 이 도구 창을 표시 되어야 합니다.  
  
3.  도구 창의 본문을 마우스 오른쪽 단추로 클릭 합니다. 색 목록이 있는 바로 가기 메뉴가 표시 됩니다.  
  
4.  바로 가기 메뉴에서 색을 클릭 합니다. 도구 창 배경 색을 선택 된 색으로 변경 되어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)   
 [서비스 사용 및 제공](../extensibility/using-and-providing-services.md)