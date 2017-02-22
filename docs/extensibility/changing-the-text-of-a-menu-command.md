---
title: "메뉴 명령 텍스트를 변경합니다. | Microsoft Docs"
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
  - "메뉴, 텍스트 변경"
  - "텍스트, 메뉴"
  - "명령, 텍스트 변경"
ms.assetid: 5cb676a0-c6e2-47e5-bd2b-133dc8842e46
caps.latest.revision: 25
caps.handback.revision: 25
ms.author: "gregvanl"
manager: "ghogen"
---
# 메뉴 명령 텍스트를 변경합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다음 단계를 사용 하 여 메뉴 명령의 텍스트 레이블을 변경 하는 방법을 보여 줍니다는 <xref:System.ComponentModel.Design.IMenuCommandService> 서비스입니다.  
  
## IMenuCommandService 사용 하 여 메뉴 명령 레이블을 변경합니다.  
  
1.  라는 이름의 VSIX 프로젝트 `MenuText` 메뉴 명령을 사용 하 여 명명 된 **ChangeMenuText**합니다. 자세한 내용은 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)을 참조하세요.  
  
2.  .Vstc 파일에서 추가 된 `TextChanges` 다음 예와에서 같이 사용자 메뉴 명령에 플래그를 지정 합니다.  
  
    ```xml  
    <Button guid="guidChangeMenuTextPackageCmdSet" id="ChangeMenuTextId" priority="0x0100" type="Button">  
        <Parent guid="guidChangeMenuTextPackageCmdSet" id="MyMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <CommandFlag>TextChanges</CommandFlag>  
        <Strings>  
            <ButtonText>Invoke ChangeMenuText</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
3.  ChangeMenuText.cs 파일에서 메뉴 명령을 표시 되기 전에 호출 되는 이벤트 처리기를 만듭니다.  
  
    ```c#  
    private void OnBeforeQueryStatus(object sender, EventArgs e)  
    {  
        var myCommand = sender as OleMenuCommand;  
        if (null != myCommand)  
        {  
            myCommand.Text = "New Text";  
                    }  
    }  
    ```  
  
     변경 하 여이 메서드는 메뉴 명령 상태를 업데이트할 수도 있습니다는 <xref:System.ComponentModel.Design.MenuCommand.Visible%2A>, <xref:System.ComponentModel.Design.MenuCommand.Checked%2A>, 및 <xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> 속성에는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 개체입니다.  
  
4.  ChangeMenuText 생성자에서 바꿉니다 원래 명령 배치 하 고 초기화 코드를 만드는 코드는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> \(대신 `MenuCommand`\) 메뉴 명령을 나타냅니다를 추가 하는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> 이벤트 처리기 및 메뉴 명령을 메뉴 명령 서비스를 제공 합니다.  
  
     그 모양을 다음과 같습니다.  
  
    ```c#  
    private ChangeMenuText(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
            EventHandler eventHandler = this.ShowMessageBox;  
            OleMenuCommand menuItem = new OleMenuCommand(ShowMessageBox, menuCommandID);  
            menuItem.BeforeQueryStatus +=  
                new EventHandler(OnBeforeQueryStatus);  
            commandService.AddCommand(menuItem);  
        }  
    }  
    ```  
  
5.  프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스가 표시 됩니다.  
  
6.  에 **도구** 메뉴 표시 되어야 라는 명령을 **ChangeMenuText 호출**합니다.  
  
7.  명령을 클릭 합니다. MenuItemCallback가 호출 된 알리는 메시지 상자가 표시 됩니다. 메시지 상자를 닫고 표시 도구 메뉴 명령의 이름입니다. 이제 인지 **새 텍스트**합니다.