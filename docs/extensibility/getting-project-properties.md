---
title: "프로젝트 속성 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도구 창에 표시 되는 프로젝트 속성"
  - "프로젝트 속성을 표시 하는 도구 창,"
ms.assetid: 96ba07ca-0811-4013-8602-12550ac4ba79
caps.latest.revision: 29
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 29
---
# 프로젝트 속성 가져오기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에서는 도구 창에서 프로젝트 속성을 표시 하는 방법입니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하십시오.  
  
### VSIX 프로젝트를 만들고 도구 창을 추가 하려면  
  
1.  모든 Visual Studio 확장 확장 자산을 포함 하는 VSIX 배포 프로젝트를 시작 합니다. 만들기는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 라는 VSIX 프로젝트 `ProjectPropertiesExtension`합니다. VSIX 프로젝트 템플릿을 찾을 수는 **새 프로젝트** 대화 상자의 **Visual C\# \/ 확장성**합니다.  
  
2.  사용자 지정 도구 창 항목 템플릿을 추가 하 여 도구 창을 추가 `ProjectPropertiesToolWindow`합니다. 에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 에 **새 항목 추가 대화 상자**, 이동 **Visual C\# 항목 \/ 확장성** 선택 하 고 **사용자 지정 도구 창**합니다. 에 **이름** 대화 상자 맨 아래에 필드, 파일 이름을 `ProjectPropertiesToolWindow.cs`합니다. 사용자 지정 도구 창을 만드는 방법에 대 한 자세한 내용은 참조 [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
3.  솔루션을 빌드하고 오류 없이 컴파일되는지 확인합니다.  
  
### 도구 창에서 프로젝트 속성을 표시 하려면  
  
1.  ProjectPropertiesToolWindowCommand.cs 파일에서 다음을 추가 문을 사용 합니다.  
  
    ```c#  
    using EnvDTE;  
    using System.Windows.Controls;  
  
    ```  
  
2.  ProjectPropertiesToolWindowControl.xaml, 제거 기존 단추를 도구 상자에서 TreeView를 추가 합니다. 또한 ProjectPropertiesToolWindowControl.xaml.cs 파일에서 클릭 이벤트 처리기를 제거할 수 있습니다.  
  
3.  ProjectPropertiesToolWindowCommand.cs, 프로젝트를 열고 해당 속성을 읽을 ShowToolWindow\(\) 메서드를 사용 하 여 다음 속성을 TreeView에 추가 합니다. ShowToolWindow에 대 한 코드는 다음과 같습니다.  
  
    ```c#  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        ToolWindowPane window = this.package.FindToolWindow(typeof(ProjectPropertiesToolWindow), 0, true);  
        if ((null == window) || (null == window.Frame))  
        {  
            throw new NotSupportedException("Cannot create window.");  
        }  
        IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
        Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
  
        // Get the tree view and populate it if there is a project open.  
        ProjectPropertiesToolWindowControl control = (ProjectPropertiesToolWindowControl)window.Content;  
        TreeView treeView = control.treeView;  
  
        // Reset the TreeView to 0 items.  
        treeView.Items.Clear();  
  
        DTE dte = (DTE)this.ServiceProvider.GetService(typeof(DTE));  
        Projects projects = dte.Solution.Projects;  
        if (projects.Count == 0)   // no project is open  
        {  
            TreeViewItem item = new TreeViewItem();  
            item.Name = "Projects";  
            item.ItemsSource = new string[]{ "no projects are open." };  
            item.IsExpanded = true;  
            treeView.Items.Add(item);  
            return;  
        }  
  
        Project project = projects.Item(1);  
        TreeViewItem item1 = new TreeViewItem();  
        item1.Header = project.Name + "Properties";  
        treeView.Items.Add(item1);  
  
        foreach (Property property in project.Properties)  
        {  
            TreeViewItem item = new TreeViewItem();  
            item.ItemsSource = new string[] { property.Name };  
            item.IsExpanded = true;  
            treeView.Items.Add(item);  
        }  
    }  
    ```  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 나타납니다.  
  
5.  실험적 인스턴스에서 프로젝트를 엽니다.  
  
6.  에 **보기 \/ 다른 창** 클릭 **ProjectPropertiesToolWindow**합니다.  
  
     트리 컨트롤의 첫 번째 프로젝트와 모든 프로젝트 속성의 이름과 함께 도구 창에 표시 됩니다.