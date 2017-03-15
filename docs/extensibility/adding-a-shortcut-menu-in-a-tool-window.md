---
title: "도구 창에서 바로 가기 메뉴를 추가 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- context menus, adding to tool windows
- menus, context menus
- shortcut menus, adding to tool windows
- tool windows, adding context menus
ms.assetid: 50234537-9e95-4b7e-9cb7-e5cf26d6e9d2
caps.latest.revision: 37
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: ab921bec73528be7207baebdf9cb31885e2253fd
ms.lasthandoff: 02/22/2017

---
# <a name="adding-a-shortcut-menu-in-a-tool-window"></a>도구 창의 바로 가기 메뉴를 추가합니다.
이 연습에서는 도구 창의 바로 가기 메뉴를 넣습니다. 바로 가기 메뉴에는 단추, 텍스트 상자 또는 창 배경 단추로 클릭할 때 표시 되는 메뉴가입니다. 바로 가기 메뉴의 명령을 다른 메뉴나 도구 모음에서 명령으로 동일 하 게 작동 합니다. 바로 가기 메뉴를 지원 하기 위해.vsct 파일에 지정 하 고 마우스 오른쪽 단추로 클릭에 대 한 응답에 표시 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.ToolWindowPane>.</xref:Microsoft.VisualStudio.Shell.ToolWindowPane> 에서 상속 되는 사용자 지정 도구 창 클래스에는 WPF 사용자 정의 컨트롤의 도구 창으로 구성 됩니다.  
  
 이 연습에서는.vsct 파일에서 메뉴 항목을 선언 하 고 관리 하는 패키지 프레임 워크를 사용 하 여 도구 창을 정의 하는 클래스에 구현 하 여 Visual Studio 메뉴, 바로 가기 메뉴를 만드는 방법을 보여 줍니다. 이 방법을 사용 하면 Visual Studio 명령, UI 요소 및 자동화 개체 모델에 대 한 액세스를 용이해 집니다.  
  
 또는 바로 가기 메뉴에 Visual Studio 기능을 액세스 하지 않는 경우 사용할 수 있습니다는 <xref:System.Windows.FrameworkElement.ContextMenu%2A>사용자 정의 컨트롤에 있는 XAML 요소의 속성입니다.</xref:System.Windows.FrameworkElement.ContextMenu%2A> 자세한 내용은 참조 [ContextMenu](http://msdn.microsoft.com/Library/2f40b2bb-b702-4706-9fc4-10bcfd7cc35d)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-the-tool-window-shortcut-menu-package"></a>도구 창 바로 가기 메뉴 패키지 만들기  
  
1.  라는 VSIX 프로젝트를 만듭니다 `TWShortcutMenu` 라는 도구 창 서식 파일을 추가 하 고 **ShortCutMenu** 에 있습니다. 도구 창을 만드는 방법에 대 한 자세한 내용은 참조 [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
## <a name="specifying-the-shortcut-menu"></a>바로 가기 메뉴를 지정합니다.  
 이 연습에 나와 있는 것 사용자 수와 같은 바로 가기 메뉴 도구 창 배경을 채우는 데 사용 되는 색의 목록에서 선택 합니다.  
  
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
  
     바로 가기 메뉴는 메뉴 또는 도구 모음에 대 한 부분이 아니기 때문에 부모가 없는지 않습니다.  
  
3.  그룹 요소 바로 가기 메뉴 항목을 포함 하는 그룹 요소를 생성 하 고 바로 가기 메뉴 그룹 연결 합니다.  
  
    ```xml  
    <Groups>  
        <Group guid="guidShortcutMenuPackageCmdSet" id="ColorGroup">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorMenu"/>  
        </Group>  
    </Groups>  
    ```  
  
4.  단추 요소에 바로 가기 메뉴에 표시 되는 각 명령을 정의 합니다. 단추 요소는 다음과 같습니다.  
  
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
  
5.  ShortcutMenuPackageGuids.cs, GUID, 바로 가기 메뉴 및 메뉴 항목을 설정 하는 명령에 대 한 정의 추가 합니다.  
  
    ```c#  
    public const string guidShortcutMenuPackageCmdSet = "00000000-0000-0000-0000-00000000"; // your GUID will differ  
    public const int ColorMenu = 0x1000;  
    public const int cmdidRed = 0x102;  
    public const int cmdidYellow = 0x103;  
    public const int cmdidBlue = 0x104;  
    ```  
  
     이들은 ShortcutMenuPackage.vsct 파일의 Symbols 섹션에 정의 된 동일한 명령 Id입니다. 컨텍스트 그룹이 포함 되지 않습니다 여기.vsct 파일에만 필요 하므로.  
  
## <a name="implementing-the-shortcut-menu"></a>바로 가기 메뉴를 구현합니다.  
 이 섹션에는 바로 가기 메뉴 및 명령을 구현합니다.  
  
1.  ShortcutMenu.cs, 도구 창 메뉴 명령 서비스를 가져올 수 있지만 포함 된 컨트롤 수 없습니다. 다음 단계에는 메뉴 명령 서비스를 사용자 정의 컨트롤에 사용할 수 있도록 하는 방법을 보여 줍니다.  
  
2.  ShortcutMenu.cs에서 다음 추가 문을 사용 하 여:  
  
    ```c#  
    using Microsoft.VisualStudio.Shell;  
    using System.ComponentModel.Design;  
    ```  
  
3.  메뉴 명령 서비스를 가져오고 메뉴 명령 서비스는 따라 비춰지는 전달 컨트롤을 추가 하는 도구 창 initialize () 메서드를 재정의 합니다.  
  
    ```c#  
    protected override void Initialize()  
    {  
        commandService = (OleMenuCommandService)GetService(typeof(IMenuCommandService));  
        Content = new ShortcutMenuControl(commandService);  
    }  
    ```  
  
4.  ShortcutMenu 도구 창 생성자에서 컨트롤을 추가 하는 줄을 제거 합니다. 생성자는 이제 다음과 같이 표시 됩니다.  
  
    ```c#  
    public ShortcutMenu() : base(null)  
    {  
        this.Caption = "ShortcutMenu";  
        this.BitmapResourceID = 301;  
        this.BitmapIndex = 1;  
    }  
    ```  
  
5.  ShortcutMenuControl.xaml.cs, 메뉴 명령 서비스에 대 한 private 필드를 추가 하 고 컨트롤 생성자 메뉴 명령 서비스를 변경 합니다. 다음 메뉴 명령 서비스를 사용 하 여 상황에 맞는 메뉴 명령을 추가할 수 있습니다. ShortcutMenuControl 생성자는 이제 다음 코드 처럼 보여야 합니다. 명령 처리기는 나중에 정의 됩니다.  
  
    ```c#  
    public ShortcutMenuControl(OleMenuCommandService service)  
    {  
        this.InitializeComponent();  
        commandService = service;  
  
        if (null !=commandService)  
        {  
            // Create an alias for the command set guid.  
            Guid guid = new Guid(ShortcutMenuPackageGuids.guidShortcutMenuPackageCmdSet);  
  
            // Create the command IDs.   
            var red = new CommandID(guid, ShortcutMenuPackageGuids.cmdidRed);  
            var yellow = new CommandID(guid, ShortcutMenuPackageGuids.cmdidYellow);  
            var blue = new CommandID(guid, ShortcutMenuPackageGuids.cmdidBlue);  
  
            // Add a command for each command ID.  
            commandService.AddCommand(new MenuCommand(ChangeColor, red));  
            commandService.AddCommand(new MenuCommand(ChangeColor, yellow));  
            commandService.AddCommand(new MenuCommand(ChangeColor, blue));  
        }  
    }  
    ```  
  
6.  ShortcutMenuControl.xaml, 추가 된 <xref:System.Windows.UIElement.MouseRightButtonDown>최상위 수준에 대 한 이벤트 <xref:System.Windows.Controls.UserControl>요소.</xref:System.Windows.Controls.UserControl> </xref:System.Windows.UIElement.MouseRightButtonDown> XAML 파일이 이제 다음과 같습니다.  
  
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
  
    ```c#  
    private void MyToolWindow_MouseRightButtonDown(object sender, MouseButtonEventArgs e)  
    {  
    . . .  
    }  
    ```  
  
8.  다음 코드를 추가 문을 사용 하 여 동일한 파일에 있습니다.  
  
    ```c#  
    using Microsoft.VisualStudio.Shell;  
    using System.ComponentModel.Design;  
    using System;  
    using System.Windows.Input;  
    using System.Windows.Media;  
    ```  
  
9. 구현 된 `MyToolWindowMouseRightButtonDown` 다음과 같이 이벤트로 합니다.  
  
    ```c#  
    private void MyToolWindow_MouseRightButtonDown(object sender, MouseButtonEventArgs e)  
    {  
        if (null != commandService)  
        {  
            CommandID menuID = new CommandID(  
                new Guid(ShortcutMenuPackageGuids.guidShortcutMenuPackageCmdSet),  
                ShortcutMenuPackageGuids.ColorMenu);  
            Point p = this.PointToScreen(e.GetPosition(this));  
            commandService.ShowContextMenu(menuID, (int)p.X, (int)p.Y);  
        }  
    }  
    ```  
  
     그렇기 때문에 한 <xref:System.ComponentModel.Design.CommandID>바로 가기 메뉴에 대 한 개체의 마우스 클릭의 위치를 식별 하 고 사용 하 여 해당 위치에 바로 가기 메뉴를 엽니다는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService.ShowContextMenu%2A>메서드.</xref:Microsoft.VisualStudio.Shell.OleMenuCommandService.ShowContextMenu%2A> </xref:System.ComponentModel.Design.CommandID>  
  
10. 명령 처리기를 구현 합니다.  
  
    ```c#  
    private void ChangeColor(object sender, EventArgs e)  
    {  
        var mc = sender as MenuCommand;  
  
        switch (mc.CommandID.ID)  
        {  
            case ShortcutMenuPackageGuids.cmdidRed:  
                MyToolWindow.Background = Brushes.Red;  
                break;  
            case ShortcutMenuPackageGuids.cmdidYellow:  
                MyToolWindow.Background = Brushes.Yellow;  
                break;  
            case ShortcutMenuPackageGuids.cmdidBlue:  
                MyToolWindow.Background = Brushes.Blue;  
                break;  
        }  
    }  
    ```  
  
     단 하나의 메서드를 식별 하 여 모든 메뉴 항목에 대 한 이벤트를 처리 하는 경우에 <xref:System.ComponentModel.Design.CommandID>하 고 그에 따라 배경색을 설정 합니다.</xref:System.ComponentModel.Design.CommandID> 메뉴 항목에는 관련 되지 않은 명령을 포함 되어 있던을 하는 경우 각 명령에 대 한 별도 이벤트 처리기를 만들어졌을 것입니다.  
  
## <a name="testing-the-tool-window-features"></a>테스트 도구 창 기능  
  
1.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
2.  실험적 인스턴스를 클릭 **보기 / 다른 창**를 클릭 하 고 **ShortcutMenu**합니다. 이렇게 하면 도구 창을 표시 되어야 합니다.  
  
3.  도구 창의 본문을 마우스 오른쪽 단추로 클릭 합니다. 색 목록이 있는 바로 가기 메뉴를 표시 합니다.  
  
4.  바로 가기 메뉴에서 색을 클릭 합니다. 도구 창 배경 색을 선택 된 색으로 변경 되어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)   
 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)
