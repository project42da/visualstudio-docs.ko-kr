---
title: "도구 창으로 검색 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tool windows, adding search
ms.assetid: f78c4892-8060-49c4-8ecd-4360f1b4d133
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d37956c01cbbebbe29d7506cf5eacd9456b3bbc1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-search-to-a-tool-window"></a>도구 창으로 검색 추가
를 작성 하거나 확장 프로그램에서 도구 창을 업데이트할 때 Visual Studio에서 다른 위치에 표시 되는 동일한 검색 기능을 추가할 수 있습니다. 이 기능에는 다음과 같은 기능이 포함 됩니다.  
  
-   도구 모음 사용자 지정 영역에 항상 있는 검색 상자입니다.  
  
-   자체 검색 상자에 중첩 하는 진행률 표시기입니다.  
  
-   각 문자 (빠른 검색)을 입력 하거나 (요청 시 검색) Enter 키를 선택한 후에 결과 표시할 수 있습니다.  
  
-   용어를 검색 가장 최근에 보여 주는 목록입니다.  
  
-   특정 필드 또는 검색 대상은의 측면에서 검색을 필터링 하는 기능.  
  
 이 연습을 수행 하 여 다음 작업을 수행 하는 방법을 배웁니다.  
  
1.  VSPackage 프로젝트를 만듭니다.  
  
2.  읽기 전용 텍스트 상자와 UserControl이 포함 된 도구 창을 만듭니다.  
  
3.  도구 창으로 검색 상자를 추가 합니다.  
  
4.  검색 구현을 추가 합니다.  
  
5.  빠른 검색 및 진행률 표시줄의 표시를 사용 하도록 설정 합니다.  
  
6.  추가 **대/소문자** 옵션입니다.  
  
7.  추가 **짝수 줄만 검색** 필터입니다.  
  
## <a name="to-create-a-vsix-project"></a>VSIX 프로젝트를 만들려면  
  
1.  라는 VSIX 프로젝트를 `TestToolWindowSearch` 라는 도구 창이 있는 **TestSearch**합니다. 이 작업을 수행 하는 도움말을 보려는 경우 참조 [도구 창을 사용 된 확장을 만드는](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
## <a name="to-create-a-tool-window"></a>도구 창을 만들려면  
  
1.  에 `TestToolWindowSearch` 프로젝트를 TestSearchControl.xaml 파일을 엽니다.  
  
2.  기존 항목 바꾸기 `<StackPanel>` 읽기 전용를 추가 하는 다음 블록을 사용 하 여 블록 <xref:System.Windows.Controls.TextBox> 에 <xref:System.Windows.Controls.UserControl> 도구 창에서입니다.  
  
    ```xaml  
    <StackPanel Orientation="Vertical">  
        <TextBox Name="resultsTextBox" Height="800.0"  
            Width="800.0"  
            IsReadOnly="True">  
        </TextBox>  
    </StackPanel>  
    ```  
  
3.  TestSearchControl.xaml.cs 파일에 다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using System.Text;  
    ```  
  
4.  제거는 `button1_Click()` 메서드.  
  
     에 **TestSearchControl** 클래스, 다음 코드를 추가 합니다.  
  
     이 코드는 공용 추가 <xref:System.Windows.Controls.TextBox> 라는 속성이 **SearchResultsTextBox** 및 라는 공개 문자열 속성이 **SearchContent**합니다. 생성자는 SearchResultsTextBox 텍스트 상자에 설정 되 고 SearchContent 줄 바꿈 구분 된 문자열 집합이으로 초기화 됩니다. 또한 입력란의 내용은 문자열 집합으로 초기화 됩니다.  
  
    ```csharp  
    public partial class TestSearchControl : UserControl  
    {  
        public TextBox SearchResultsTextBox { get; set; }  
        public string SearchContent { get; set; }  
  
        public TestSearchControl()  
        {  
            InitializeComponent();  
  
            this.SearchResultsTextBox = resultsTextBox;  
            this.SearchContent = BuildContent();  
  
            this.SearchResultsTextBox.Text = this.SearchContent;  
        }  
  
        private string BuildContent()  
        {  
            StringBuilder sb = new StringBuilder();  
            sb.AppendLine("1 go");  
            sb.AppendLine("2 good");  
            sb.AppendLine("3 Go");  
            sb.AppendLine("4 Good");  
            sb.AppendLine("5 goodbye");  
            sb.AppendLine("6 Goodbye");  
  
            return sb.ToString();  
        }  
    }  
    ```  
  
     [!code-csharp[ToolWindowSearch#1](../extensibility/codesnippet/CSharp/adding-search-to-a-tool-window_1.cs)]
     [!code-vb[ToolWindowSearch#1](../extensibility/codesnippet/VisualBasic/adding-search-to-a-tool-window_1.vb)]  
  
5.  프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스가 표시 됩니다.  
  
6.  메뉴 모음에서 **보기**, **다른 창**, **TestSearch**합니다.  
  
     도구 창이 표시 되지만 검색 컨트롤은 아직 표시 되지 않습니다.  
  
## <a name="to-add-a-search-box-to-the-tool-window"></a>도구 창에는 검색 상자를 추가 하려면  
  
1.  TestSearch.cs 파일에 다음 코드를 추가 `TestSearch` 클래스입니다. 코드는 재정의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.SearchEnabled%2A> 속성 get 접근자 반환 되도록 `true`합니다.  
  
     검색을 사용 하도록 설정 하려면 재정의 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.SearchEnabled%2A> 속성입니다. <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> 클래스 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch> 하지 않는 검색을 사용 하는 기본 구현을 제공 합니다.  
  
    ```csharp  
    public override bool SearchEnabled  
    {  
        get { return true; }  
    }  
    ```  
  
2.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
3.  Visual Studio의 실험적 인스턴스를 열고 **TestSearch**합니다.  
  
     도구 창 맨 위에 있는 검색 컨트롤 표시는 **검색** 워터 마크와 유리 확대 아이콘입니다. 그러나 검색 프로세스가 구현 되어 있지 않은 때문에 검색 아직 작동 하지 않습니다.  
  
## <a name="to-add-the-search-implementation"></a>검색 구현을 추가 하려면  
 검색을 설정 하면는 <xref:Microsoft.VisualStudio.Shell.ToolWindowPane>와 마찬가지로 이전 절차에서 도구 창을 검색 호스트를 만듭니다. 이 호스트를 설정 하 고 항상 백그라운드 스레드에서 발생 하는 검색 프로세스를 관리 합니다. 때문에 <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> 클래스를 검색의 검색 호스트 및 설정의 생성을 관리만 검색 작업을 만들 하 고 검색 메서드를 제공 해야 합니다. 검색 프로세스는 백그라운드 스레드에서 발생 하 고 도구 창 컨트롤에 대 한 호출이 UI 스레드에서 발생 합니다. 따라서 사용 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.ThreadHelper.Invoke%2A> 컨트롤과 함께 처리 하는 데에서 확인 하는 모든 호출을 관리 하기 위한 방법을 합니다.  
  
1.  TestSearch.cs 파일에 다음 추가 `using` 문:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Runtime.InteropServices;  
    using System.Text;  
    using System.Windows.Controls;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
2.  에 `TestSearch` 클래스에서는 다음 작업을 수행 하는 다음 코드를 추가 합니다.  
  
    -   재정의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.CreateSearch%2A> 메서드 검색 작업을 만듭니다.  
  
    -   재정의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.ClearSearch%2A> 입력란의 상태를 복원 하는 메서드. 이 메서드는 사용자가 사용자를 설정 하거나 옵션 또는 필터 설정이 해제 시기 및 검색 작업을 취소 하는 경우 호출 됩니다. 둘 다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.CreateSearch%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.ClearSearch%2A> UI 스레드에서 호출 됩니다. 따라서 방법으로 텍스트 상자에 액세스할 필요가 없습니다는 <xref:Microsoft.VisualStudio.Shell.ThreadHelper.Invoke%2A> 메서드.  
  
    -   라는 클래스를 만듭니다. `TestSearchTask` 에서 상속 되는 <xref:Microsoft.VisualStudio.Shell.VsSearchTask>의 기본 구현을 제공 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSearchTask>합니다.  
  
         `TestSearchTask`, 도구 창 참조 하는 private 필드를 설정 하는 생성자입니다. Search 메서드를 제공 하려면 재정의 <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStartSearch%2A> 및 <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStopSearch%2A> 메서드. <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStartSearch%2A> 메서드는 검색 프로세스를 구현 하는 위치입니다. 이 프로세스는 검색, 텍스트 상자에 검색 결과 표시 하 고 검색은 완료를 보고 하기 위해이 메서드의 기본 클래스 구현을 호출을 포함 합니다.  
  
    ```csharp  
    public override IVsSearchTask CreateSearch(uint dwCookie, IVsSearchQuery pSearchQuery, IVsSearchCallback pSearchCallback)  
    {  
        if (pSearchQuery == null || pSearchCallback == null)  
            return null;  
         return new TestSearchTask(dwCookie, pSearchQuery, pSearchCallback, this);  
    }  
  
    public override void ClearSearch()  
    {  
        TestSearchControl control = (TestSearchControl)this.Content;  
        control.SearchResultsTextBox.Text = control.SearchContent;  
    }  
  
    internal class TestSearchTask : VsSearchTask  
    {  
        private TestSearch m_toolWindow;  
  
        public TestSearchTask(uint dwCookie, IVsSearchQuery pSearchQuery, IVsSearchCallback pSearchCallback, TestSearch toolwindow)  
            : base(dwCookie, pSearchQuery, pSearchCallback)  
        {  
            m_toolWindow = toolwindow;  
        }  
  
        protected override void OnStartSearch()  
        {  
            // Use the original content of the text box as the target of the search.   
            var separator = new string[] { Environment.NewLine };  
            TestSearchControl control = (TestSearchControl)m_toolWindow.Content;  
            string[] contentArr = control.SearchContent.Split(separator, StringSplitOptions.None);  
  
            // Get the search option.   
            bool matchCase = false;  
            // matchCase = m_toolWindow.MatchCaseOption.Value;   
  
                // Set variables that are used in the finally block.  
                StringBuilder sb = new StringBuilder("");  
                uint resultCount = 0;  
                this.ErrorCode = VSConstants.S_OK;  
  
                try  
                {  
                    string searchString = this.SearchQuery.SearchString;  
  
                    // Determine the results.   
                    uint progress = 0;  
                    foreach (string line in contentArr)  
                    {  
                        if (matchCase == true)  
                        {  
                            if (line.Contains(searchString))  
                            {  
                                sb.AppendLine(line);  
                                resultCount++;  
                            }  
                        }  
                        else  
                            {  
                                if (line.ToLower().Contains(searchString.ToLower()))  
                                {  
                                    sb.AppendLine(line);  
                                    resultCount++;  
                                }  
                            }  
  
                            // SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));   
  
                            // Uncomment the following line to demonstrate the progress bar.   
                            // System.Threading.Thread.Sleep(100);  
                        }  
                    }  
                    catch (Exception e)  
                    {  
                        this.ErrorCode = VSConstants.E_FAIL;  
                    }  
                    finally  
                    {  
                        ThreadHelper.Generic.Invoke(() =>  
                        { ((TextBox)((TestSearchControl)m_toolWindow.Content).SearchResultsTextBox).Text = sb.ToString(); });  
  
                        this.SearchResults = resultCount;  
                    }  
  
            // Call the implementation of this method in the base class.   
            // This sets the task status to complete and reports task completion.   
            base.OnStartSearch();  
        }  
  
        protected override void OnStopSearch()  
        {  
            this.SearchResults = 0;  
        }  
    }  
    ```  
  
3.  다음 단계를 수행 하 여 검색 구현을 테스트 합니다.  
  
    1.  프로젝트를 다시 작성 하 고 디버깅을 시작 합니다.  
  
    2.  Visual Studio의 실험적 인스턴스에서 도구 창을 다시 엽니다 검색 창에 검색 텍스트를 입력 하 고 enter 키를 누릅니다.  
  
         올바른 결과가 표시 됩니다.  
  
## <a name="to-customize-the-search-behavior"></a>검색 동작을 사용자 지정 하려면  
 검색 설정을 변경 하 여 검색 컨트롤 모양을 검색 수행 방법 및 다양 한 변화를 만들 수 있습니다. 예를 들어, 워터 마크 (검색 상자에 표시 되는 기본 텍스트), 최소값 및 검색 컨트롤의 최대 너비 및 진행률 표시줄을 표시할지 여부를 변경할 수 있습니다. 지점에는 검색 결과 (요청 또는 빠른 검색)에 시작 하 고을 최근에 검색 용어 목록을 표시할지 여부를 변경할 수 있습니다. 에 있는 설정의 전체 목록을 찾을 수 있습니다는 <xref:Microsoft.VisualStudio.PlatformUI.SearchSettingsDataSource> 클래스입니다.  
  
1.  TestSearch.cs 파일에 다음 코드를 추가 `TestSearch` 클래스입니다. 이 코드에서는 주문형 검색 (ENTER를 클릭 하 여 사용자에 게 의미) 대신 빠른 검색 합니다. 코드는 재정의 `ProvideSearchSettings` 에서 메서드는 `TestSearch` 는 기본 설정을 변경 하는 데 필요한 클래스입니다.  
  
    ```csharp  
    public override void ProvideSearchSettings(IVsUIDataSource pSearchSettings)  
    {  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchStartTypeProperty.Name,   
            (uint)VSSEARCHSTARTTYPE.SST_INSTANT);}  
    ```  
  
2.  새 테스트 솔루션을 다시 작성 하 고 디버거를 다시 시작 하 여 설정 합니다.  
  
     검색 결과가 검색 상자에 문자를 입력 하면 때마다 나타납니다.  
  
3.  에 `ProvideSearchSettings` 메서드를 진행률 표시줄의 표시를 설정 하는 다음 줄을 추가 합니다.  
  
    ```csharp  
    public override void ProvideSearchSettings(IVsUIDataSource pSearchSettings)  
    {  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchStartTypeProperty.Name,   
             (uint)VSSEARCHSTARTTYPE.SST_INSTANT);  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchProgressTypeProperty.Name,   
             (uint)VSSEARCHPROGRESSTYPE.SPT_DETERMINATE);  
    }  
    ```  
  
     표시할 진행률 표시줄에 대 한 진행률을 보고 해야 합니다. 진행률을 보고 하려면 다음 코드를 주석 처리 제거는 `OnStartSearch` 의 메서드는 `TestSearchTask` 클래스:  
  
    ```csharp  
    SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));  
    ```  
  
4.  다음 줄의 주석 처리 제거 막대가 진행률 정도로 처리 속도가 표시 되는 `OnStartSearch` 의 메서드는 `TestSearchTask` 클래스:  
  
    ```csharp  
    System.Threading.Thread.Sleep(100);  
    ```  
  
5.  솔루션을 다시 빌드하면 하 debugb를 시작 하 여 새 설정을 테스트 합니다.  
  
     진행률 표시줄이 검색 창 (로 표시 검색 텍스트 상자 아래 파란색 선) 될 때마다 검색을 수행 합니다.  
  
## <a name="to-enable-users-to-refine-their-searches"></a>검색을 구체화할 수 있도록 하려면  
 사용자가 같은 옵션을 사용 하 여 검색을 구체화할 수 있도록 **대/소문자** 또는 **단어 단위로**합니다. 확인란 또는 단추로 표시 되는 명령으로 표시 함 옵션, 부울 될 수 있습니다. 이 연습에서는 부울 옵션을 만듭니다.  
  
1.  TestSearch.cs 파일에 다음 코드를 추가 `TestSearch` 클래스입니다. 코드는 재정의 `SearchOptionsEnum` 메서드를 지정 된 옵션을 설정 하거나 해제 있는지 확인 하는 검색 구현을 허용 합니다. 코드 `SearchOptionsEnum` 를 대/소문자를 구분 하는 옵션이 추가 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumWindowSearchOptions> 열거자입니다. 대/소문자 구분 하는 옵션은 또한으로 사용할 수는 `MatchCaseOption` 속성입니다.  
  
    ```csharp  
    private IVsEnumWindowSearchOptions m_optionsEnum;  
    public override IVsEnumWindowSearchOptions SearchOptionsEnum  
    {  
        get  
        {  
            if (m_optionsEnum == null)  
            {  
                List<IVsWindowSearchOption> list = new List<IVsWindowSearchOption>();  
  
                list.Add(this.MatchCaseOption);  
  
                m_optionsEnum = new WindowSearchOptionEnumerator(list) as IVsEnumWindowSearchOptions;  
            }  
            return m_optionsEnum;  
        }  
    }  
  
    private WindowSearchBooleanOption m_matchCaseOption;  
    public WindowSearchBooleanOption MatchCaseOption  
    {  
        get  
        {  
            if (m_matchCaseOption == null)  
            {  
                m_matchCaseOption = new WindowSearchBooleanOption("Match case", "Match case", false);  
            }  
            return m_matchCaseOption;  
        }  
    }  
    ```  
  
2.  에 `TestSearchTask` 클래스 matchCase 줄의 주석 처리 제거는 `OnStartSearch` 메서드:  
  
    ```csharp  
    private IVsEnumWindowSearchOptions m_optionsEnum;  
    public override IVsEnumWindowSearchOptions SearchOptionsEnum  
    {  
        get  
        {  
            if (m_optionsEnum == null)  
            {  
                List<IVsWindowSearchOption> list = new List<IVsWindowSearchOption>();  
  
                list.Add(this.MatchCaseOption);  
  
                m_optionsEnum = new WindowSearchOptionEnumerator(list) as IVsEnumWindowSearchOptions;  
            }  
            return m_optionsEnum;  
        }  
    }  
  
    private WindowSearchBooleanOption m_matchCaseOption;  
    public WindowSearchBooleanOption MatchCaseOption  
    {  
        get  
         {  
            if (m_matchCaseOption == null)  
            {  
                m_matchCaseOption = new WindowSearchBooleanOption("Match case", "Match case", false);  
            }  
            return m_matchCaseOption;  
        }  
    }  
    ```  
  
3.  옵션을 테스트 합니다.  
  
    1.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
    2.  도구 창에서 입력란의 오른쪽에 있는 아래쪽 화살표를 선택 합니다.  
  
         **대/소문자** 확인란이 나타납니다.  
  
    3.  선택 된 **대/소문자** 확인란을 선택한 다음 몇 가지 검색을 수행 합니다.  
  
## <a name="to-add-a-search-filter"></a>검색 필터를 추가 하려면  
 검색 대상 집합을 정의 하는 사용자가 허용 하는 검색 필터를 추가할 수 있습니다. 예를 들어 기반이 수정한 가장 최근 날짜와 해당 파일 이름 확장명으로 파일 탐색기에서 파일을 필터링 할 수 있습니다. 이 연습에서는 짝수 줄만에 대 한 필터를 추가 합니다. 해당 필터를 선택 하면 검색 호스트 검색 쿼리를 지정 하는 문자열을 추가 합니다. 그런 다음 이러한 문자열 검색 메서드 내부 식별 하 고 그에 따라 검색 대상은 필터링 수 있습니다.  
  
1.  TestSearch.cs 파일에 다음 코드를 추가 `TestSearch` 클래스입니다. 이 코드는 구현 `SearchFiltersEnum` 추가 하 여 한 <xref:Microsoft.VisualStudio.PlatformUI.WindowSearchSimpleFilter> 결과 필터링 하는 검색에도 줄만 표시 되도록 지정 하는 합니다.  
  
    ```csharp  
    public override IVsEnumWindowSearchFilters SearchFiltersEnum  
    {  
        get  
        {  
            List<IVsWindowSearchFilter> list = new List<IVsWindowSearchFilter>();  
            list.Add(new WindowSearchSimpleFilter("Search even lines only", "Search even lines only", "lines", "even"));  
            return new WindowSearchFilterEnumerator(list) as IVsEnumWindowSearchFilters;  
        }  
    }  
  
    ```  
  
     검색 컨트롤은 검색 필터를 표시 합니다. 이제 `Search even lines only`합니다. 사용자가 필터 문자열을 선택 하는 경우 `lines:"even"` 검색 상자에 표시 합니다. 검색 조건을 다른 필터와 같은 시간에 나타날 수 있습니다. 검색 문자열의 필터, 또는 둘 다 후 필터를 하기 전에 나타날 수 있습니다.  
  
2.  TestSearch.cs 파일에 추가 하려면 다음 방법의 `TestSearchTask` 에 있는 클래스는 `TestSearch` 클래스입니다. 이러한 메서드는 지원의 `OnStartSearch` 메서드를 다음 단계에서 수정 합니다.  
  
    ```csharp  
    private string RemoveFromString(string origString, string stringToRemove)  
    {  
        int index = origString.IndexOf(stringToRemove);  
        if (index == -1)  
            return origString;  
        else   
             return (origString.Substring(0, index) + origString.Substring(index + stringToRemove.Length)).Trim();  
    }  
  
    private string[] GetEvenItems(string[] contentArr)  
    {  
        int length = contentArr.Length / 2;  
        string[] evenContentArr = new string[length];  
  
        int indexB = 0;  
        for (int index = 1; index < contentArr.Length; index += 2)  
        {  
            evenContentArr[indexB] = contentArr[index];  
            indexB++;  
        }  
  
        return evenContentArr;  
    }  
    ```  
  
3.  에 `TestSearchTask` 클래스, 업데이트는 `OnStartSearch` 메서드를 다음 코드로 합니다. 이러한 변경의 필터를 지원 하기 위한 코드를 업데이트 합니다.  
  
    ```csharp  
    protected override void OnStartSearch()  
    {  
        // Use the original content of the text box as the target of the search.   
        var separator = new string[] { Environment.NewLine };  
        string[] contentArr = ((TestSearchControl)m_toolWindow.Content).SearchContent.Split(separator, StringSplitOptions.None);  
  
        // Get the search option.   
        bool matchCase = false;  
        matchCase = m_toolWindow.MatchCaseOption.Value;  
  
        // Set variables that are used in the finally block.  
        StringBuilder sb = new StringBuilder("");  
        uint resultCount = 0;  
        this.ErrorCode = VSConstants.S_OK;  
  
        try  
        {  
            string searchString = this.SearchQuery.SearchString;  
  
            // If the search string contains the filter string, filter the content array.   
            string filterString = "lines:\"even\"";  
  
            if (this.SearchQuery.SearchString.Contains(filterString))  
            {  
                // Retain only the even items in the array.  
                contentArr = GetEvenItems(contentArr);  
  
                // Remove 'lines:"even"' from the search string.  
                searchString = RemoveFromString(searchString, filterString);  
            }  
  
            // Determine the results.   
            uint progress = 0;  
            foreach (string line in contentArr)  
            {  
                if (matchCase == true)  
                {  
                    if (line.Contains(searchString))  
                    {  
                        sb.AppendLine(line);  
                        resultCount++;  
                    }  
                }  
                else  
                {  
                    if (line.ToLower().Contains(searchString.ToLower()))  
                    {  
                        sb.AppendLine(line);  
                        resultCount++;  
                    }  
                }  
  
                SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));  
  
                // Uncomment the following line to demonstrate the progress bar.   
                // System.Threading.Thread.Sleep(100);  
            }  
        }  
        catch (Exception e)  
        {  
            this.ErrorCode = VSConstants.E_FAIL;  
        }  
        finally  
        {  
            ThreadHelper.Generic.Invoke(() =>  
            { ((TextBox)((TestSearchControl)m_toolWindow.Content).SearchResultsTextBox).Text = sb.ToString(); });  
  
            this.SearchResults = resultCount;  
        }  
  
        // Call the implementation of this method in the base class.   
        // This sets the task status to complete and reports task completion.   
        base.OnStartSearch();  
    }  
    ```  
  
4.  코드를 테스트 합니다.  
  
5.  프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스에서 도구 창을 열고 검색 컨트롤에 있는 아래쪽 화살표를 선택 합니다.  
  
     **대/소문자** 확인란 및 **짝수 줄만 검색** 필터 나타납니다.  
  
6.  필터를 선택 합니다.  
  
     검색 상자에 **줄: "도"**, 다음과 같은 결과가 나타납니다.  
  
     좋은 2  
  
     4 양호  
  
     6 goodbye  
  
7.  삭제 `lines:"even"` 검색 상자에서 선택 된 **대/소문자** 확인란을 선택한 다음 입력 `g` 검색 상자에 합니다.  
  
     다음과 같은 결과가 나타납니다.  
  
     1로 이동  
  
     좋은 2  
  
     5 goodbye  
  
8.  검색 상자의 오른쪽에 있는 X를 선택 합니다.  
  
     검색을 해제 한 원래 내용이 나타납니다. 그러나는 **대/소문자** 확인란이 아직 선택 되어 있습니다.