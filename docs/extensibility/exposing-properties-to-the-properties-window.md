---
title: "속성 창에 속성 노출 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "속성 브라우저에서 노출 하는 속성 [Visual Studio SDK]"
  - "속성 [Visual Studio SDK]"
  - "속성을 노출 하는 속성 브라우저"
ms.assetid: 47f295b5-1ca5-4e7b-bb52-7b926b136622
caps.latest.revision: 36
caps.handback.revision: 36
ms.author: "gregvanl"
manager: "ghogen"
---
# 속성 창에 속성 노출
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

개체의 공용 속성을 노출 하는이 연습에서 **속성** 창입니다. 이러한 속성에 변경 내용이 반영 된 **속성** 창입니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하십시오.  
  
## 속성 창에 속성 노출  
 이 섹션에서는 사용자 지정 도구 창을 만들고에 연결 된 창 창 개체의 공용 속성이 표시는 **속성** 창입니다.  
  
#### 속성 창에 속성을 노출 하려면  
  
1.  모든 Visual Studio 확장 확장 자산을 포함 하는 VSIX 배포 프로젝트를 시작 합니다. 만들기는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 라는 VSIX 프로젝트 `MyObjectPropertiesExtension`합니다. VSIX 프로젝트 템플릿을 찾을 수는 **새 프로젝트** 대화 상자의 **Visual C\# \/ 확장성**합니다.  
  
2.  사용자 지정 도구 창 항목 템플릿을 추가 하 여 도구 창을 추가 `MyToolWindow`합니다. 에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 에 **새 항목 추가 대화 상자**, 이동 **Visual C\# 항목 \/ 확장성** 선택 하 고 **사용자 지정 도구 창**합니다. 에 **이름** 대화 상자 맨 아래에 필드, 파일 이름을 `MyToolWindow.cs`합니다. 사용자 지정 도구 창을 만드는 방법에 대 한 자세한 내용은 참조 [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
3.  MyToolWindow.cs를 열고 다음 코드를 추가 문을 사용 하 여:  
  
    ```  
    using System.Collections;  
    using System.ComponentModel;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
4.  이제 다음 필드를 추가 `MyToolWindow` 클래스입니다.  
  
    ```c#  
    private ITrackSelection trackSel;  
    private SelectionContainer selContainer;  
  
    ```  
  
5.  MyToolWindow 클래스에 다음 코드를 추가 합니다.  
  
    ```c#  
    private ITrackSelection TrackSelection  
    {  
        get  
        {  
            if (trackSel == null)  
                trackSel =  
                   GetService(typeof(STrackSelection)) as ITrackSelection;  
            return trackSel;  
        }  
    }  
  
    public void UpdateSelection()  
    {  
        ITrackSelection track = TrackSelection;  
        if (track != null)  
            track.OnSelectChange((ISelectionContainer)selContainer);  
    }  
  
    public void SelectList(ArrayList list)  
    {  
        selContainer = new SelectionContainer(true, false);  
        selContainer.SelectableObjects = list;  
        selContainer.SelectedObjects = list;  
        UpdateSelection();  
    }  
  
    public override void OnToolWindowCreated()  
    {  
        ArrayList listObjects = new ArrayList();  
        listObjects.Add(this);  
        SelectList(listObjects);  
    }  
    ```  
  
     `TrackSelection` 속성에 사용 `GetService` 얻으려고는 `STrackSelection` 서비스를 제공 하는 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> 인터페이스입니다.`OnToolWindowCreated` 이벤트 처리기 및 `SelectList` 메서드는 함께 도구 창 창 개체 자체를 포함 하는 선택 된 개체의 목록을 만듭니다.`UpdateSelection` 메서드는 **속성** 창에서 도구 창의 공용 속성을 표시 합니다.  
  
6.  프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스에서 표시 되어야 합니다.  
  
7.  하는 경우는 **속성** 창이 표시 되지 않으면, F4 키를 눌러 엽니다.  
  
8.  열기는 **MyToolWindow** 창입니다. 찾을 수 있습니다 **보기 \/ 다른 창**합니다.  
  
     하면 창이 열리고 창 선택의 공용 속성에 표시 된 **속성** 창입니다.  
  
9. 변경 된 **캡션** 속성에는 **속성** 창 **내 개체 속성**.  
  
     MyToolWindow 창 캡션에 그에 따라 변경 합니다.  
  
## 도구 창에 속성을 노출합니다.  
 이 섹션에서는 도구 창을 추가 하 고 해당 속성을 노출 합니다. 속성에 대 한 변경을에 반영 되는 **속성** 창입니다.  
  
#### 도구 창에 속성을 노출 하려면  
  
1.  MyToolWindow.cs, 열고 MyToolWindow 클래스에는 공용 부울 IsChecked 속성을 추가 합니다.  
  
    ```c#  
    [Category("My Properties")]  
    [Description("MyToolWindowControl properties")]  
    public bool IsChecked  
    {  
        get {  
            if (base.Content == null)  return false;  
            return (bool)(( MyToolWindowControl) base.Content).checkBox.IsChecked;   
        }  
        set {  
            ((MyToolWindowControl) base.Content).checkBox.IsChecked = value;  
        }  
    }  
    ```  
  
     이 속성에서 나중에 만들 WPF 확인란의 상태를 가져옵니다.  
  
2.  MyToolWindowControl.xaml.cs 열고 MyToolWindowControl 생성자를 다음 코드로 바꿉니다.  
  
    ```vb  
    private MyToolWindow pane;  
    public MyToolWindowControl(MyToolWindow pane)  
    {  
        InitializeComponent();  
        this.pane = pane;  
        checkBox.IsChecked = false;  
    }  
    ```  
  
     이렇게 하면 `MyToolWindowControl` 에 대 한 액세스는 `MyToolWindow` 창입니다.  
  
3.  MyToolWindow.cs에서 변경 된 `MyToolWindow` 생성자를 다음과 같이 합니다.  
  
    ```c#  
    base.Content = new MyToolWindowControl(this);  
    ```  
  
4.  MyToolWindowControl의 디자인 보기를 변경 합니다.  
  
5.  단추를 삭제 하 고 확인란에서 추가 **도구 상자** 왼쪽된 위 모퉁이에 있습니다.  
  
6.  선택 및 선택 취소 이벤트를 추가 합니다. 디자인 보기에서 확인란을 선택 합니다.**속성** 창에서 이벤트 처리기 단추를 클릭 \(맨 오른쪽에 **속성** 창\). 찾기 **Checked** 유형과 **checkbox\_Checked** 텍스트 상자에 찾을 **선택 하지 않은** 유형과 **checkbox\_Unchecked** 텍스트 상자에 합니다.  
  
7.  확인란 이벤트 처리기를 추가 합니다.  
  
    ```c#  
    private void checkbox_Checked(object sender, RoutedEventArgs e)  
    {  
        pane.IsChecked = true;  
        pane.UpdateSelection();  
    }  
    private void checkbox_Unchecked(object sender, RoutedEventArgs e)  
    {  
        pane.IsChecked = false;  
        pane.UpdateSelection();  
    }  
    ```  
  
8.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
9. 실험적 인스턴스를 열고는 **MyToolWindow** 창입니다.  
  
     창의 속성에 대 한 조회는 **속성** 창입니다.**IsChecked** 아래에서 속성 창의 맨 아래에 표시 된 **내 속성** 범주.  
  
10. 이 확인란는 **MyToolWindow** 창입니다.**IsChecked** 에 **속성** 창으로 변경 **True**합니다. 에 있는 확인란의 선택을 취소는 **MyToolWindow** 창입니다.**IsChecked** 에 **속성** 창으로 변경 **False**합니다. 값을 변경 **IsChecked** 에 **속성** 창입니다. 에 있는 확인란의 **MyToolWindow** 새 값과 일치 하도록 창 변경 합니다.  
  
    > [!NOTE]
    >  에 표시 되는 개체의 삭제 해야 하는 경우는 **속성** 창, 호출 `OnSelectChange` 와 `null` 선택 컨테이너 첫 번째입니다. 속성 또는 개체를 삭제 한 후 업데이트 선택 컨테이너를 변경할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.SelectionContainer.SelectableObjects%2A> 및 <xref:Microsoft.VisualStudio.Shell.SelectionContainer.SelectedObjects%2A> 나열 합니다.  
  
## 선택 목록 변경  
 이 섹션에서는 기본 속성 클래스에 대 한 선택 목록을 추가 하 고 도구 창 인터페이스를 사용 하 여 어떤 선택 목록을 표시 하려면 선택 합니다.  
  
#### 선택 목록 변경 하려면  
  
1.  MyToolWindow.cs 열고 라는 공용 클래스를 추가 `Simple`합니다.  
  
    ```c#  
    public class Simple  
    {  
        private string someText = "";  
  
        [Category("My Properties")]  
        [Description("Simple Properties")]  
        [DisplayName("My Text")]  
        public string SomeText  
        {  
            get { return someText; }  
            set { someText = value; }  
        }  
  
        [Category("My Properties")]  
        [Description("Read-only property")]  
        public bool ReadOnly  
        {  
            get { return false; }  
        }  
    }  
    ```  
  
2.  두 가지 방법으로 전환 및 MyToolWindow 클래스 SimpleObject 속성을 추가 **속성** 창 창 간에 창 선택 및 `Simple` 개체입니다.  
  
    ```c#  
    private Simple simpleObject = null;  
    public Simple SimpleObject  
    {  
        get  
        {  
            if (simpleObject == null) simpleObject = new Simple();  
            return simpleObject;  
        }  
    }  
  
    public void SelectSimpleList()  
    {  
        ArrayList listObjects = new ArrayList();  
        listObjects.Add(SimpleObject);  
        SelectList(listObjects);  
    }  
  
    public void SelectThisList()  
    {  
        ArrayList listObjects = new ArrayList();  
        listObjects.Add(this);  
        SelectList(listObjects);  
    }  
    ```  
  
3.  MyToolWindowControl.cs에서 확인란 처리기를 코드의 다음이 줄으로 바꿉니다.  
  
    ```c#  
    private void checkbox_Checked(object sender, RoutedEventArgs e)  
     {  
        pane.IsChecked = true;  
        pane.SelectSimpleList();  
        pane.UpdateSelection();  
    }  
    private void checkbox_Unchecked(object sender, RoutedEventArgs e)  
    {  
        pane.IsChecked = false;  
        pane.SelectThisList();  
        pane.UpdateSelection();  
    }  
    ```  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
5.  실험적 인스턴스를 열고는 **MyToolWindow** 창입니다.  
  
6.  에 있는 확인란을 선택 된 **MyToolWindow** 창입니다.**속성** 창에 표시는 `Simple` 개체 속성 **SomeText** 및 **ReadOnly**합니다. 확인란의 선택을 취소 합니다. 공용 속성 창에 표시 된 **속성** 창입니다.  
  
    > [!NOTE]
    >  표시 이름을 **SomeText** 는 **내 텍스트**합니다.  
  
## 모범 사례  
 이 연습에서는 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 는 선택 가능한 개체 컬렉션 및 선택한 개체 컬렉션 동일한 컬렉션에 구현 됩니다. 선택한 개체만 속성 브라우저 목록에 나타납니다. 더 완전 한 ISelectionContainer 구현 Reference.ToolWindow 샘플을 참조 하세요.  
  
 Visual Studio 도구 창 Visual Studio 세션 간에 유지 됩니다. 도구 창 상태를 유지에 대 한 자세한 내용은 참조 하십시오. <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>합니다.  
  
## 참고 항목  
 [속성 및 속성 창 확장](../extensibility/extending-properties-and-the-property-window.md)