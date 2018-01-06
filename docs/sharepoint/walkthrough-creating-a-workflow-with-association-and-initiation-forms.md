---
title: "연습: 연결 및 초기화 폼이 있는 워크플로 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- SharePoint development in Visual Studio, workflow association forms
- workflows [SharePoint development in Visual Studio]
- association forms [SharePoint development in Visual Studio]
- initiation forms [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, workflow initiation forms
ms.assetid: c8666d8c-b173-4245-8014-9c1cd6acb071
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b3178c330d34570d1406a1b63368537bc7f66887
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-workflow-with-association-and-initiation-forms"></a>연습: 연결 및 초기화 폼이 있는 워크플로 만들기
  이 연습에는 연결 및 초기화 폼의 사용을 통합 하는 기본적인 순차 워크플로 만드는 방법을 보여 줍니다. 이들은 (연결 양식) SharePoint 관리자가 처음 연결할 때 및 워크플로 (시작 양식) 사용자가 시작 될 때 워크플로에 추가할 매개 변수를 사용 하도록 설정 하는 ASPX 폼입니다.  
  
 이 연습에서는 다음과 같은 요구 사항이 있는 경비 보고서에 대 한 승인 워크플로 만들려면 사용자가 위치 하는 시나리오를 설명 합니다.  
  
-   워크플로 목록에 연결 되 면 관리자 연결 폼 경비 보고서에 대 한 금액 한도 입력 하 라는 메시지가 표시 됩니다.  
  
-   직원 공유 문서 목록에 해당 경비 보고서를 업로드 하 고, 워크플로 시작, 워크플로 시작 양식에서 총 비용을 입력 합니다.  
  
-   총 직원 경비 보고서 관리자의 미리 정의 된 제한을 초과 하면 경비 보고서를 승인 하는 직원의 관리자에 대 한 작업이 만들어집니다. 그러나 직원의 경비 보고서 합계가 지출 한도 보다 작거나 경우 워크플로 기록 목록에 자동으로 승인 메시지는 기록 됩니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   SharePoint 목록 정의 순차 워크플로 프로젝트를 만들어 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
-   워크플로 일정을 만드는 중입니다.  
  
-   워크플로 활동 이벤트를 처리 합니다.  
  
-   워크플로 연결 및 초기화 폼 만들기  
  
-   워크플로 연결 합니다.  
  
-   수동으로 워크플로 시작 합니다.  
  
> [!NOTE]  
>  이 연습에서는 순차 워크플로 프로젝트는 프로세스는 상태 시스템 워크플로의 같습니다.  
>   
>  컴퓨터를 다른 이름 또는 위치 중 일부에 대해 표시할 수 있습니다는 또한는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 다음 지침에 설명 된 사용자 인터페이스 요소입니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 해야 하는 버전 및 설정이 있습니다를 사용 하는 이러한 요소에 따라 결정 됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원 되는 버전 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 합니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio.  
  
## <a name="creating-a-sharepoint-sequential-workflow-project"></a>SharePoint 순차 워크플로 프로젝트 만들기  
 먼저의 순차 워크플로 프로젝트를 만듭니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 순차 워크플로 마지막 작업이 완료 될 때까지 순서 대로 실행 되는 일련의 단계입니다. 이 절차에서는 SharePoint에서 공유 문서 목록에 적용 되는 순차 워크플로 만들게 됩니다. 워크플로 마법사 사용 하면 사이트 또는 목록 정의 워크플로가 연결 하 고 워크플로가 시작 시기를 결정할 수 있습니다.  
  
#### <a name="to-create-a-sharepoint-sequential-workflow-project"></a>SharePoint 순차 워크플로 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로**, **프로젝트** 표시 하는 **새 프로젝트** 대화 상자.  
  
2.  확장 하 고는 **SharePoint** 노드 아래의 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **2010** 노드.  
  
3.  에 **템플릿** 창에서 선택 된 **SharePoint 2010 프로젝트** 프로젝트 템플릿을 합니다.  
  
4.  에 **이름** 상자에 입력 **ExpenseReport** 선택한 후는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
5.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지를 선택 합니다는 **팜 솔루션으로 배포** 옵션 단추를 선택한 후는 **마침** 적용할 단추는 신뢰 수준 및 기본 사이트입니다.  
  
     또한이 단계는 워크플로 프로젝트에 대 한 옵션만 사용할 수 있는 팜 솔루션으로 솔루션에 대 한 신뢰 수준을 설정 합니다.  
  
6.  **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.  
  
7.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
8.  아래의 **Visual C#** 또는 **Visual Basic**를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
9. 에 **템플릿** 창 선택 **순차 워크플로 (팜 솔루션에만 해당)** 서식 파일을 선택한 후는 **추가** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
10. 에 **디버깅에 대 한 워크플로 이름을 지정** 페이지에서 기본 이름을 적용 (**경비 보고서-Workflow1**). 기본 워크플로 템플릿 형식 값을 유지 (**목록 워크플로)**합니다. **다음** 단추를 선택합니다.  
  
11. 에 **Visual Studio 디버그 세션에서 워크플로 자동으로 연결 하 시겠습니까?** 페이지에서 선택 하는 경우 워크플로 템플릿을 자동으로 연결 하는 확인란의 선택을 취소 합니다.  
  
     이 단계를 사용 하면 수동으로 응용 프로그램 폼을 표시 하는 공유 문서 목록 나중에 사용 하 여 워크플로 연결할 수 있습니다.  
  
12. 선택 된 **마침** 단추입니다.  
  
## <a name="adding-an-association-form-to-the-workflow"></a>연결 양식을 워크플로에 추가  
 다음으로 만듭니다는 합니다. SharePoint 관리자는 먼저 워크플로가 경비 보고서 문서와 연결 하는 경우 나타나는 ASPX 연결 폼  
  
#### <a name="to-add-an-association-form-to-the-workflow"></a>연결 양식을 워크플로에 추가 하려면  
  
1.  선택 된 **Workflow1** 노드에서 **솔루션 탐색기**합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가** 표시 하는 **새 항목 추가** 대화 상자.  
  
3.  확장 대화 상자의 트리 보기에서 **Visual C#** 또는 **Visual Basic** (언어에 따라 프로젝트)를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
4.  템플릿 목록에서 선택 된 **워크플로 연결 양식** 템플릿.  
  
5.  에 **이름** 텍스트 상자에 입력 **ExpenseReportAssocForm.aspx**합니다.  
  
6.  선택 된 **추가** 프로젝트에 폼을 추가 하려면 단추입니다.  
  
## <a name="designing-and-coding-the-association-form"></a>디자인 하 고 응용 프로그램 폼 코딩  
 이 절차에서는 컨트롤 및 코드를 추가 하 여 연결 폼는 기능을 도입 합니다.  
  
#### <a name="to-design-and-code-the-association-form"></a>디자인 및 코드 응용 프로그램 폼  
  
1.  연결 양식 (ExpenseReportAssocForm.aspx)를 찾습니다는 `asp:Content` 를 가진 요소가 `ID="Main"`합니다.  
  
2.  이 콘텐츠 요소의 첫 번째 줄으로 바로 뒤 레이블 및 비용 승인 한도를 묻는를 만들려면 다음 코드를 추가 (*AutoApproveLimit*):  
  
    ```  
    <asp:Label ID="lblAutoApproveLimit" Text="Auto Approval Limit:" runat="server" />  
  
    <asp:TextBox ID="AutoApproveLimit" runat="server" />  
    <br /><br />  
    ```  
  
3.  확장의 **ExpenseReportAssocForm.aspx** 파일을 **솔루션 탐색기** 해당 종속 파일을 표시 합니다.  
  
    > [!NOTE]  
    >  프로젝트에 있으면 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]를 선택 해야 합니다는 **모든 파일 보기** 단추가이 단계를 수행 합니다.  
  
4.  ExpenseReportAssocForm.aspx 파일에 대 한 바로 가기 메뉴를 열고 **코드 보기**합니다.  
  
5.  대체는 `GetAssociationData` 메서드:  
  
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
  
## <a name="adding-an-initiation-form-to-the-workflow"></a>시작 양식을 워크플로에 추가  
 다음으로 사용자가 자신의 경비 보고서에 대 한 워크플로 실행할 때 나타나는 시작 양식을 만듭니다.  
  
#### <a name="to-create-an-initiation-form"></a>시작 폼을 만들려면  
  
1.  선택 된 **Workflow1** 노드에서 **솔루션 탐색기**합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가** 표시는 **새 항목 추가** 대화 상자.  
  
3.  확장 대화 상자의 트리 보기에서 **Visual C#** 또는 **Visual Basic** (언어에 따라 프로젝트)를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
4.  템플릿 목록에서 선택 된 **워크플로 시작 양식** 템플릿.  
  
5.  에 **이름** 텍스트 상자에 입력 **ExpenseReportInitForm.aspx**합니다.  
  
6.  선택 된 **추가** 프로젝트에 폼을 추가 하려면 단추입니다.  
  
## <a name="designing-and-coding-the-initiation-form"></a>디자인 하 고 초기화 폼 코딩  
 다음으로, 컨트롤 및 코드를 추가 하 여 초기화 폼에 기능을 도입 합니다.  
  
#### <a name="to-code-the-initiation-form"></a>초기화 폼의 코드를 작성 하려면  
  
1.  시작 양식 (ExpenseReportInitForm.aspx)를 찾습니다는 `asp:Content` 포함 된 요소 `ID="Main"`합니다.  
  
2.  바로이 콘텐츠 요소의 첫 번째 줄 뒤 레이블 및 비용 승인 한도 표시 하는 텍스트 상자를 만들려면 다음 코드를 추가 (*AutoApproveLimit*) 연결 양식을 및 다른 레이블을 입력 한 및 비용 합계에 대 한 메시지를 표시 하는 입력란 (*ExpenseTotal*):  
  
    ```  
    <asp:Label ID="lblAutoApproveLimit" Text="Auto Approval Limit:" runat="server" />  
  
    <asp:TextBox ID="AutoApproveLimit" ReadOnly="true" runat="server" />  
    <br /><br />  
    <asp:Label ID="lblExpenseTotal" Text="Expense Total:" runat="server" />  
  
    <asp:TextBox ID="ExpenseTotal" runat="server" />  
    <br /><br />  
    ```  
  
3.  확장의 **ExpenseReportInitForm.aspx** 파일을 **솔루션 탐색기** 해당 종속 파일을 표시 합니다.  
  
4.  ExpenseReportInitForm.aspx 파일에 대 한 바로 가기 메뉴를 열고 **코드 보기**합니다.  
  
5.  대체는 `Page_Load` 메서드를 다음 예제로:  
  
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
  
6.  대체는 `GetInitiationData` 메서드를 다음 예제로:  
  
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
  
## <a name="customizing-the-workflow"></a>워크플로 사용자 지정  
 그런 다음 워크플로 사용자 지정 합니다. 이상에서는 두 가지 양식을 워크플로에 연결 합니다.  
  
#### <a name="to-customize-the-workflow"></a>워크플로 사용자 지정 하려면  
  
1.  프로젝트에서 Workflow1 열어 워크플로 디자이너에서 워크플로 표시 합니다.  
  
2.  에 **도구 상자**, 확장 하 고는 **Windows Workflow v3.0** 노드를 찾습니다는 **IfElse** 활동입니다.  
  
3.  다음 단계 중 하나를 수행 하 여이 활동을 워크플로에 추가 합니다.  
  
    -   에 대 한 바로 가기 메뉴를 열고는 **IfElse** 활동 선택 **복사**, 아래의 줄에 대 한 바로 가기 메뉴를 열고는 **onWorkflowActivated1** 워크플로 디자이너의 활동 선택한 후 **붙여넣기**합니다.  
  
    -   끌어서는 **IfElse** 활동을는 **도구 상자**, 아래의 줄에 연결 하 고는 **onWorkflowActiviated1** 워크플로 디자이너에서 활동입니다.  
  
4.  도구 상자에서 확장의 **SharePoint 워크플로** 노드를 찾습니다는 **CreateTask** 활동입니다.  
  
5.  다음 단계 중 하나를 수행 하 여이 활동을 워크플로에 추가 합니다.  
  
    -   에 대 한 바로 가기 메뉴를 열고는 **CreateTask** 활동 선택 **복사**, 둘 중 하나에 대 한 바로 가기 메뉴를 열고 **여기에 작업 놓기** 내의 영역  **IfElseActivity1** 워크플로 디자이너에서 선택한 후 **붙여넣기**합니다.  
  
    -   끌어서는 **CreateTask** 활동을는 **도구 상자** 둘 중 하나에 **여기에 작업 놓기** 내의 영역 **IfElseActivity1**합니다.  
  
6.  에 **속성** 창의 속성 값을 입력 *taskToken* 에 대 한는 **CorrelationToken** 속성입니다.  
  
7.  확장 된 **CorrelationToken** 더하기 기호를 선택 하 여 속성 (![TreeView 더하기 기호](../sharepoint/media/plus.gif "TreeView 더하기 기호")) 옆에 있는 합니다.  
  
8.  에 있는 드롭다운 화살표를 선택는 **OwnerActivityName** 하위 속성을 설정 하 고는 *Workflow1* 값입니다.  
  
9. 선택은 **TaskId** 속성을 선택한 후 줄임표 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표"))는 표시하려면단추**바인딩 속성** 대화 상자.  
  
10. 선택 된 **새 멤버에 바인딩** 탭을 선택는 **필드 만들기** 옵션 단추를 선택한 후는 **확인** 단추 합니다.  
  
11. 선택은 **TaskProperties** 속성을 선택한 후 줄임표 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표"))는 표시하려면단추 **속성을 바인딩할** 대화 상자.  
  
12. 선택 된 **새 멤버에 바인딩** 탭을 선택는 **필드 만들기** 옵션 단추를 선택한 후는 **확인** 단추 합니다.  
  
13. 에 **도구 상자**를 확장 하 고는 **SharePoint 워크플로** 노드를 찾습니다는 **LogToHistoryListActivity** 활동입니다.  
  
14. 다음 단계 중 하나를 수행 하 여이 활동을 워크플로에 추가 합니다.  
  
    -   에 대 한 바로 가기 메뉴를 열고는 **LogToHistoryListActivity** 활동 선택 **복사**, 다른 작업에 대 한 바로 가기 메뉴를 열고 **여기에 작업 놓기** 내의영역**IfElseActivity1** 워크플로 디자이너에서 선택한 후 **붙여넣기**합니다.  
  
    -   끌어서는 **LogToHistoryListActivity** 활동을는 **도구 상자**, 다른 끌어다 놓으십시오 **여기에 작업 놓기** 영역 내에서 **IfElseActivity1** .  
  
## <a name="adding-code-to-the-workflow"></a>워크플로에 코드 추가  
 워크플로 기능을 제공 하려면 다음으로 코드를 추가 합니다.  
  
#### <a name="to-add-code-to-the-workflow"></a>코드의 워크플로에 추가 하려면  
  
1.  에 대 한 바로 가기 메뉴를 열고는 **createTask1** 워크플로 디자이너의 활동 선택 **코드 보기**합니다.  
  
2.  다음 메서드를 추가 합니다.  
  
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
    >  코드에서 대체 `somedomain\\someuser` 작업은 만들 수 있는와 같은 도메인 및 사용자 이름으로 "`Office\\JoeSch`"입니다. 테스트를 위해 사용 하 여 개발 계정을 사용 하도록 쉽습니다.  
  
3.  아래는 `MethodInvoking` 메서드를 다음 예제에서는 추가:  
  
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
  
4.  워크플로 디자이너에서 선택 된 **ifElseBranchActivity1** 활동입니다.  
  
5.  에 **속성** 창에 있는 드롭다운 화살표를 선택는 **조건** 속성을 설정 합니다는 *코드 조건* 값입니다.  
  
6.  확장의 **조건** 더하기 기호를 선택 하 여 속성 (![TreeView 더하기 기호](../sharepoint/media/plus.gif "TreeView 더하기 기호")) 옆에 다음 값을 설정 하 고 *checkApprovalNeeded* .  
  
7.  워크플로 디자이너에 대 한 바로 가기 메뉴를 열고는 **logToHistoryListActivity1** 활동을 선택한 후 **생성 처리기** 에 대 한 빈 메서드를 생성 하는 `MethodInvoking` 이벤트입니다.  
  
8.  대체는 `MethodInvoking` 코드를 다음 코드로:  
  
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
  
9. 프로그램을 디버깅 하려면 F5 키를 선택 합니다.  
  
     이 응용 프로그램을 컴파일할 수 있는 패키지로, 배포, 해당 기능을 활성화, 재생 되는 [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] 응용 프로그램 풀 및 다음 처음에 지정 된 위치에서 브라우저는 **사이트 Url** 속성입니다.  
  
## <a name="associating-the-workflow-to-the-documents-list"></a>문서 목록에 워크플로 연결  
 다음으로, 워크플로 연결 양식을 사용 하 여 워크플로 연결 하 여 표시는 **SharedDocuments** SharePoint 사이트의 목록입니다.  
  
#### <a name="to-associate-the-workflow"></a>워크플로 연결 하려면  
  
1.  선택 된 **공유 문서** 빠른 실행 모음에서 링크 합니다.  
  
2.  선택 된 **라이브러리** 링크를 **라이브러리 도구** 탭을 선택 합니다는 **라이브러리 설정** 리본 단추입니다.  
  
3.  **사용 권한 및 관리** 섹션에서 선택 된 **워크플로 설정** 링크 선택한 후는 **워크플로 추가** 링크를 **워크플로** 페이지.  
  
4.  워크플로 설정 페이지의 맨 위 목록에서 선택 된 **경비 보고서-Workflow1** 서식 파일입니다.  
  
5.  다음 필드에 입력 **ExpenseReportWorkflow** 선택한 후는 **다음** 단추입니다.  
  
     그러면 연결 된 워크플로 **공유 문서** 나열 하 고 워크플로 연결 폼이 표시 됩니다.  
  
6.  에 **자동 승인 제한** 텍스트 상자에 입력 **1200** 선택한 후는 **워크플로 연결** 단추입니다.  
  
## <a name="starting-the-workflow"></a>워크플로 시작  
 다음으로, 문서 중 하나에 워크플로 연결의 **공유 문서** 목록 워크플로 시작 양식을 표시 합니다.  
  
#### <a name="to-start-the-workflow"></a>워크플로 시작 하려면  
  
1.  SharePoint 페이지에서 선택 된 **홈** 단추입니다.  
  
2.  선택 된 **공유 문서** 표시 하려면 빠른 실행 모음에서 링크는 **공유 문서** 목록입니다.  
  
3.  선택 된 **문서** 링크를 **라이브러리 도구** 페이지 맨 위에 있는 탭을 선택 합니다는 **문서 업로드** 새 문서를 업로드 하려면 리본에서 단추는 **공유 문서** 목록입니다.  
  
4.  에 **문서 업로드** 대화 상자에서 선택 하는 **찾아보기** 단추, 문서 파일 선택를 선택는 **열려** 단추를 선택한 후는 **확인** 단추입니다.  
  
     이 대화 상자에서 문서에 대 한 설정을 변경할 수 있지만 선택 하 여 기본값 그대로 **저장** 단추입니다.  
  
5.  표시 되 면 선택한 후 드롭다운 화살표를 업로드 한 문서를 선택는 **워크플로** 항목입니다.  
  
6.  ExpenseReportWorkflow 옆에 있는 이미지를 선택 합니다.  
  
     워크플로 시작 양식을 표시 됩니다. (값에 표시 되는 **자동 승인 제한** 상자는 읽기 전용 응용 프로그램 폼의 입력 되었으므로.)  
  
7.  에 **비용 합계** 텍스트 상자에 입력 **1600**, 선택한 후는 **워크플로 시작** 단추입니다.  
  
     그러면 표시 됩니다는 **공유 문서** 목록을 다시 합니다. 이라는 새 열 **ExpenseReportWorkflow** 값과 **Completed** 워크플로가 방금 시작 항목에 추가 됩니다.  
  
8.  업로드 한 문서 옆의 드롭다운 화살표를 선택 하 고 선택는 **워크플로** 항목 워크플로 상태 페이지를 표시 합니다. 선택 된 **완료** 아래 **워크플로가 완료**합니다. 아래는 작업이 표시 됩니다는 **작업** 섹션.  
  
9. 작업 세부 정보를 표시 하기 위해 작업의 제목을 선택 합니다.  
  
10. 로 돌아가기는 **SharedDocuments** 나열 하 고 동일한 문서 또는 다른 중 하나를 사용 하 여 워크플로 다시 시작 합니다.  
  
11. 연결 페이지에 입력 된 금액 보다 작은 시작 페이지에서 금액을 입력 하십시오 (**1200**).  
  
     이러한 경우 기록 목록에 있는 항목 작업 대신 생성 됩니다. 에 항목이 표시 됩니다는 **워크플로 기록** 워크플로 상태 페이지의 섹션입니다. 에 메시지를 확인는 **결과** 기록 이벤트의 열입니다. 에 입력 한 텍스트가 포함 된 `logToHistoryListActivity1.MethodInvoking` 자동 승인 된 금액을 포함 하는 이벤트입니다.  
  
## <a name="next-steps"></a>다음 단계  
 다음이 항목에서는 워크플로 템플릿을 만드는 방법에 대해 자세히 알아볼 수 있습니다.  
  
-   SharePoint 워크플로에 대 한 자세한 참조 [Windows SharePoint Services에서 워크플로](http://go.microsoft.com/fwlink/?LinkID=166275)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 워크플로 솔루션 만들기](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [연습: 워크플로에 응용 프로그램 페이지 추가](../sharepoint/walkthrough-add-an-application-page-to-a-workflow.md)  
  
  