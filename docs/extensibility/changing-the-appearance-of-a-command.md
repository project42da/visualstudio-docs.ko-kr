---
title: "명령의 모양 변경 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령에 모양 변경"
  - "메뉴 명령, 모양 변경"
  - "메뉴, 명령 모양 변경"
ms.assetid: da2474fa-f92d-4e9e-b8bf-67c61bf249c2
caps.latest.revision: 23
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 23
---
# 명령의 모양 변경
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

명령의 모양을 변경 하 여 사용자 피드백을 제공할 수 있습니다. 예를 들어 명령을 사용할 수 없으면 다른 모양으로 좋습니다. 명령을 사용할 수 없거나, 숨기기 또는 숨겨진 기능을 표시 또는 확인 하거나 메뉴에서 선택 취소 합니다.  
  
 명령의 모양을 변경 하려면 이러한 작업 중 하나를 수행 합니다.  
  
-   명령 테이블 파일에서 명령 정의에서 적절 한 플래그를 지정 합니다.  
  
-   사용 하 여 <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> 서비스입니다.  
  
-   구현 된 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스 및 원시 명령 개체를 수정 합니다.  
  
 다음 단계를 찾아 관리 하는 패키지 프레임 워크 \(MPF\)를 사용 하 여 명령의 모양을 업데이트 하는 방법을 보여 줍니다.  
  
### 메뉴 명령의 모양을 변경 하려면  
  
1.  지침에 따라 [메뉴 명령 텍스트를 변경합니다.](../extensibility/changing-the-text-of-a-menu-command.md) 라는 메뉴 항목을 만들려면 `New Text`합니다.  
  
2.  ChangeMenuText.cs 파일에서 다음 추가 문을 사용 하 여:  
  
    ```c#  
    using System.Security.Permissions;  
    ```  
  
3.  ChangeMenuTextPackageGuids.cs 파일에 다음 줄을 추가 합니다.  
  
    ```c#  
    public const string guidChangeMenuTextPackageCmdSet= "00000000-0000-0000-0000-00000000";  // get the GUID from the .vsct file  
    ```  
  
4.  ChangeMenuText.cs 파일에서 ShowMessageBox 메서드에서 코드를 다음으로 바꿉니다.  
  
    ```c#  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        var command = sender as OleMenuCommand;  
        if (command.Text == "New Text")  
            ChangeMyCommand(command.CommandID.ID, false);}  
    }  
    ```  
  
5.  업데이트를 원하는 명령을 가져오는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> 개체 및 명령 개체에서 적절 한 속성을 설정 합니다. 예를 들어, 다음 메서드는 VSPackage 명령에서 지정 된 명령을 사용 가능 여부가 집합을 만듭니다. 다음 코드에서는 명명 된 항목의 메뉴 `New Text` 클릭 한 후 사용할 수 없습니다.  
  
    ```c#  
    public bool ChangeMyCommand(int cmdID, bool enableCmd)  
    {  
        bool cmdUpdated = false;  
        var mcs = this.ServiceProvider.GetService(typeof(IMenuCommandService))  
            as OleMenuCommandService;  
        var newCmdID = new CommandID(new Guid(ChangeMenuTextPackageGuids.guidChangeMenuTextPackageCmdSet), cmdID);  
        MenuCommand mc = mcs.FindCommand(newCmdID);  
        if (mc != null)  
        {  
            mc.Enabled = enableCmd;  
            cmdUpdated = true;  
        }  
        return cmdUpdated;    }  
    }  
    ```  
  
6.  프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스에서 표시 되어야 합니다.  
  
7.  에 **도구** 메뉴를 클릭 하는 **ChangeMenuText 호출** 명령. 이 시점에서 명령 이름을 **호출 ChangeMenuText**, 이므로 명령 처리기 ChangeMyCommand\(\)를 호출 하지 않습니다.  
  
8.  에 **도구** 이제 메뉴 **새 텍스트**합니다. 클릭 **새 텍스트**합니다. 이 명령은 회색 이제 해야 합니다.  
  
## 참고 항목  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)   
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)