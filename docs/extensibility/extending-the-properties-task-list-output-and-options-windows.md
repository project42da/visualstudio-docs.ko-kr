---
title: "속성, 작업 목록, 출력 및 옵션 창을 확장 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties pane
- task list
- output window
- properties window
- tutorials
- tool windows
ms.assetid: 06990510-5424-44b8-9fd9-6481acec5c76
caps.latest.revision: "37"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f94a8364f52f7723a1ab9dae6114a8bb66a91683
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-the-properties-task-list-output-and-options-windows"></a>속성, 작업 목록, 출력 및 옵션 창을 확장합니다.
Visual Studio의 모든 도구 창에 액세스할 수 있습니다. 이 연습에서는 새 도구 창에 대 한 정보를 통합 하는 방법을 보여 줍니다. **옵션** 페이지와 새 설정에는 **속성** 페이지 및에 쓰는 방법을 **작업목록** 및 **출력** windows 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="create-an-extension-with-a-tool-window"></a>도구 창 확장 만들기  
  
1.  라는 프로젝트 **TodoList** VSIX 서식 파일을 사용 하 고 명명 된 사용자 지정 도구 창 항목 템플릿을 추가 **TodoWindow**합니다.  
  
    > [!NOTE]
    >  도구 창을 사용 된 확장을 만드는 방법에 대 한 자세한 내용은 참조 [도구 창을 사용 된 확장을 만드는](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
## <a name="set-up-the-tool-window"></a>도구 창 설정  
 목록에 새 항목을 추가 하는 단추와 목록에 항목을 표시 하려면 목록 새 할 일 항목을 입력할 텍스트 상자를 추가 합니다.  
  
1.  TodoWindow.xaml에 UserControl에서 단추, 텍스트 상자 및 StackPanel 컨트롤을 삭제 합니다.  
  
    > [!NOTE]
    >  이 삭제 되지 않습니다는 **button1_Click** 는 이후 단계에서 다시 사용 하는 이벤트 처리기입니다.  
  
2.  **모든 WPF 컨트롤** 섹션은 **도구 상자**, 끌어는 **캔버스** 표에 제어 합니다.  
  
3.  끌어서는 **TextBox**, **단추**, 및 **ListBox** 캔버스에 해당 합니다. 동일한 수준에 있는 텍스트 상자 및 단추 및 목록 상자 채우기 아래 그림과 같이, 아래 창의 나머지 있도록 요소를 정렬 합니다.  
  
     ![도구 창 완료](../extensibility/media/t5-toolwindow.png "T5 도구 창")  
  
4.  XAML 창에서 단추 찾아서로 Content 속성 설정 **추가**합니다. 단추 컨트롤에 단추 이벤트 처리기를 추가 하 여 다시 연결을 `Click="button1_Click"` 특성입니다. 캔버스 블록은 다음과 같이 표시 됩니다.  
  
    ```xml  
    <Canvas HorizontalAlignment="Left" Width="306">  
        <TextBox x:Name="textBox" HorizontalAlignment="Left" Height="23" Margin="10,10,0,0" TextWrapping="Wrap" Text="TextBox" VerticalAlignment="Top" Width="208"/>  
            <Button x:Name="button" Content="Add" HorizontalAlignment="Left" Margin="236,13,0,0" VerticalAlignment="Top" Width="48" Click="button1_Click"/>  
            <ListBox x:Name="listBox" HorizontalAlignment="Left" Height="222" Margin="10,56,0,0" VerticalAlignment="Top" Width="274"/>  
    </Canvas>  
    ```  
  
#### <a name="customize-the-constructor"></a>생성자는 사용자 지정  
  
1.  TodoWindowControl.xaml.cs 파일에 다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using System;  
    ```  
  
2.  TodoWindow에 대 한 공용 참조를 추가 하 고 TodoWindow 매개 변수를 사용 하 여 TodoWindowControl 생성자가 있습니다. 코드는 다음과 같이 표시 됩니다.  
  
    ```csharp  
    public TodoWindow parent;  
  
    public TodoWindowControl(TodoWindow window)  
    {  
        InitializeComponent();  
        parent = window;  
    }  
    ```  
  
3.  TodoWindow.cs, TodoWindowControl TodoWindow 매개 변수를 포함 하는 생성자를 변경 합니다. 코드는 다음과 같이 표시 됩니다.  
  
    ```csharp  
    public TodoWindow() : base(null)  
    {  
        this.Caption = "TodoWindow";  
        this.BitmapResourceID = 301;  
        this.BitmapIndex = 1;  
  
         this.Content = new TodoWindowControl(this);  
    }  
    ```  
  
## <a name="create-an-options-page"></a>옵션 페이지 만들기  
 페이지를 제공할 수 있습니다는 **옵션** 대화 상자를 사용자가 도구 창에 대 한 설정을 변경할 수 있습니다. 옵션 페이지를 만들려면 옵션과 TodoListPackage.cs 또는 TodoListPackage.vb 파일의 항목에 설명 하는 클래스 모두 필요 합니다.  
  
1.  라는 클래스를 추가 `ToolsOptions.cs`합니다. 상속 ToolsOptions 클래스 <xref:Microsoft.VisualStudio.Shell.DialogPage>합니다.  
  
    ```csharp  
    class ToolsOptions : DialogPage  
    {  
    }  
    ```  
  
2.  다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    ```  
  
3.  이 연습에서 옵션 페이지 DaysAhead 라는 하나의 옵션을 제공 합니다. 이라는 private 필드를 추가 **daysAhead** 속성 및 이름이 **DaysAhead** ToolsOptions 클래스:  
  
    ```csharp  
    private double daysAhead;  
  
    public double DaysAhead  
    {  
        get { return daysAhead; }  
        set { daysAhead = value; }  
    }  
    ```  
  
 이제 해야 프로젝트가 옵션 페이지를 인식 합니다.  
  
#### <a name="make-the-options-page-available-to-users"></a>사용자에 게 옵션 페이지  
  
1.  TodoWindowPackage.cs에 추가 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> TodoWindowPackage 클래스:  
  
    ```csharp  
    [ProvideOptionPage(typeof(ToolsOptions), "ToDo", "General", 101, 106, true)]  
    ```  
  
2.  ProvideOptionPage 생성자에 첫 번째 매개 변수는 앞에서 만든 있는 ToolsOptions 클래스의 형식입니다. 두 번째 매개 변수 "ToDo"에 있는 category의 이름인는 **옵션** 대화 상자. 세 번째 매개 변수 "일반"의 이름인의 하위 범주는 **옵션** 대화 상자에 옵션 페이지를 사용할 수 있습니다. 다음 두 매개 변수는 문자열;에 대 한 리소스 Id 첫 번째는 범주의 이름을 고 두 번째는 하위 범주의 이름입니다. 마지막 매개 변수는 자동화를 사용 하 여이 페이지에 액세스할 수 있는지 여부를 결정 합니다.  
  
     사용자가 옵션 페이지를 열면 다음 그림과 비슷해야 합니다.  
  
     ![옵션 페이지](../extensibility/media/t5optionspage.gif "T5OptionsPage")  
  
     범주를 확인 **ToDo** 및 하위 범주 **일반**합니다.  
  
## <a name="make-data-available-to-the-properties-window"></a>속성 창에 데이터를 사용할 수 있도록  
 TodoItem 할 일 목록에 있는 개별 항목에 대 한 정보를 저장 하 라는 클래스를 만들어 할 일 목록 정보를 사용할 수 있습니다.  
  
1.  라는 클래스를 추가 `TodoItem.cs`합니다.  
  
     도구 창이 사용자가 사용할 수 있을 때 목록 상자에서 항목 TodoItems로 표현 됩니다. 사용자가 목록 상자에서 이러한 항목 중 하나를 선택는 **속성** 창 항목에 대 한 정보에 표시 됩니다.  
  
     데이터에서 사용할 수 있게 하는 **속성** 두 가지 특별 한 특성이 있는 공용 속성으로 데이터를 바꿀 창 `Description` 및 `Category`합니다. `Description`맨 아래에 나타나는 텍스트는 **속성** 창. `Category`여기서 속성이 표시 되는 시기를 결정은 **속성** 창에 표시 됩니다는 **항목별** 보기. 다음 그림에는 **속성** 창에 내용이 **항목별** 보기는 **이름** 속성에는 **ToDo 필드** 범주는 을 선택 하 고에 대 한 설명을 **이름** 속성 창의 맨 아래에 표시 됩니다.  
  
     ![속성 창](../extensibility/media/t5properties.png "T5Properties")  
  
2.  다음 추가 TodoItem.cs 파일 문을 사용 하 여 합니다.  
  
    ```csharp  
    using System.ComponentModel;  
    using System.Windows.Forms;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
3.  추가 된 `public` 액세스 한정자를 클래스 선언 합니다.  
  
    ```csharp  
    public class TodoItem  
    {  
    }  
    ```  
  
     이름 및 DueDate 두 속성을 추가 합니다. UpdateList() 및 CheckForErrors()을 나중에 수행 합니다.  
  
    ```csharp  
    public class TodoItem  
    {  
        private TodoWindowControl parent;  
        private string name;  
        [Description("Name of the ToDo item")]  
        [Category("ToDo Fields")]  
        public string Name  
        {  
            get { return name; }  
            set  
            {  
                name = value;  
                parent.UpdateList(this);  
            }  
        }  
  
        private DateTime dueDate;  
        [Description("Due date of the ToDo item")]  
        [Category("ToDo Fields")]  
        public DateTime DueDate  
        {  
            get { return dueDate; }  
            set  
            {  
                dueDate = value;  
                parent.UpdateList(this);  
                parent.CheckForErrors();  
            }  
        }  
    }  
    ```  
  
4.  사용자 정의 컨트롤에 대 한 개인 참조를 추가 합니다. 사용자 정의 컨트롤 및 두 일 항목의 이름을 사용 하는 생성자를 추가 합니다. DaysAhead에 대 한 값을 찾으려면 옵션 페이지 속성을 가져옵니다.  
  
    ```csharp  
    private TodoWindowControl parent;  
  
    public TodoItem(TodoWindowControl control, string itemName)  
    {  
        parent = control;  
        name = itemName;  
        dueDate = DateTime.Now;  
  
        double daysAhead = 0;  
        IVsPackage package = parent.parent.Package as IVsPackage;  
        if (package != null)  
        {  
            object obj;  
            package.GetAutomationObject("ToDo.General", out obj);  
  
            ToolsOptions options = obj as ToolsOptions;  
            if (options != null)  
            {  
                daysAhead = options.DaysAhead;  
            }  
        }  
  
        dueDate = dueDate.AddDays(daysAhead);  
    }  
    ```  
  
5.  때문에 인스턴스는 `TodoItem` 클래스 목록 상자에 저장 되 고 목록 상자를 호출 합니다는 `ToString` 함수를 오버 로드 해야는 `ToString` 함수입니다. 생성자와 클래스의 끝에 TodoItem.cs, 다음 코드를 추가 합니다.  
  
    ```csharp  
    public override string ToString()  
    {  
        return name + " Due: " + dueDate.ToShortDateString();  
    }  
    ```  
  
6.  TodoWindowControl.xaml.cs, 스텁 메서드에 대 한 TodoWindowControl 클래스에 추가 된 `CheckForError` 및 `UpdateList` 메서드. ProcessDialogChar 뒤와 파일의 끝 앞에 배치 합니다.  
  
    ```csharp  
    public void CheckForErrors()  
    {  
    }  
    public void UpdateList(TodoItem item)  
    {  
    }  
    ```  
  
     `CheckForError` 해당 메서드는, 오류가 발생 한 올바르게 처리 하는지 여부를 확인 하 고 메서드를 부모 개체에 같은 이름을 갖는 메서드를 호출 합니다. `UpdateList` 메서드는 부모 컨트롤의 ListBox 업데이트; 때 메서드가 호출 되는 `Name` 및 `DueDate` 이 클래스의 변경 내용에는 속성입니다. 나중에 구현 됩니다.  
  
## <a name="integrate-into-the-properties-window"></a>속성 창에 통합  
 이제 목록 상자에 연결 될를 관리 하는 코드를 작성은 **속성** 창.  
  
 리소스의 단추 처리기 TextBox 읽기, a TodoItem 만들기를 클릭 하 고 목록 상자에 추가 합니다.  
  
1.  기존 항목 바꾸기 `button1_Click` 를 새 TodoItem을 만들고 목록 상자에 추가 하는 코드로 함수입니다. 나중에 정의 되는 TrackSelection()를 호출 합니다.  
  
    ```csharp  
    private void button1_Click(object sender, RoutedEventArgs e)  
    {  
        if (textBox.Text.Length > 0)  
        {  
            var item = new TodoItem(this, textBox.Text);  
            listBox.Items.Add(item);  
            TrackSelection();  
            CheckForErrors();  
        }  
    }  
    ```  
  
2.  디자인 뷰에서 ListBox 컨트롤을 선택 합니다. 에 **속성** 창 클릭은 **이벤트 처리기** 단추 및 SelectionChanged 이벤트를 찾습니다. 텍스트 상자에 입력 **listBox_SelectionChanged**합니다. 이렇게 SelectionChanged 처리기에 대 한 스텁을 추가 하 고 이벤트에 할당 합니다.  
  
3.  TrackSelection() 메서드를 구현 합니다. 가져올 필요 하므로 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> 확인 필요한 서비스는 <xref:Microsoft.VisualStudio.Shell.WindowPane.GetService%2A> 는 TodoWindowControl에서 액세스할 수 있습니다. TodoWindow 클래스에 다음 메서드를 추가 합니다.  
  
    ```  
    internal object GetVsService(Type service)  
    {  
        return GetService(service);  
    }  
    ```  
  
4.  다음 추가 TodoWindowControl.xaml.cs 문을 사용 하 여:  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.Shell.Interop;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Shell;  
    ```  
  
5.  SelectionChanged 처리기를 다음과 같이 입력 합니다.  
  
    ```  
    private void listBox_SelectionChanged(object sender, SelectionChangedEventArgs e)  
    {  
        TrackSelection();  
    }  
    ```  
  
6.  이제,와 통합을 제공할 수 있는 TrackSelection 함수를 입력의 **속성** 창. 이 함수는 목록 상자에 항목을 추가 하거나가 목록 상자에 항목을 클릭할 때 호출 됩니다. ListBox의 내용을 SelectionContainer에 추가 하 고 SelectionContainer에 전달 된 **속성** 창의 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> 이벤트 처리기입니다. 사용자 인터페이스 (UI)에서 개체를 추적 하 고 해당 속성을 표시 하는 TrackSelection 서비스  
  
    ```csharp  
    private SelectionContainer mySelContainer;  
    private System.Collections.ArrayList mySelItems;  
    private IVsWindowFrame frame = null;  
  
    private void TrackSelection()  
    {  
        if (frame == null)  
        {  
            var shell = parent.GetVsService(typeof(SVsUIShell)) as IVsUIShell;  
            if (shell != null)  
            {  
                var guidPropertyBrowser = new  
                Guid(ToolWindowGuids.PropertyBrowser);  
                shell.FindToolWindow((uint)__VSFINDTOOLWIN.FTW_fForceCreate,  
                ref guidPropertyBrowser, out frame);  
            }  
        }  
        if (frame != null)  
            {  
                frame.Show();  
            }  
        if (mySelContainer == null)  
        {  
            mySelContainer = new SelectionContainer();  
        }  
  
        mySelItems = new System.Collections.ArrayList();  
  
        var selected = listBox.SelectedItem as TodoItem;  
        if (selected != null)  
        {  
            mySelItems.Add(selected);  
        }  
  
        mySelContainer.SelectedObjects = mySelItems;  
  
        ITrackSelection track = parent.GetVsService(typeof(STrackSelection))  
                                as ITrackSelection;  
        if (track != null)  
        {  
            track.OnSelectChange(mySelContainer);  
        }  
    }  
    ```  
  
     클래스를가지고 있는 **속성** 창을 사용할 수 있는데, 통합할 수 있습니다는 **속성** 창 도구 창 사용 합니다. 도구 창에서 목록 상자에서 항목을 클릭할 때는 **속성** 창은 적절 하 게 업데이트 해야 합니다. 마찬가지로, 사용자의 할 일 항목을 변경할는 **속성** 창, 연결된 된 항목을 업데이트 해야 합니다.  
  
7.  이제 TodoWindowControl.xaml.cs에 UpdateList 함수 코드의 나머지 부분을 추가 합니다. 삭제 하 고 목록 상자에서 수정 된 TodoItem을 다시 추가 합니다.  
  
    ```csharp  
    public void UpdateList(TodoItem item)  
    {  
        var index = listBox.SelectedIndex;  
        listBox.Items.RemoveAt(index);  
        listBox.Items.Insert(index, item);  
        listBox.SelectedItem = index;  
    }  
    ```  
  
8.  코드를 테스트 합니다. 프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스 표시 되어야 합니다.  
  
9. 열기는 **도구 / 옵션** 페이지입니다. 왼쪽된 창에서 작업 범주에 표시 됩니다. 범주는 사전순으로 나열 됩니다, 그리고 따라서 Ts 아래를 확인 합니다.  
  
10. Todo 옵션 페이지의 DaysAhead 속성이로 설정 되어 표시 됩니다 **0**합니다. 로 변경 **2**합니다.  
  
11. 보기 / 다른 창 메뉴, 열기 **TodoWindow**합니다. 형식 **EndDate** 클릭 확인 하 고 텍스트 상자에 **추가**합니다.  
  
12. 목록 상자에 2 일 오늘 이후의 날짜를 표시 됩니다.  
  
## <a name="add-text-to-the-output-window-and-items-to-the-task-list"></a>텍스트를 출력 창과 작업 목록에 항목 추가  
 에 대 한는 **작업 목록**, 작업, 형식의 새 개체를 만들고 해당 작업 개체에 추가 **작업 목록** 해당 Add 메서드를 호출 하 여 합니다. 에 쓸 수는 **출력** 창 창 개체를 가져오는 GetPane 메서드를 호출 하 고 다음 창 개체의 OutputString 메서드를 호출 합니다.  
  
1.  TodoWindowControl.xaml.cs에는 `button1_Click` 메서드를 가져오는 코드를 추가 **일반** 의 창은 **출력** 창 (즉, 기본값), 있고 쓸 합니다. 메서드는 다음과 같이 표시 됩니다.  
  
    ```csharp  
    private void button1_Click(object sender, EventArgs e)  
    {  
        if (textBox.Text.Length > 0)  
        {  
            var item = new TodoItem(this, textBox.Text);  
            listBox.Items.Add(item);  
  
            var outputWindow = parent.GetVsService(  
                typeof(SVsOutputWindow)) as IVsOutputWindow;  
            IVsOutputWindowPane pane;  
            Guid guidGeneralPane = VSConstants.GUID_OutWindowGeneralPane;  
            outputWindow.GetPane(ref guidGeneralPane, out pane);  
            if (pane != null)  
            {  
                 pane.OutputString(string.Format(  
                    "To Do item created: {0}\r\n",  
                 item.ToString()));  
        }  
            TrackSelection();  
            CheckForErrors();  
        }  
    }  
    ```  
  
2.  작업 목록에 항목을 추가 하려면는 중첩된 클래스 TodoWindowControl 클래스를 추가 하려면. 중첩 된 클래스에서 파생 해야 <xref:Microsoft.VisualStudio.Shell.TaskProvider>합니다. TodoWindowControl 클래스의 끝에 다음 코드를 추가 합니다.  
  
    ```csharp  
    [Guid("72de1eAD-a00c-4f57-bff7-57edb162d0be")]  
    public class TodoWindowTaskProvider : TaskProvider  
    {  
        public TodoWindowTaskProvider(IServiceProvider sp)  
            : base(sp)  
        {  
        }  
    }  
    ```  
  
3.  다음 TodoWindowControl 클래스에 대 한 개인 TodoTaskProvider 참조 한 CreateProvider() 메서드를 추가 합니다. 코드는 다음과 같이 표시 됩니다.  
  
    ```csharp  
    private TodoWindowTaskProvider taskProvider;  
    private void CreateProvider()  
    {  
        if (taskProvider == null)  
        {  
            taskProvider = new TodoWindowTaskProvider(parent);  
            taskProvider.ProviderName = "To Do";  
        }  
    }  
    ```  
  
4.  작업 목록을 지우는, ClearError() 및 ReportError()로, 작업 목록에 항목을 추가, TodoWindowControl 클래스에 추가 합니다.  
  
    ```csharp  
    private void ClearError()  
    {  
        CreateProvider();  
        taskProvider.Tasks.Clear();  
    }  
    private void ReportError(string p)  
    {  
        CreateProvider();  
        var errorTask = new Task();  
        errorTask.CanDelete = false;  
        errorTask.Category = TaskCategory.Comments;  
        errorTask.Text = p;  
  
        taskProvider.Tasks.Add(errorTask);  
  
        taskProvider.Show();  
  
        var taskList = parent.GetVsService(typeof(SVsTaskList))  
            as IVsTaskList2;  
        if (taskList == null)  
        {  
            return;  
        }  
  
        var guidProvider = typeof(TodoWindowTaskProvider).GUID;  
         taskList.SetActiveProvider(ref guidProvider);  
    }  
    ```  
  
5.  이제 다음과 같이 CheckForErrors 메서드를 구현 합니다.  
  
    ```csharp  
    public void CheckForErrors()  
    {  
        foreach (TodoItem item in listBox.Items)  
        {  
            if (item.DueDate < DateTime.Now)  
            {  
                ReportError("To Do Item is out of date: "  
                    + item.ToString());  
            }  
        }  
    }  
    ```  
  
## <a name="trying-it-out"></a>시험적으로  
  
1.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
2.  TodoWindow 엽니다 (**보기 / 다른 창 / TodoWindow**).  
  
3.  텍스트 상자에 내용을 입력 하 고 클릭 **추가**합니다.  
  
     기한 날짜 목록 상자에 현재 추가 된 후 2 일입니다. 오류로 인 및 **작업 목록** (**작업 / 확인 목록**) 항목이 없는 있어야 합니다.  
  
4.  이제에서 설정을 변경는 **도구 / 옵션 / ToDo** 에서 페이지 **2** 다시 **0**합니다.  
  
5.  입력에 다른 항목은 **TodoWindow** 클릭 하 고 **추가** 다시 합니다. 이 경우는 오류 또는 항목에는 **작업 목록**합니다.  
  
     항목을 추가한 경우 초기 날짜 지금 플러스 2 일 동안으로 설정 됩니다.  
  
6.  에 **보기** 메뉴를 클릭 **출력** 열려는 **출력** 창.  
  
     다음에 유의 될 때마다 항목을 추가 하면에 메시지가 표시 됩니다는 **작업 목록** 창.  
  
7.  목록 상자에서 항목 중 하나를 클릭 합니다.  
  
     **속성** 창 항목에 대해 두 속성이 표시 됩니다.  
  
8.  속성 중 하나를 변경 하 고 enter 키를 누릅니다.  
  
     항목 목록 상자에서 업데이트 됩니다.