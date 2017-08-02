---
title: "연습: 연결 및 초기화 폼이 있는 워크플로 만들기"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "연결 폼[Visual Studio에서 SharePoint 개발]"
  - "초기화 폼[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 워크플로 연결 폼"
  - "Visual Studio에서 SharePoint 개발, 워크플로 초기화 폼"
  - "Visual Studio에서 SharePoint 개발, 워크플로"
  - "워크플로[Visual Studio에서 SharePoint 개발]"
ms.assetid: c8666d8c-b173-4245-8014-9c1cd6acb071
caps.latest.revision: 38
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 37
---
# 연습: 연결 및 초기화 폼이 있는 워크플로 만들기
  이 연습에서는 연결 및 초기화 폼의 사용을 통합하는 기본적인 순차 워크플로를 만드는 방법을 보여 줍니다.  이러한 폼은 SharePoint 관리자가 처음 연결할 때\(연결 폼\) 및 사용자가 워크플로를 시작할 때\(초기화 폼\) 워크플로에 매개 변수를 추가할 수 있는 ASPX 폼입니다.  
  
 이 연습에서는 사용자가 다음 요구 사항을 가진 비용 보고서 승인 워크플로를 만드는 시나리오에 대해 설명합니다.  
  
-   워크플로가 목록에 연결되어 있으면 관리자에게 연결 폼이 표시되며, 여기서 비용 보고서의 금액 한도를 입력합니다.  
  
-   직원은 해당 비용 보고서를 공유 문서 목록에 업로드하고, 워크플로를 시작한 다음 워크플로 시작 양식에 비용 합계를 입력합니다.  
  
-   직원 비용 보고서 합계가 관리자의 미리 정의된 한도를 초과하면 직원 관리자에 대해 비용 보고서 승인 작업이 만들어집니다.  하지만 직원 비용 보고서 합계가 비용 한도 이하이면 워크플로의 기록 목록에 자동 승인 메시지가 기록됩니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 목록 정의 순차 워크플로 프로젝트 만들기  
  
-   워크플로 일정 만들기  
  
-   워크플로 작업 이벤트 처리  
  
-   워크플로 연결 및 초기화 폼 만들기  
  
-   워크플로 연결  
  
-   수동으로 워크플로 시작  
  
> [!NOTE]  
>  이 연습에서는 순차 워크플로 프로젝트를 사용하지만 상태 시스템 워크플로의 경우에도 프로세스가 동일합니다.  
>   
>  또한 컴퓨터에서 일부 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 사용자 인터페이스 요소에 대해 다음 지침에서 설명한 것과는 다른 이름이나 위치를 표시할 수 있습니다.  설치한 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio  
  
## SharePoint 순차 워크플로 프로젝트 만들기  
 먼저 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 순차 워크플로 프로젝트를 만듭니다.  순차 워크플로는 마지막 작업이 끝날 때까지 순서대로 실행되는 일련의 단계입니다.  이 절차에서는 SharePoint의 공유 문서 목록에 적용되는 순차 워크플로를 만듭니다.  워크플로 마법사를 사용하면 워크플로를 사이트 정의나 목록 정의에 연결하고 워크플로 시작 시기를 결정할 수 있습니다.  
  
#### SharePoint 순차 워크플로 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 을 선택합니다.  
  
3.  **템플릿** 창에서 **SharePoint 2010 프로젝트** 프로젝트 템플릿을 선택합니다.  
  
4.  **이름** 텍스트 상자에 ExpenseReport를 입력한 후 **확인** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
5.  **사이트 지정 및 디버깅에 대한 보안 수준** 페이지에서 **팜 솔루션으로 배포** 옵션 버튼을 선택한 다음 **마침** 버튼을 선택하여 신뢰 수준 및 기본 사이트를 수락합니다.  
  
     또한 이 단계에서는 솔루션의 신뢰 수준을 팜 솔루션으로 설정합니다. 이 옵션은 워크플로 프로젝트에 사용할 수 있는 유일한 옵션입니다.  
  
6.  **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.  
  
7.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
8.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
9. **템플릿** 창에서 **순차 워크플로 \(팜 솔루션에서만\)** 템플릿을 선택한 후 **추가** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
10. **디버깅에 사용할 워크플로 이름 지정** 페이지에서 기본 이름\(**ExpenseReport \- Workflow1**\)을 적용합니다.  기본 워크플로 템플릿 형식 값\(**List Workflow\)**을 그대로 두고  **다음** 단추를 선택합니다.  
  
11. **Visual Studio를 통해 디버그 세션에서 워크플로를 자동으로 연결하시겠습니까?** 페이지에서 워크플로 템플릿을 자동으로 연결하는 확인란이 선택되어 있으면 선택을 취소합니다.  
  
     이 단계를 수행하면 나중에 워크플로를 공유 문서 목록에 수동으로 연결할 수 있으며, 이 경우 연결 폼이 표시됩니다.  
  
12. **마침** 단추를 선택합니다.  
  
## 워크플로에 연결 폼 추가  
 다음으로, SharePoint 관리자가 처음으로 워크플로를 비용 보고서 문서와 연결할 때 표시되는 .ASPX 연결 폼을 만듭니다.  
  
#### 워크플로에 연결 폼을 추가하려면  
  
1.  **솔루션 탐색기** 에서 **Workflow1** 노드를 선택합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택하여 **새 항목 추가** 대화 상자를 표시합니다.  
  
3.  대화 상자 트리 뷰에서 프로젝트 언어에 따라 **Visual C\#** 또는 **Visual Basic**을 확장하고 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
4.  템플릿 목록에서 **워크플로 연결 폼** 템플릿을 선택합니다.  
  
5.  **이름** 텍스트 상자에 ExpenseReportAssocForm.aspx를 입력합니다.  
  
6.  **추가** 버튼을 선택하여 폼을 프로젝트에 추가합니다.  
  
## 연결 폼 디자인 및 코딩  
 이 절차에서는 컨트롤과 코드를 추가하여 연결 폼에 기능을 도입합니다.  
  
#### 연결 폼을 디자인하고 코딩하려면  
  
1.  연결 폼\(ExpenseReportAssocForm.aspx\)에서 `ID="Main"`인 `asp:Content` 요소를 찾습니다.  
  
2.  이 콘텐츠 요소의 첫째 줄 바로 뒤에 다음 코드를 추가하여 비용 승인 한도\(*AutoApproveLimit*\)를 묻는 레이블과 텍스트 상자를 만듭니다.  
  
    ```  
    <asp:Label ID="lblAutoApproveLimit" Text="Auto Approval Limit:" runat="server" />  
  
    <asp:TextBox ID="AutoApproveLimit" runat="server" />  
    <br /><br />  
    ```  
  
3.  **솔루션 탐색기**에서 **ExpenseReportAssocForm.aspx** 파일을 확장하여 종속 파일을 표시합니다.  
  
    > [!NOTE]  
    >  프로젝트가 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]로 작성된 경우 이 단계를 수행하려면 **모든 파일 보기** 단추를 선택해야 합니다.  
  
4.  ExpenseReportAssocForm.aspx 파일에 대한 바로 가기 메뉴를 열고 **코드 보기** 를 선택합니다.  
  
5.  `GetAssociationData` 메서드를 다음 코드로 바꿉니다.  
  
    ```vb  
    Private Function GetAssociationData() As String  
        ' TODO: Return a string that contains the association data that   
        ' will be passed to the workflow. Typically, this is in XML   
        ' format.  
        Return Me.AutoApproveLimit.Text  
    End Function  
    ```  
  
    ```csharp  
    private string GetAssociationData()  
    {  
        // TODO: Return a string that contains the association data that   
        // will be passed to the workflow. Typically, this is in XML   
        // format.  
        return this.AutoApproveLimit.Text;  
    }  
    ```  
  
## 워크플로에 초기화 폼 추가  
 다음으로, 사용자가 비용 보고서에 대해 워크플로를 실행할 때 표시되는 초기화 폼을 만듭니다.  
  
#### 초기화 폼을 만들려면  
  
1.  **솔루션 탐색기** 에서 **Workflow1** 노드를 선택합니다.  
  
2.  메뉴 표시줄에서 **프로젝트**, **새 항목 추가**를 선택하여 **새 항목 추가** 대화 상자를 표시합니다.  
  
3.  대화 상자 트리 뷰에서 프로젝트 언어에 따라 **Visual C\#** 또는 **Visual Basic**을 확장하고 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
4.  템플릿 목록에서 **워크플로 시작 폼** 템플릿을 선택합니다.  
  
5.  **이름** 텍스트 상자에 ExpenseReportInitForm.aspx를 입력합니다.  
  
6.  **추가** 버튼을 선택하여 폼을 프로젝트에 추가합니다.  
  
## 초기화 폼 디자인 및 코딩  
 다음으로, 컨트롤과 코드를 추가하여 초기화 폼에 기능을 도입합니다.  
  
#### 초기화 폼을 코딩하려면  
  
1.  초기화 폼\(ExpenseReportInitForm.aspx\)에서 `ID="Main"` 인 `asp:Content` 요소를 찾습니다.  
  
2.  이 콘텐츠 요소의 첫째 줄 바로 뒤에 다음 코드를 추가하여 연결 폼에 입력된 비용 승인 한도\(*AutoApproveLimit*\)를 표시하는 레이블 및 텍스트 상자와 비용 합계를 묻는 다른 레이블 및 텍스트 상자\(*ExpenseTotal*\)를 만듭니다.  
  
    ```  
    <asp:Label ID="lblAutoApproveLimit" Text="Auto Approval Limit:" runat="server" />  
  
    <asp:TextBox ID="AutoApproveLimit" ReadOnly="true" runat="server" />  
    <br /><br />  
    <asp:Label ID="lblExpenseTotal" Text="Expense Total:" runat="server" />  
  
    <asp:TextBox ID="ExpenseTotal" runat="server" />  
    <br /><br />  
    ```  
  
3.  **솔루션 탐색기**에서 **ExpenseReportInitForm.aspx** 파일을 확장하여 종속 파일을 표시합니다.  
  
4.  ExpenseReportInitForm.aspx 파일에 대한 바로 가기 메뉴를 열고 **코드 보기** 를 선택합니다.  
  
5.  `Page_Load` 메서드를 다음 예제로 바꿉니다.  
  
    ```vb  
    Protected Sub Page_Load(ByVal sender As Object, ByVal e As   
      EventArgs) Handles Me.Load  
        InitializeParams()  
        Me.AutoApproveLimit.Text = workflowList.WorkflowAssociations(New   
          Guid(associationGuid)).AssociationData  
        ' Optionally, add code here to pre-populate your form fields.  
    End Sub  
    ```  
  
    ```csharp  
    protected void Page_Load(object sender, EventArgs e)  
    {  
        InitializeParams();  
        this.AutoApproveLimit.Text =   
          workflowList.WorkflowAssociations[new   
          Guid(associationGuid)].AssociationData;  
    }  
    ```  
  
6.  `GetInitiationData` 메서드를 다음 예제로 바꿉니다.  
  
    ```vb  
    ' This method is called when the user clicks the button to start the workflow.  
    Private Function GetInitiationData() As String  
        Return Me.ExpenseTotal.Text  
        ' TODO: Return a string that contains the initiation data that   
        ' will be passed to the workflow. Typically, this is in XML   
        ' format.  
        Return String.Empty  
    End Function  
    ```  
  
    ```csharp  
    // This method is called when the user clicks the button to start the workflow.          
    private string GetInitiationData()  
    {  
        // TODO: Return a string that contains the initiation data that   
        // will be passed to the workflow. Typically, this is in XML   
        // format.  
        return this.ExpenseTotal.Text;  
    }  
    ```  
  
## 워크플로 사용자 지정  
 다음으로, 워크플로를 사용자 지정합니다.  나중에 두 개의 폼을 워크플로에 연결합니다.  
  
#### 워크플로를 사용자 지정하려면  
  
1.  프로젝트에서 Workflow1을 열어 Workflow Designer에 워크플로를 표시합니다.  
  
2.  **도구 상자** 에서 **Windows Workflow v3.0** 노드를 확장하고 **IfElse** 작업을 찾습니다.  
  
3.  다음 단계 중 하나를 수행 하여 이 작업을 워크플로에 추가 합니다.  
  
    -   **IfElse** 작업의 바로 가기 메뉴에서 **복사**를 선택하고, 워크플로 디자이너의 **onWorkflowActivated1** 작업 아래의 줄에 대한 바로 가기 메뉴를 연 다음 **붙여넣기**를 선택합니다.  
  
    -   **도구 상자** 에서 **IfElse** 작업을 끌어와 워크플로 디자이너의 **onWorkflowActiviated1** 작업 아래의 줄에 연결합니다.  
  
4.  도구 상자에서 **SharePoint Workflow** 노드를 확장하고 **CreateTask** 작업을 찾습니다.  
  
5.  다음 단계 중 하나를 수행 하여 이 작업을 워크플로에 추가 합니다.  
  
    -   **CreateTask** 작업의 바로 가기 메뉴에서 **복사** 를 선택하고, 워크플로 디자이너의 IfElseActivity1 내부의 두 **여기에 활동 놓기** 영역 중 하나에 대한 바로 가기 메뉴를 연 다음 **붙여넣기** 를 선택합니다.  
  
    -   **CreateTask** 작업을 끌어와 **도구 상자** 에서 IfElseActivity1 내부의 두 **여기에 활동 놓기** 영역 중 하나에 드래그 시킵니다.  
  
6.  **속성** 창에서 **CorrelationToken** 속성에 대해 *taskToken*의 속성 값을 입력합니다.  
  
7.  **CorrelationToken** 속성 옆에 있는 더하기 기호\(![TreeView 더하기 기호](~/sharepoint/media/plus.gif "TreeView 더하기 기호")\)를 선택하여 이 속성을 확장합니다.  
  
8.  **OwnerActivityName** 하위 속성의 드롭 다운 화살표를 선택 하고 *Workflow1* 값을 설정합니다.  
  
9. **TaskId** 속성을 선택한 다음 줄임표 \(![ASP.NET 모바일 디자이너 줄임표](~/sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")\) 버튼을 선택하여 **바인딩 속성** 대화 상자를 표시합니다.  
  
10. **새 멤버에 바인딩** 탭에서 **필드 만들기** 옵션 버튼을 선택한 다음 **확인** 버튼을 선택합니다.  
  
11. **TaskProperties** 속성을 선택한 다음 줄임표 \(![ASP.NET 모바일 디자이너 줄임표](~/sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")\) 버y튼을 선택하여 **바인딩 속성** 대화 상자를 표시합니다.  
  
12. **새 멤버에 바인딩** 탭에서 **필드 만들기** 옵션 버튼을 선택한 다음 **확인** 버튼을 선택합니다.  
  
13. **도구 상자** 에서 **SharePoint Workflow** 노드를 확장하고 **LogToHistoryListActivity** 작업을 찾습니다.  
  
14. 다음 단계 중 하나를 수행 하여 이 작업을 워크플로에 추가 합니다.  
  
    -   **LogToHistoryListActivity** 작업의 바로 가기 메뉴에서 **복사** 를 선택하고, 워크플로 디자이너의 IfElseActivity1 내부의 다른 **여기에 활동 놓기** 영역에 대한 바로 가기 메뉴를 연 다음 **붙여넣기** 를 선택합니다.  
  
    -   **LogToHistoryListActivity** 작업을 **도구 상자** 에서 끌어오고 IfElseActivity1 내부의 다른 **여기에 활동 놓기** 영역에 놓습니다.  
  
## 워크플로에 코드 추가  
 다음으로, 워크플로에 코드를 추가하여 기능을 제공합니다.  
  
#### 워크플로에 코드를 추가하려면  
  
1.  워크플로 디자이너에서 **createTask1**작업에 대한 바로 가기 메뉴를 열고 **코드 보기** 를 선택합니다.  
  
2.  다음 메서드를 추가합니다.  
  
    ```vb  
    Private Sub createTask1_MethodInvoking(ByVal sender As   
      System.Object, ByVal e As System.EventArgs)  
        createTask1_TaskId1 = Guid.NewGuid  
        createTask1_TaskProperties1.AssignedTo = "somedomain\\someuser"  
        createTask1_TaskProperties1.Description = "Please approve the   
          expense report"  
        createTask1_TaskProperties1.Title = "Expense Report Approval   
          Needed"  
    End Sub   
    ```  
  
    ```csharp  
    private void createTask1_MethodInvoking(object sender, EventArgs e)  
    {  
        createTask1_TaskId1 = Guid.NewGuid();  
        createTask1_TaskProperties1.AssignedTo = "somedomain\\someuser";  
        createTask1_TaskProperties1.Description = "Please approve the   
          expense report";  
        createTask1_TaskProperties1.Title = "Expense Report Approval   
          Needed";  
    }   
    ```  
  
    > [!NOTE]  
    >  코드에서 `somedomain\\someuser`를 작업이 만들어질 도메인 및 사용자 이름\(예: "`Office\\JoeSch`"\)으로 바꿉니다.  테스트를 위해 개발 시 사용한 계정을 사용하는 것이 가장 편리합니다.  
  
3.  `MethodInvoking` 메서드 아래에 다음 예제를 추가합니다.  
  
    ```vb  
    Private Sub checkApprovalNeeded(ByVal sender As Object, ByVal e As   
      ConditionalEventArgs)  
        Dim approval As Boolean = False  
        If (Convert.ToInt32(workflowProperties.InitiationData) >   
          Convert.ToInt32(workflowProperties.AssociationData)) Then  
            approval = True  
        End If  
        e.Result = approval  
    End Sub   
    ```  
  
    ```csharp  
    private void checkApprovalNeeded(object sender, ConditionalEventArgs   
      e)  
    {  
        bool approval = false;  
        if (Convert.ToInt32(workflowProperties.InitiationData) >   
          Convert.ToInt32(workflowProperties.AssociationData))  
        {  
            approval = true;  
        }  
        e.Result = approval;  
    }   
    ```  
  
4.  Workflow Designer에서 **ifElseBranchActivity1** 작업을 선택합니다.  
  
5.  **속성** 창에서 **조건** 속성의 드롭다운 화살표를 선택한 다음 *Code Condition* 값을 설정합니다.  
  
6.  **조건** 속성 옆에 있는 더하기 기호\(![TreeView 더하기 기호](~/sharepoint/media/plus.gif "TreeView 더하기 기호")\)를 선택하여 이 속성을 확장하고 해당 값을 *checkApprovalNeeded*로 설정합니다.  
  
7.  Workflow Designer에서 **logToHistoryListActivity1** 작업의 바로 가기 메뉴를 연 다음, **핸들러 생성**을 선택하여 `MethodInvoking` 이벤트에 대한 빈 메서드를 생성합니다.  
  
8.  `MethodInvoking` 코드를 다음과 같이 바꿉니다.  
  
    ```vb  
    Private Sub logToHistoryListActivity1_MethodInvoking(ByVal sender As   
      System.Object, ByVal e As System.EventArgs)  
        Me.logToHistoryListActivity1.HistoryOutcome = ("Expense was auto   
          approved for " + workflowProperties.InitiationData)  
    End Sub   
    ```  
  
    ```csharp  
    private void logToHistoryListActivity1_MethodInvoking(object sender,   
      EventArgs e)  
    {  
        this.logToHistoryListActivity1.HistoryOutcome = "Expense was   
          auto approved for " + workflowProperties.InitiationData;  
    }   
    ```  
  
9. F5 키를 눌러 프로그램을 디버그 합니다.  
  
     응용 프로그램을 컴파일, 패키징 및 배포하고, 기능을 활성화하고, [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] 응용 프로그램 풀을 재생한 다음 **사이트 URL** 속성에 지정된 위치에서 브라우저를 시작합니다.  
  
## 문서 목록에 워크플로 연결  
 다음으로, SharePoint 사이트의 **공유문서** 목록에 워크플로를 연결하여 워크플로 연결 폼을 표시합니다.  
  
#### 워크플로를 연결하려면  
  
1.  빠른 실행 모음에서 **공유 문서** 링크를 선택합니다.  
  
2.  **Library Tools** 리본 메뉴 탭에서 **라이브러리** 를 클릭한 다음 **라이브러리 설정** 리본 메뉴 버튼을 선택합니다.  
  
3.  **사용 권한 및 관리** 섹션에서 **워크플로 설정** 링크를 선택한 다음 **워크플로** 페이지에서 **워크플로 추가** 링크를 선택합니다.  
  
4.  워크플로 설정 페이지의 맨 위 목록에서 **ExpenseReport \- Workflow1** 템플릿을 선택합니다.  
  
5.  다음 필드에 ExpenseReportWorkflow를 입력하고 **다음** 버튼을 선택합니다.  
  
     워크플로가 **공유 문서** 목록에 연결되고 워크플로 연결 폼이 표시됩니다.  
  
6.  **자동 승인 한도** 텍스트 상자에 1200을 입력하고 **워크플로 연결** 버튼을 선택합니다.  
  
## 워크플로 시작  
 다음으로, **공유 문서** 목록의 문서 중 하나에 워크플로를 연결하여 워크플로 시작 양식을 표시합니다.  
  
#### 워크플로를 시작하려면  
  
1.  SharePoint 페이지에서 **추가** 버튼을 선택합니다.  
  
2.  빠른 실행 표시줄에서 **공유 문서** 링크를 선택하여 **공유 문서** 목록을 표시합니다.  
  
3.  페이지 맨 위에 있는 **라이브러리 도구** 탭에서 **문서** 링크를 선택한 다음 리본 메뉴에서 **문서 업로드** 버튼을 선택하여 **공유 문서** 목록에 새 문서를 업로드합니다.  
  
4.  **문서 업로드** 대화 상자에서 **찾아보기** 버튼을 선택하고, 문서 파일을 선택하고, **열기** 버튼을 선택한 다음 **확인** 버튼을 선택합니다.  
  
     이 대화 상자에서 문서 설정을 변경할 수 있지만 일단은 **저장** 버튼을 선택하여 기본값을 그대로 유지합니다.  
  
5.  업로드 된 문서를 선택하고, 표시되는 드롭 다운 화살표를 선택한 다음 **워크플로** 항목을 선택합니다.  
  
6.  ExpenseReportWorkflow 옆에 있는 이미지를 선택합니다.  
  
     워크플로 시작 양식이 표시됩니다. **자동 승인 한도** 상자에 표시된 값은 연결 폼에서 입력되었으므로 읽기 전용입니다.  
  
7.  **비용 합계** 텍스트 상자에 1600을 입력 한 다음, **워크플로 시작** 버튼을 선택합니다.  
  
     **공유 문서** 목록이 다시 표시됩니다.  값이 **완료됨**인 **ExpenseReportWorkflow**라는 새 열이 워크플로에서 방금 시작한 항목에 추가됩니다.  
  
8.  업로드된 문서 옆에 있는 드롭다운 화살표를 선택한 다음 **워크플로** 항목을 선택하여 워크플로 상태 페이지를 표시합니다.  **완료된 워크플로** 아래에서 **완료됨** 값을 선택합니다.  **작업** 섹션 아래에 해당 작업이 표시됩니다.  
  
9. 작업 제목을 선택하여 작업 세부 정보를 표시합니다.  
  
10. **공유문서** 목록으로 돌아가서 동일한 문서나 다른 문서를 사용하여 워크플로를 다시 시작합니다.  
  
11. 연결 페이지에 입력된 금액\(1200\) 이하의 금액을 초기화 페이지에 입력합니다.  
  
     이렇게 하면 작업 대신 기록 목록의 항목이 만들어집니다.  워크플로 상태 페이지의 **워크플로 기록** 섹션에 항목이 표시됩니다.  기록 이벤트의 **결과** 열에 표시된 메시지를 확인합니다.  이 메시지에는 자동 승인된 금액을 비롯하여 `logToHistoryListActivity1.MethodInvoking` 이벤트에 입력한 텍스트가 포함됩니다.  
  
## 다음 단계  
 다음 항목에서는 워크플로 템플릿을 만드는 방법에 대해 더 자세히 설명합니다.  
  
-   SharePoint 워크플로에 대한 자세한 내용은 [Windows SharePoint Services에서의 워크플로](http://go.microsoft.com/fwlink/?LinkID=166275) 을 참조하십시오.  
  
## 참고 항목  
 [SharePoint 워크플로 솔루션 만들기](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [연습: 워크플로에 응용 프로그램 페이지 추가](../sharepoint/walkthrough-add-an-application-page-to-a-workflow.md)  
  
  