---
title: "FAQ: VSPackage 확장에 추가 기능을 변환 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a01d333-6e31-423f-ae06-5091a4fcb7a9
caps.latest.revision: 22
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
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 8db7d203b599c11ce8fea07ed3647771c879a256
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="faq-converting-add-ins-to-vspackage-extensions"></a>FAQ: VSPackage 확장으로 추가 기능 변환
추가 기능은 이제 사용되지 않습니다. 새 Visual Studio 확장을 하려면 VSIX 확장을 만들기 위해 필요 합니다. 다음은 VSIX 확장을 Visual Studio 추가 기능을 변환 하는 방법에 대 한 몇 가지 자주 묻는 질문에 대답 합니다.  
  
> [!WARNING]
>  C# 및 Visual Basic 프로젝트에 대 한 Visual Studio 2015부터 VSIX 프로젝트를 사용 하 여 추가 하는 메뉴 명령, 도구 창 및 Vspackage에 대 한 항목 템플릿. 자세한 내용은 참조 [What's New in Visual Studio 2015 SDK](../extensibility/what-s-new-in-the-visual-studio-2015-sdk.md)합니다.  
  
> [!IMPORTANT]
>  대부분의 경우에서 VSPackage 프로젝트 항목과 VSIX 프로젝트에 추가 기능 코드를 단순히 전송할 수 있습니다. <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 메서드에서 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>를 호출하여 DTE 자동화 개체를 가져올 수 있습니다.  
>   
>  `DTE2 dte = (DTE2)GetService(typeof(DTE));`  
>   
>  자세한 내용은 참조 [실행 하는 방법 추가 기능에서 코드는 VSPackage에서?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_RunAddin) 아래 합니다.  
  
## <a name="what-software-do-i-need-to-develop-vsix-extensions"></a>VSIX 확장을 개발 하는 소프트웨어 필요 합니까?  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="wheres-the-extension-documentation"></a>확장 문서는 어디 입니까?  
 로 시작 [Visual Studio 확장 개발 하기 시작](../extensibility/starting-to-develop-visual-studio-extensions.md)합니다. MSDN에서 VSSDK 확장 개발에 대 한 다른 문서는 하나 다음과 같습니다.  
  
## <a name="can-i-convert-my-add-in-project-to-a-vsix-project"></a>VSIX 프로젝트에 내 추가 기능 프로젝트를 변환할 수 있습니까?  
 VSIX 프로젝트에서 사용 되는 메커니즘 추가 기능 프로젝트에서 되는 것과 동일 하지 않기 때문에 VSIX 프로젝트에 직접 추가 기능 프로젝트를 변환할 수 없습니다. VSIX 프로젝트 템플릿 및 적절 한 프로젝트 항목 템플릿 덕분은 비교적 쉽게 시작 하 고 VSIX 확장으로 실행 중인 코드 많이 있을 것입니다.  
  
##  <a name="BKMK_StartDeveloping"></a>VSIX 확장을 개발을 시작 하는 방법  
 메뉴 명령에는 VSIX를 확인 하는 방법을 다음과 같습니다.  
  
#### <a name="to-make-a-vsix-extension-that-has-a-menu-command"></a>메뉴 명령이 포함 된 VSIX 확장을 확인 하려면  
  
1.  VSIX 프로젝트를 만듭니다. (**파일**, **새로**, **프로젝트**, 또는 형식 **프로젝트** 에 **빠른 실행** 창). 에 **새 프로젝트** 대화 상자에서 **Visual C# / 확장성** 또는 **Visual Basic / 확장성** 선택 **VSIX 프로젝트**.) 프로젝트 이름을 **TestExtension** 것에 대 한 위치를 지정 합니다.  
  
2.  추가 **사용자 지정 명령** 프로젝트 항목 템플릿을 합니다. (에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기** 선택 **추가 / 새 항목**합니다. 에 **새 프로젝트** Visual C# 또는 Visual Basic의 경우 선택 대화 상자는 **확장성** 노드 선택한 **사용자 지정 명령**.)  
  
3.  F5 키를 눌러 디버그 모드에서 프로젝트를 빌드하고 실행합니다.  
  
     두 번째 Visual Studio 인스턴스가 표시됩니다. 이 두 번째 인스턴스는 실험적 인스턴스이며, 코드를 작성하는 데 사용하는 Visual Studio 인스턴스와 설정이 다를 수도 있습니다. 실험적 인스턴스를 처음 실행할 때는 VS Online에 로그인하고 테마와 프로필을 지정하라는 메시지가 표시됩니다.  
  
     에 **도구** 이라는 단추가 표시 됩니다 (실험적 인스턴스)에 메뉴 **내 명령 이름을**합니다. 이 단추를 선택 하면 메시지가 표시 됩니다: **내 TestVSPackagePackage.MenuItemCallback()**합니다.  
  
##  <a name="BKMK_RunAddin"></a>VSPackage에서 추가 기능에서 코드를 실행 하는 방법  
 추가 기능 코드는 보통 두 가지 방법 중 하나로 실행됩니다.  
  
-   메뉴 명령을 통한 트리거. 코드는 `IDTCommandTarget.Exec` 메서드에 포함되어 있습니다.  
  
-   시작 시 자동으로 실행. 코드는 `OnConnection` 이벤트 처리기에 포함되어 있습니다.  
  
 VSPackage에서도 같은 방식을 사용할 수 있습니다. 콜백 메서드에 일부 추가 기능 코드를 추가하는 방법은 다음과 같습니다.  
  
#### <a name="to-implement-a-menu-command-in-a-vspackage"></a>VSPackage에서 메뉴 명령을 구현하려면  
  
1.  메뉴 명령이 포함된 VSPackage를 만듭니다. (자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md).)  
  
2.  VSPackage 정의가 포함된 파일을 엽니다. (C# 프로젝트의 있기 * \<프로젝트 이름 >*Package.cs.)  
  
3.  파일에 다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  `MenuItemCallback` 메서드를 찾습니다. <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 호출을 추가하여 <xref:EnvDTE80.DTE2> 개체를 가져옵니다.  
  
    ```csharp  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  추가 기능의 `IDTCommandTarget.Exec` 메서드에 포함되어 있었던 코드를 추가합니다. 예를 들어 다음은 새 창에 추가 하는 일부 코드는 **출력** 창 고 새 창에 "일부 텍스트"에 출력 합니다.  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));  
        OutputWindow outputWindow = dte.ToolWindows.OutputWindow;  
  
        OutputWindowPane outputWindowPane = outputWindow.OutputWindowPanes.Add("A New Pane");  
        outputWindowPane.OutputString("Some Text");  
    }  
  
    ```  
  
6.  이 프로젝트를 빌드하고 실행합니다. F5 키를 누르거나 선택 **시작** 에 **디버그** 도구 모음입니다. Visual Studio의 실험적 인스턴스에서 **도구** 메뉴 이라는 단추가 있어야 **내 명령 이름을**합니다. 이 단추는 단어를 선택 하는 경우 **일부 텍스트** 에 표시 됩니다는 **출력** 창. (열어야 할 수도 있습니다는 **출력** 창입니다.)  
  
 시작 시 코드가 실행되도록 할 수도 있습니다. 그러나 일반적으로 VSPackage 확장에는 이 방식을 사용하지 않는 것이 좋습니다. Visual Studio 시작 시 너무 많은 확장이 로드되면 시작 시간이 현저하게 길어질 수 있습니다. 따라서 솔루션을 열 때와 같이 일부 조건이 충족되는 경우에만 VSPackage를 자동으로 로드하는 것이 보다 효율적입니다.  
  
 아래 절차에서는 솔루션을 열 때 자동으로 로드되는 VSPackage의 추가 기능 코드를 실행하는 방법을 보여줍니다.  
  
#### <a name="to-autoload-a-vspackage"></a>VSPackage를 자동 로드하려면  
  
1.  Visual Studio 패키지 프로젝트 항목과 VSIX 프로젝트를 만듭니다. (이 작업을 수행 하는 단계를 참조 하십시오. [개발 VSIX 확장을 시작 하는 방법?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping)합니다. 추가 **Visual Studio 패키지** 대신 프로젝트 항목입니다.) VSIX 프로젝트 이름을 **TestAutoload**합니다.  
  
2.  TestAutoloadPackage.cs를 엽니다. 패키지 클래스가 선언된 줄을 찾습니다.  
  
    ```csharp  
    public sealed class <name of your package>Package : Package  
    ```  
  
3.  이 줄 위에는 특성 집합이 있습니다. 다음 특성을 추가합니다.  
  
    ```csharp  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    ```  
  
4.  그런 다음 `Initialize()` 메서드에서 중단점을 설정하고 F5 키를 눌러 디버깅을 시작합니다.  
  
5.  실험적 인스턴스에서 프로젝트를 엽니다. VSPackage가 로드되고 중단점에 도달합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>의 필드를 사용하여 VSPackage를 로드할 다른 컨텍스트를 지정할 수 있습니다. 자세한 내용은 참조 [로드 Vspackage](../extensibility/loading-vspackages.md)합니다.  
  
## <a name="how-can-i-get-the-dte-object"></a>DTE 개체는 어떻게 가져오나요?  
 추가 기능에 메뉴 명령, 도구 모음 단추, 도구 창 등의 UI가 표시되지 않는 경우 VSPackage에서 DTE 자동화 개체를 가져오면 코드를 그대로 사용할 수 있습니다. 방법은 다음과 같습니다.  
  
#### <a name="to-get-the-dte-object-from-a-vspackage"></a>VSPackage에서 DTE 개체를 가져오려면  
  
1.  Visual Studio 패키지 항목 템플릿 사용 하 여 VSIX 프로젝트를 찾습니다는 * \<프로젝트 이름 >*Package.cs 파일입니다. 이 파일은 <xref:Microsoft.VisualStudio.Shell.Package>에서 파생되는 클래스로, Visual Studio와 상호 작용하는 데 사용할 수 있습니다. 여기서는 해당 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>를 사용하여 <xref:EnvDTE80.DTE2> 개체를 가져옵니다.  
  
2.  다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
3.  `Initialize` 메서드를 찾습니다. 이 메서드는 패키지 마법사에서 지정한 명령을 처리합니다. <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 호출을 추가하여 DTE 개체를 가져옵니다.  
  
    ```csharp  
    DTE dte = (DTE)GetService(typeof(DTE));  
    ```  
  
 <xref:EnvDTE.DTE> 자동화 개체를 가져온 후에는 추가 기능 코드의 나머지 부분을 프로젝트에 추가할 수 있습니다. <xref:EnvDTE80.DTE2> 개체가 필요한 경우에도 같은 작업을 수행하면 됩니다.  
  
## <a name="how-do-i-change-menu-commands-and-toolbar-buttons-in-my-add-in-to-the-vspackage-style"></a>추가 기능의 메뉴 명령 및 도구 모음 단추를 VSPackage 스타일로 변경하려면 어떻게 하나요?  
 VSPackage 확장은 .vsct 파일을 사용하여 대부분의 메뉴 명령, 도구 모음, 도구 모음 단추 및 기타 UI를 만듭니다. **사용자 지정 명령** 프로젝트 항목 템플릿을 제공 명령을 만들 수 있습니다는 **도구** 메뉴. 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
 .Vsct 파일에 대 한 자세한 내용은 참조 [어떻게 Vspackage 추가 사용자 인터페이스 요소](../extensibility/internals/how-vspackages-add-user-interface-elements.md)합니다. 메뉴 항목, 도구 모음 및 도구 모음 단추를 추가할.vsct 파일을 사용 하는 방법을 보여 주는 연습을 참조 하십시오. [확장 메뉴 및 명령을](../extensibility/extending-menus-and-commands.md)합니다.  
  
## <a name="how-do-i-add-custom-tool-windows-in-the-vspackage-way"></a>VSPackage 방식으로 사용자 지정 도구 창을 추가하려면 어떻게 하나요?  
 사용자 지정 도구 창 프로젝트 항목 템플릿을 도구 창을 만드는 옵션을 제공 합니다. 이 프로젝트 항목 템플릿에 대 한 자세한 내용은 참조 [도구 창을 사용 된 확장을 만드는](../extensibility/creating-an-extension-with-a-tool-window.md)합니다. 도구 창에 대 한 정보를 참조 하십시오. [확장 및 사용자 지정 도구 창의](../extensibility/extending-and-customizing-tool-windows.md) 및 포함 된 문서, 특히 [도구 창을 추가](../extensibility/adding-a-tool-window.md)합니다.  
  
## <a name="how-do-i-manage-visual-studio-windows-in-the-vspackage-way"></a>VSPackage 방식으로 Visual Studio 창을 관리하려면 어떻게 하나요?  
 추가 기능이 Visual Studio 창을 관리하는 경우 VSPackage에서도 추가 기능 코드가 작동합니다. 이 절차에서는 관리 코드를 추가 하는 방법을 설명 하는 예를 들어는 **작업 목록** 에 `MenuItemCallback` vspackage 메서드.  
  
#### <a name="to-insert-window-management-code-from-an-add-in-into-a-vspackage"></a>창 관리 코드를 추가 기능에서 VSPackage로 삽입하려면  
  
1.  메뉴 명령에는 VSPackage 만들기는 [개발 VSIX 확장을 시작 하는 방법?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping) 섹션.  
  
2.  VSPackage 정의가 포함된 파일을 엽니다. (C# 프로젝트의 있기 * \<프로젝트 이름 >*Package.cs.)  
  
3.  다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  `MenuItemCallback` 메서드를 찾습니다. <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 호출을 추가하여 <xref:EnvDTE80.DTE2> 개체를 가져옵니다.  
  
    ```csharp  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  추가 기능의 코드를 추가합니다. 예를 들어 다음은 새 작업을 추가 하는 일부 코드는 **작업 목록**작업 수를 나열 하 고 다음 하나 이상의 태스크를 삭제 합니다.  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)   
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));   
  
        TaskList tl = (TaskList)dte.ToolWindows.TaskList;   
        askItem tlItem;   
  
        // Add a couple of tasks to the Task List.   
        tlItem = tl.TaskItems.Add(" ", " ", "Test task 1.",    
            vsTaskPriority.vsTaskPriorityHigh, vsTaskIcon.vsTaskIconUser,   
            true, "", 10, true, true);  
        tlItem = tl.TaskItems.Add(" ", " ", "Test task 2.",   
            vsTaskPriority.vsTaskPriorityLow, vsTaskIcon.vsTaskIconComment, true, "", 20, true,true);  
  
        // List the total number of task list items after adding the new task items.  
        System.Windows.Forms.MessageBox.Show("Task Item 1 description: "+tl.TaskItems.Item(2).Description);  
        System.Windows.Forms.MessageBox.Show("Total number of task items: "+tl.TaskItems.Count);   
  
        // Remove the second task item. The items list in reverse numeric order.   
        System.Windows.Forms.MessageBox.Show("Deleting the second task item");  
        tl.TaskItems.Item(2).Delete();  
        System.Windows.Forms.MessageBox.Show("Total number of task items: "+tl.TaskItems.Count);   
    }  
    ```  
  
## <a name="how-do-i-manage-projects-and-solutions-in-a-vspackage"></a>VSPackage에서 프로젝트와 솔루션을 관리하려면 어떻게 하나요?  
 추가 기능이 프로젝트와 솔루션을 관리하는 경우 VSPackage에서도 추가 기능 코드가 작동합니다. 예를 들어 다음 절차에서는 시작 프로젝트를 가져오는 코드를 추가하는 방법을 보여줍니다.  
  
1.  메뉴 명령에는 VSPackage 만들기는 [개발 VSIX 확장을 시작 하는 방법?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping) 섹션.  
  
2.  VSPackage 정의가 포함된 파일을 엽니다. (C# 프로젝트의 있기 * \<프로젝트 이름 >*Package.cs.)  
  
3.  다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  `MenuItemCallback` 메서드를 찾습니다. <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 호출을 추가하여 <xref:EnvDTE80.DTE2> 개체를 가져옵니다.  
  
    ```csharp  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  추가 기능의 코드를 추가합니다. 예를 들어 다음 코드는 솔루션의 시작 프로젝트 이름을 가져옵니다. 이 패키지를 실행할 때는 다중 프로젝트 솔루션이 열려 있어야 합니다.  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));   
  
        SolutionBuild2 sb = (SolutionBuild2)dte.Solution.SolutionBuild;   
        Project startupProj;   
        string msg = "";  
  
        foreach (String item in (Array)sb.StartupProjects)   
        {  
            msg += item;   
        }  
        System.Windows.Forms.MessageBox.Show("Solution startup Project: "+msg);   
        startupProj = dte.Solution.Item(msg);   
        System.Windows.Forms.MessageBox.Show("Full name of solution's startup project: "+"/n"+startupProj.FullName);   
    }  
    ```  
  
## <a name="how-do-i-set-keyboard-shortcuts-in-a-vspackage"></a>VSPackage에서 바로 가기 키를 설정하려면 어떻게 하나요?  
 .vsct 파일의 `<KeyBindings>` 요소를 사용합니다. 다음 예에서 `idCommand1` 명령의 바로 가기 키는 Alt+A이고 `idCommand2` 명령의 바로 가기 키는 Alt+Ctrl+A입니다. 키 이름의 구문을 확인하세요.  
  
```xml  
<KeyBindings>  
    <KeyBinding guid="MyProjectCmdSet" id="idCommand1" editor="guidVSStd97" key1="A" mod1="ALT" />  
    <KeyBinding guid="MyProjectCmdSet" id="idCommand2" editor="guidVSStd97" key1="A" mod1="CONTROL" mod2="ALT" />  
</KeyBindings>  
```  
  
## <a name="how-do-i-handle-automation-events-in-a-vspackage"></a>VSPackage에서 자동화 이벤트를 처리하려면 어떻게 하나요?  
 VSPackage에서도 추가 기능에서와 같은 방식으로 자동화 이벤트를 처리합니다. 다음 코드에서는 `OnItemRenamed` 이벤트를 처리하는 방법을 보여줍니다. 이 예에서는 DTE 개체를 이미 가져왔다고 가정합니다.  
  
```csharp  
Events2 dteEvents = (Events2)dte.Events;  
dteEvents.ProjectItemsEvents.ItemRenamed += listener1.OnItemRenamed;   
. . .  
public void OnItemRenamed(EnvDTE.ProjectItem projItem, string oldName)   
{  
    string s = "[Event] Renamed " + oldName + " to " + Path.GetFileName(projItem.get_FileNames(1) + " in project " + projItem.ContainingProject.Name;   
}  
```
