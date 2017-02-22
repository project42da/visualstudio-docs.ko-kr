---
title: "FAQ: VSPackage 확장으로 추가 기능 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3a01d333-6e31-423f-ae06-5091a4fcb7a9
caps.latest.revision: 22
caps.handback.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
---
# FAQ: VSPackage 확장으로 추가 기능 변환
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

추가 기능이 이제 사용 되지 않습니다. 새로운 Visual Studio 확장을 하려면 VSIX 확장을 만들기 위해 필요 합니다. 다음은 Visual Studio 추가 기능에 VSIX 확장을 변환 하는 방법에 대 한 몇 가지 자주 묻는 질문에 대답 합니다.  
  
> [!WARNING]
>  Visual Studio 2015에서 C\# 및 Visual Basic 프로젝트에 대 한 시작 VSIX 프로젝트를 사용 하 여 추가 하는 메뉴 명령, 도구 창 및 VSPackages에 대 한 항목 템플릿. 자세한 내용은 [Visual Studio 2015 SDK의 새로운 기능](../extensibility/what-s-new-in-the-visual-studio-2015-sdk.md)을 참조하세요.  
  
> [!IMPORTANT]
>  대부분의 경우에는 VSPackage 프로젝트 항목과 VSIX 프로젝트에 간단히 추가 기능 코드를 전송할 수 있습니다. 호출 하 여 DTE 자동화 개체를 가져올 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 에 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드.  
>   
>  `DTE2 dte = (DTE2)GetService(typeof(DTE));`  
>   
>  자세한 내용은 참조 [VSPackage에서 추가 기능에 코드를 실행할 수는 방법](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_RunAddin) 아래입니다.  
  
## 소프트웨어 개발 VSIX 확장 하나요?  
 Visual Studio 확장 Visual Studio 2015 외에도 Visual Studio 2015 SDK 필요합니다.  VSIX 프로젝트를 만들거나 기존 VSIX 프로젝트를 열고 Visual Studio 필요한 소프트웨어를 다운로드 합니다. Visual Studio SDK를 설치 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
## 확장 문서는 어디 입니까?  
 로 시작 [Visual Studio 확장 프로그램을 개발 하기 시작](../extensibility/starting-to-develop-visual-studio-extensions.md)합니다. MSDN에서 VSSDK 확장 개발에 대 한 다른 문서는 하나 다음과 같습니다.  
  
## VSIX 프로젝트에 내에서 추가 기능 프로젝트를 변환할 수 있습니까?  
 VSIX 프로젝트에서 사용 되는 메커니즘에서 추가 기능 프로젝트에서 했던 것과 동일 하지 않기 때문에 VSIX 프로젝트에 직접 추가 기능 프로젝트를 변환할 수 없습니다. VSIX 프로젝트 템플릿을 적절 한 프로젝트 항목 템플릿 코드를 사용 하면 비교적 쉽게 시작 하 고 VSIX 확장으로 실행 하는 많이 있을 것입니다.  
  
##  <a name="BKMK_StartDeveloping"></a> VSIX 확장 개발 시작 하려면 어떻게 해야 합니까?  
 메뉴 명령이 포함 된 VSIX를 활용 하는 방법을 다음과 같습니다.  
  
#### 메뉴 명령이 포함 된 VSIX 확장  
  
1.  VSIX 프로젝트를 만듭니다. \(**파일**, **새로**, **프로젝트**, 또는 형식 **프로젝트** 에 **빠른 실행** 창\). 에 **새 프로젝트** 대화 상자에서 **Visual C\# \/ 확장성** 또는 **Visual Basic \/ 확장성** 선택한 **VSIX 프로젝트**.\) 프로젝트 이름을 **TestExtension** 에 대 한 위치를 지정 합니다.  
  
2.  추가 **사용자 지정 명령** 프로젝트 항목 템플릿. \(에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기** 선택한 **추가 \/ 새 항목**합니다. 에 **새 프로젝트** Visual C\# 또는 Visual Basic의 경우 선택 대화 상자는 **확장성** 노드 선택한 **사용자 지정 명령**.\)  
  
3.  F5 키를 눌러 빌드하고 디버그 모드에서 프로젝트를 실행 합니다.  
  
     Visual Studio의 두 번째 인스턴스가 표시 됩니다. 이 두 번째 인스턴스는 실험적 인스턴스를 라고 하 고 동일한 설정으로 코드를 작성 하려면 사용 중인 Visual Studio의 인스턴스를 없을 수 있습니다. 처음 실험적 인스턴스를 실행 하면 VS Online에 로그인 하 고 테마와 프로필을 지정 하 라는 메시지가 됩니다.  
  
     에 **도구** 메뉴 \(실험적 인스턴스\) 이라는 단추가 표시 됩니다 **내 명령 이름**합니다. 이 단추를 선택 하면 메시지가 표시 됩니다: **Testvspackagepackage.menuitemcallback**합니다.  
  
##  <a name="BKMK_RunAddin"></a> VSPackage에서 추가 기능에 코드를 실행할 수는 방법  
 추가 기능 코드는 일반적으로 두 가지 방법 중 하나에서 실행 됩니다.  
  
-   메뉴 명령에 의해 트리거된 \(코드는는 `IDTCommandTarget.Exec` 메서드\)  
  
-   시작 시에 자동으로 \(코드는는 `OnConnection` 이벤트 처리기입니다.\)  
  
 VSPackage에서 동일한 작업을 수행할 수 있습니다. 콜백 메서드에 일부 추가 기능 코드를 추가 하는 방법을 다음과 같습니다.  
  
#### VSPackage에서 메뉴 명령을 구현 하려면  
  
1.  메뉴 명령이 포함 된 VSPackage를 만듭니다. 자세한 내용은 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)을 참조하세요.  
  
2.  VSPackage 정의가 포함 된 파일을 엽니다. \(C\# 프로젝트의 경우에 있어서 *\< 프로젝트 이름 \>*Package.cs입니다.\)  
  
3.  다음 코드를 추가 `using` 문을 파일에 있습니다.  
  
    ```c#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  찾기는 `MenuItemCallback` 메서드. 호출을 추가 하면 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 가져오려는 <xref:EnvDTE80.DTE2> 개체:  
  
    ```c#  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  에 추가 기능에 코드를 추가 해당 `IDTCommandTarget.Exec` 메서드. 예를 들어 다음은 새 창에 추가 하는 코드는 **출력** 창 고 새 창에서 "Some Text"에 출력 합니다.  
  
    ```c#  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));  
        OutputWindow outputWindow = dte.ToolWindows.OutputWindow;  
  
        OutputWindowPane outputWindowPane = outputWindow.OutputWindowPanes.Add("A New Pane");  
        outputWindowPane.OutputString("Some Text");  
    }  
  
    ```  
  
6.  빌드하고이 프로젝트를 실행 합니다. F5 키를 누르거나 선택 **시작** 에 **디버그** 도구 모음입니다. Visual Studio의 실험적 인스턴스에서 **도구** 메뉴 이라는 단추가 있어야 **내 명령 이름**합니다. 이 단추는 단어를 선택 하면 **Some Text** 에 나타나야는 **출력** 창 선택 합니다. \(열어야 할 수도 **출력** 창입니다.\)  
  
 시작 시 코드가 실행 되도록 할 수도 있습니다. 그러나이 방법은 일반적으로 VSPackage 확장에 좋습니다. 너무 많은 확장을 Visual Studio를 시작할 때 로드 하려고 시작 시간이 아주 오래 될 수 있습니다. \(예: 솔루션을 열\) 일부 조건이 충족 될 경우에 VSPackage를 자동으로 로드 하는 것이 좋습니다.  
  
 이 절차에서는 솔루션을 열 때 자동으로 로드 되는 VSPackage에서 추가 기능 코드를 실행 하는 방법을 보여 줍니다.  
  
#### VSPackage 자동 로드 하려면  
  
1.  Visual Studio 패키지 프로젝트 항목과 VSIX 프로젝트를 만듭니다. \(이 작업을 수행 하는 단계를 참조 하십시오. [VSIX 확장 개발 시작 하려면 어떻게 해야 합니까?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping)합니다. 추가 된 **Visual Studio 패키지** 대신 프로젝트 항목입니다.\) VSIX 프로젝트의 이름을 **testautoload로**합니다.  
  
2.  TestAutoloadPackage.cs를 엽니다. 패키지 클래스를 선언 하는 줄을 찾습니다.  
  
    ```c#  
    public sealed class <name of your package>Package : Package  
    ```  
  
3.  이 줄 위에 특성의 집합입니다. 이 특성을 추가 합니다.  
  
    ```c#  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    ```  
  
4.  중단점을 설정는 `Initialize()` 메서드와 시작 \(F5\)을 디버깅 합니다.  
  
5.  실험적 인스턴스에서 프로젝트를 엽니다. VSPackage가 로드 되 고 중단점에 도달 합니다.  
  
 필드를 사용 하 여 VSPackage를 로드할 수 있는 다른 컨텍스트를 지정할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>합니다. 자세한 내용은 [Vspackage를 로드합니다.](../extensibility/loading-vspackages.md)을 참조하십시오.  
  
## DTE 개체를 어떻게 얻을 수 있습니까?  
 추가 기능에서 UI 표시 되지 않는 경우\-예를 들어 메뉴 명령, 도구 모음 단추 또는 도구 창을\-코드를 사용할 수 있습니다\-VSPackage에서 DTE 자동화 개체를 가져올 그대로입니다. 다음은 방법:  
  
#### VSPackage에서 DTE 개체를 가져와  
  
1.  Visual Studio 패키지 항목 템플릿 사용 하 여 VSIX 프로젝트에서 찾아봅니다는 *\< 프로젝트 이름 \>*Package.cs 파일입니다. 이 클래스는 클래스에서 파생 된 <xref:Microsoft.VisualStudio.Shell.Package>; Visual Studio와 상호 작용 하는 데 유용 합니다. 사용 하는 경우에 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 가져오려는 <xref:EnvDTE80.DTE2> 개체입니다.  
  
2.  이러한 추가 `using` 문:  
  
    ```c#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
3.  찾기는 `Initialize` 메서드. 이 메서드는 패키지 마법사에서 지정한 명령을 처리 합니다. 호출을 추가 하면 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> DTE 개체를 가져옵니다.  
  
    ```c#  
    DTE dte = (DTE)GetService(typeof(DTE));  
    ```  
  
 추가한 후의 <xref:EnvDTE.DTE> 자동화 개체를 프로젝트에 추가 기능 코드의 나머지 부분을 추가할 수 있습니다. 필요한 경우는 <xref:EnvDTE80.DTE2> 개체를 동일한 작업을 수행할 수 있습니다.  
  
## 변경 하는 방법 메뉴 명령 및 도구 모음 단추 내 추가 기능에서 VSPackage 스타일으로?  
 VSPackage 확장.vsct 파일을 사용 하 여 메뉴 명령, 도구 모음, 도구 모음 단추 및 기타 UI의 대부분을 만들려고 합니다.**사용자 지정 명령** 프로젝트 항목 템플릿을에 명령을 만드는 옵션을 제공 된 **도구** 메뉴. 자세한 내용은 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)을 참조하세요.  
  
 .Vsct 파일에 대 한 자세한 내용은 참조 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)합니다. 메뉴 항목, 도구 모음 및 도구 모음 단추를 추가 하려면.vsct 파일을 사용 하는 방법을 보여 주는 연습을 참조 하십시오. [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)합니다.  
  
## VSPackage 방식으로 사용자 지정 도구 창 추가  
 사용자 지정 도구 창 프로젝트 항목 템플릿을 도구 창을 만드는 옵션을 제공 합니다. 이 프로젝트 항목 템플릿에 대 한 자세한 내용은 참조 [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)합니다. 도구 창에 대 한 정보를 참조 하십시오. [확장 및 도구 창을 사용자 지정](../extensibility/extending-and-customizing-tool-windows.md) 및 그 아래 문서 특히 [도구 창 추가](../extensibility/adding-a-tool-window.md)합니다.  
  
## VSPackage 방식으로 Visual Studio 창을 관리 하려면 어떻게 해야 합니까?  
 추가 기능에 Visual Studio 창 관리를 하는 경우 VSPackage에서 추가 기능 코드 작동 해야 합니다. 이 절차를 관리 하는 코드를 추가 하는 방법을 보여 줍니다 예를 들어는 **작업 목록** 에 `MenuItemCallback` vspackage 메서드.  
  
#### 추가 기능에서 VSPackage에 창 관리 코드를 삽입 하려면  
  
1.  와 같이 메뉴 명령이 포함 된 VSPackage를 만들기는 [VSIX 확장 개발 시작 하려면 어떻게 해야 합니까?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping) 섹션입니다.  
  
2.  VSPackage 정의가 포함 된 파일을 엽니다. \(C\# 프로젝트의 경우에 있어서 *\< 프로젝트 이름 \>*Package.cs입니다.\)  
  
3.  이러한 추가 `using` 문:  
  
    ```c#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  찾기는 `MenuItemCallback` 메서드. 호출을 추가 하면 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 가져오려는 <xref:EnvDTE80.DTE2> 개체:  
  
    ```c#  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  추가 기능에서 코드를 추가 합니다. 예를 들어 다음은 새로운 작업을 추가 하는 코드는 **작업 목록**, 작업의 수를 나열 하 고 다음 작업 하나를 삭제 합니다.  
  
    ```c#  
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
  
## VSPackage에서 프로젝트 및 솔루션 관리 하려면 어떻게 해야 합니까?  
 추가 기능에 프로젝트 및 솔루션을 관리 하는 경우 VSPackage에서 추가 기능 코드 작동 해야 합니다. 예를 들어이 절차에서는 시작 프로젝트를 가져오는 코드를 추가 하는 방법을 보여 줍니다.  
  
1.  와 같이 메뉴 명령이 포함 된 VSPackage를 만들기는 [VSIX 확장 개발 시작 하려면 어떻게 해야 합니까?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping) 섹션입니다.  
  
2.  VSPackage 정의가 포함 된 파일을 엽니다. \(C\# 프로젝트의 경우에 있어서 *\< 프로젝트 이름 \>*Package.cs입니다.\)  
  
3.  이러한 추가 `using` 문:  
  
    ```c#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  찾기는 `MenuItemCallback` 메서드. 호출을 추가 하면 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 가져오려는 <xref:EnvDTE80.DTE2> 개체:  
  
    ```c#  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  추가 기능에서 코드를 추가 합니다. 예를 들어 다음 코드는 솔루션에서 시작 프로젝트의 이름을 가져옵니다. \(다중 프로젝트 솔루션 열려 있어야이 패키지를 실행 합니다.\)  
  
    ```c#  
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
  
## VSPackage에서 바로 가기 키를 설정 하려면 어떻게 합니까?  
 사용 된 `<KeyBindings>` .vsct 파일의 요소입니다. 다음 예제는 명령에 대 한 바로 가기 키 `idCommand1` Alt \+ A 및 명령에 대 한 바로 가기 키가 `idCommand2` Alt \+ Ctrl \+ A입니다. 키 이름 구문을 확인 하세요.  
  
```xml  
<KeyBindings>  
    <KeyBinding guid="MyProjectCmdSet" id="idCommand1" editor="guidVSStd97" key1="A" mod1="ALT" />  
    <KeyBinding guid="MyProjectCmdSet" id="idCommand2" editor="guidVSStd97" key1="A" mod1="CONTROL" mod2="ALT" />  
</KeyBindings>  
```  
  
## VSPackage에서 자동화 이벤트를 처리 하는 방법  
 추가 기능에서 같이 동일한 방법으로 VSPackage에서 자동화 이벤트를 처리 합니다. 다음 코드에서는 처리 하는 방법을 보여 줍니다.는 `OnItemRenamed` 이벤트입니다. \(이 예제에서는 DTE 개체 이미 받으신\)  
  
```c#  
Events2 dteEvents = (Events2)dte.Events;  
dteEvents.ProjectItemsEvents.ItemRenamed += listener1.OnItemRenamed;   
. . .  
public void OnItemRenamed(EnvDTE.ProjectItem projItem, string oldName)   
{  
    string s = "[Event] Renamed " + oldName + " to " + Path.GetFileName(projItem.get_FileNames(1) + " in project " + projItem.ContainingProject.Name;   
}  
```