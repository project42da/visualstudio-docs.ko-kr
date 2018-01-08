---
title: "출력 창 확장 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Output window, about Output window
ms.assetid: b02fa88c-f92a-4ff6-ba5f-2eb4d48a643a
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8fa99e2c741d11c79cb41226e3958b04d0265621
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-output-window"></a>출력 창 확장
**출력** 창은 텍스트 창 읽기/쓰기의 집합입니다. Visual Studio에는 이러한 기본 제공 창이: **빌드**, 프로젝트에서 빌드에 대 한 메시지를 통신 및 **일반**는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE에 대 한 메시지를 통신 합니다. 프로젝트 가져오기에 대 한 참조는 **빌드** 창을 통해 자동으로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg> 인터페이스 메서드 및 Visual Studio에 대 한 직접 액세스를 제공는 **일반** 통해 창은 <xref:Microsoft.VisualStudio.Shell.Interop.SVsGeneralOutputWindowPane> 서비스입니다. 기본 제공 창과 수 만들고 사용자 고유의 사용자 지정 작업창을 관리 합니다.  
  
 제어할 수 있습니다는 **출력** 창을 통해 직접는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane> 인터페이스입니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> 인터페이스에서 제공 하는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsOutputWindow> 서비스, 만들기, 검색 및 제거에 대 한 메서드를 정의 **출력** 창. <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> 인터페이스 창 표시, 창, 숨기기 및 텍스트를 조작 하기 위한 메서드를 정의 합니다. 제어 하는 다른 방법으로 **출력** 기간은 통해는 <xref:EnvDTE.OutputWindow> 및 <xref:EnvDTE.OutputWindowPane> Visual Studio 자동화 개체 모델의 개체입니다. 이러한 개체는 거의 모든 기능을 캡슐화는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane> 인터페이스입니다. 또한는 <xref:EnvDTE.OutputWindow> 및 <xref:EnvDTE.OutputWindowPane> 열거를 쉽게 수행할 수 있도록 더 높은 수준의 일부 기능을 추가 하는 개체는 **출력** 창을 창에서 텍스트를 검색할 수 있습니다.  
  
## <a name="creating-an-extension-that-uses-the-output-pane"></a>출력 창에 사용 하 여 확장을 만들기  
 출력 창의 다양 한 측면을 실행 하는 확장을 만들 수 있습니다.  
  
1.  라는 VSIX 프로젝트를 `TestOutput` 메뉴 명령을 사용 하 여 명명 된 **TestOutput**합니다. 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
2.  다음 참조를 추가 합니다.  
  
    1.  EnvDTE  
  
    2.  EnvDTE80  
  
3.  TestOutput.cs에 다음 추가 문을 사용 하 여:  
  
    ```f#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  TestOutput.cs, ShowMessageBox 메서드를 삭제 합니다. 다음 메서드 스텁을 추가 합니다.  
  
    ```csharp  
    private void OutputCommandHandler(object sender, EventArgs e)  
    {  
    }  
    ```  
  
5.  TestOutput 생성자에 명령 처리기 OutputCommandHandler를 변경 합니다. 명령을 추가 하는 부분은 다음과 같습니다.  
  
    ```csharp  
    OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
    if (commandService != null)  
    {  
        CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
        EventHandler eventHandler = OutputCommandHandler;  
        MenuCommand menuItem = new MenuCommand(eventHandler, menuCommandID);  
        commandService.AddCommand(menuItem);  
    }  
    ```  
  
6.  다음 단원에서는 다른 하는 메서드가 출력 창 처리 하는 한 가지 방법을 보여 줍니다. OutputCommandHandler() 메서드의 본문에 이러한 메서드를 호출할 수 있습니다. 예를 들어 다음 코드는 다음 섹션에 지정 된 CreatePane() 메서드를 추가 합니다.  
  
    ```csharp  
    private void OutputCommandHandler(object sender, EventArgs e)  
    {  
        CreatePane(new Guid(), "Created Pane", true, false);  
    }  
    ```  
  
## <a name="creating-an-output-window-with-ivsoutputwindow"></a>출력 창 IVsOutputWindow를 사용 하 여 만들기  
 이 예제에서는 새 **출력** 창을 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> 인터페이스입니다.  
  
```csharp  
void CreatePane(Guid paneGuid, string title,   
    bool visible, bool clearWithSolution)  
{  
    IVsOutputWindow output =   
        (IVsOutputWindow)GetService(typeof(SVsOutputWindow));  
    IVsOutputWindowPane pane;  
  
    // Create a new pane.  
    output.CreatePane(  
        ref paneGuid,   
        title,   
        Convert.ToInt32(visible),   
        Convert.ToInt32(clearWithSolution));  
  
    // Retrieve the new pane.  
    output.GetPane(ref paneGuid, out pane);  
  
     pane.OutputString("This is the Created Pane \n");  
}  
```  
  
 클릭 하면 이전 섹션에 지정 된 확장 프로그램에이 메서드를 추가 하는 경우는 **호출 TestOutput** 나타납니다 명령을 **출력** 라고 표시 하는 헤더를 사용 하 여 창을 **출력 보기 : CreatedPane** 및 단어 **만든 창 이것이** 창 자체에 있습니다.  
  
## <a name="creating-an-output-window-with-outputwindow"></a>출력 창 OutputWindow를 사용 하 여 만들기  
 만드는 방법을 보여 주는이 예제는 **출력** 창을 사용 하 여는 <xref:EnvDTE.OutputWindow> 개체입니다.  
  
```csharp  
void CreatePane(string title)  
{  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    OutputWindowPanes panes =  
        dte.ToolWindows.OutputWindow.OutputWindowPanes;  
  
    try  
    {  
        // If the pane exists already, write to it.  
        panes.Item(title);  
    }  
    catch (ArgumentException)  
    {  
        // Create a new pane and write to it.  
        return panes.Add(title);  
    }  
}  
```  
  
 하지만 <xref:EnvDTE.OutputWindowPanes> 컬렉션을 사용 하면 검색할는 **출력** 제목으로 창, 창 제목 보장이 없습니다 고유 하 게 합니다. 제목의 고유성을 의문 때 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow.GetPane%2A> 메서드를 해당 GUID가 올바른 창을 검색 합니다.  
  
 클릭 하면 이전 섹션에 지정 된 확장 프로그램에이 메서드를 추가 하는 경우는 **호출 TestOutput** 라고 표시 하는 헤더를 사용 하 여 출력 창 표시 되어야 하는 명령을 **에서 출력 보기: DTEPane** 및 단어 **DTE 창 추가** 창 자체에 있습니다.  
  
## <a name="deleting-an-output-window"></a>삭제 출력 창  
 삭제 하는 방법을 보여 주는이 예제는 **출력** 창.  
  
```csharp  
void DeletePane(Guid paneGuid)  
{  
    IVsOutputWindow output =  
    (IVsOutputWindow)ServiceProvider.GetService(typeof(SVsOutputWindow));  
  
    IVsOutputWindowPane pane;  
    output.GetPane(ref paneGuid, out pane);  
  
    if (pane == null)  
    {  
        CreatePane(paneGuid, "New Pane\n", true, true);  
    }  
     else  
    {  
        output.DeletePane(ref paneGuid);  
    }  
}  
```  
  
 클릭 하면 이전 섹션에 지정 된 확장 프로그램에이 메서드를 추가 하는 경우는 **호출 TestOutput** 라고 표시 하는 헤더를 사용 하 여 출력 창 표시 되어야 하는 명령을 **에서 출력 보기: 새 창** 및 단어 **만든 창 추가** 창 자체에 있습니다. 클릭는 **호출 TestOutput** 명령을 다시, 창에서 삭제 됩니다.  
  
## <a name="getting-the-general-pane-of-the-output-window"></a>출력 창의 일반 창 가져오기  
 이 예제에는 기본 제공을 가져오는 방법을 보여 줍니다 **일반** 의 창 고 **출력** 창.  
  
```csharp  
void GetGeneralPane()  
{  
    return (IVsOutputWindowPane)GetService(  
        typeof(SVsGeneralOutputWindowPane));  
}  
```  
  
 클릭 하면 이전 섹션에 지정 된 확장 프로그램에이 메서드를 추가 하는 경우는 **TestOutput 호출** 표시 되어야 하는 명령에서 **출력** 창에 표시 된 단어 **일반 발견 창** 창에서.  
  
## <a name="getting-the-build-pane-of-the-output-window"></a>출력 창의 빌드 창 가져오기  
 이 예제에는 검색 빌드 창에 쓰는 방법을 보여 줍니다. 기본적으로 빌드 창 없는 경과 활성화 것도 됩니다.  
  
```csharp  
void OutputTaskItemStringExExample(string buildMessage)  
{  
    EnvDTE80.DTE2 dte = (EnvDTE80.DTE2)ServiceProvider.GetService(typeof(EnvDTE.DTE));  
  
    EnvDTE.OutputWindowPanes panes =  
        dte.ToolWindows.OutputWindow.OutputWindowPanes;  
    foreach (EnvDTE.OutputWindowPane pane in panes)  
        {  
            if (pane.Name.Contains("Build"))  
            {  
                pane.OutputString(buildMessage + "\n");  
                pane.Activate();  
                return;  
             }  
        }  
}  
```