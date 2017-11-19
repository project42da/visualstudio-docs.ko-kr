---
title: "연습: 생성 및 SharePoint 워크플로 솔루션을 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Workflow.WorkflowConditions
- VS.SharePointTools.Workflow.WorkflowList
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
ms.assetid: 81756490-ab5a-4fa4-96c6-eed2cfbf8374
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d64c0767cce43d5b157fca82cc3e1e210a2f8c58
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-and-debugging-a-sharepoint-workflow-solution"></a>연습: SharePoint 워크플로 솔루션 만들기 및 디버깅
  이 연습에서는 기본 순차 워크플로 템플릿을 만드는 방법을 보여 줍니다. 워크플로에서 문서 검토 되었는지 여부를 결정 하는 공유 문서 라이브러리의 속성을 검사 합니다. 문서를 검토 하는 경우 워크플로가 완료 합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   SharePoint 목록 정의 순차 워크플로 프로젝트를 만들어 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
-   워크플로 활동을 작성 합니다.  
  
-   워크플로 활동 이벤트를 처리 합니다.  
  
> [!NOTE]  
>  이 연습에서는 순차 워크플로 프로젝트를 사용 하지만 프로세스는 상태 시스템 워크플로 프로젝트에 대해 동일 합니다.  
>   
>  또한 컴퓨터 표시 될 수 있습니다 다른 이름 또는 위치가 시스템에 일부 Visual Studio 사용자 인터페이스 요소 다음 지침에 설명 합니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio.  
  
## <a name="adding-properties-to-the-sharepoint-shared-documents-library"></a>문서 라이브러리를 공유 하는 SharePoint에 속성 추가  
 에 있는 문서의 상태 검토를 추적 하는 **공유 문서** 라이브러리 만듭니다 공유 문서에 대 한 새 속성을 3 개의 SharePoint 사이트에서: `Status`, `Assignee`, 및 `Review Comments`합니다. 이러한 속성에 정의 된 **공유 문서** 라이브러리입니다.  
  
#### <a name="to-add-properties-to-the-sharepoint-shared-documents-library"></a>문서 라이브러리 SharePoint 공유에 속성 추가  
  
1.  Http:// 같은 SharePoint 사이트를 열고\<시스템 이름 > / 웹 브라우저에서 SitePages/Home.aspx 합니다.  
  
2.  빠른 실행 모음에서 **SharedDocuments**합니다.  
  
3.  선택 **라이브러리** 에 **라이브러리 도구** 리본 메뉴를 선택한 후는 **열 만들기** 새 열을 만들려면 리본에서 단추입니다.  
  
4.  열의 이름을 **문서 상태**, 해당 형식으로 설정 **선택 (메뉴에서 선택할 수)**다음 세 가지 선택 옵션을 지정 하 고 눌러는 **확인** 단추:  
  
    -   **검토 필요**  
  
    -   **검토 완료**  
  
    -   **요청 된 변경 내용**  
  
5.  두 개 이상의 열을 만들고 이름을 **책임자** 및 **검토 주석**합니다. 텍스트의 여러 줄으로의 텍스트를 한 줄으로 책임자 열 형식과 검토 주석 열 형식을 설정 합니다.  
  
## <a name="enabling-documents-to-be-edited-without-requiring-a-check-out"></a>문서를 체크 아웃 필요 없이 편집을 사용 하도록 설정  
 체크 아웃 하지 않고도 문서를 편집할 수 있도록 워크플로 템플릿을 테스트 하는 것이 쉽습니다. 다음 절차에는 사용할 수 있도록 SharePoint 사이트를 구성 합니다.  
  
#### <a name="to-enable-documents-to-be-edited-without-checking-them-out"></a>체크 아웃 하지 않고 편집할 문서를 사용 하도록 설정 하려면  
  
1.  빠른 실행 모음에서 선택 된 **공유 문서** 링크 합니다.  
  
2.  에 **라이브러리 도구** 리본에서 선택 된 **라이브러리** 탭을 선택 합니다는 **라이브러리 설정** 표시 하려면 단추는 **문서라이브러리설정** 페이지.  
  
3.  **일반 설정** 섹션에서 선택 된 **버전 관리 설정** 표시 하려면 링크는 **버전 관리 설정** 페이지.  
  
4.  확인에 대 한 설정을 **문서를 편집 하려면 먼저 체크 아웃 해야** 은 **아니요**합니다. 그렇지 않은 경우 변경 **아니요** 선택한 후는 **확인** 단추입니다.  
  
5.  브라우저를 닫습니다.  
  
## <a name="creating-a-sharepoint-sequential-workflow-project"></a>SharePoint 순차 워크플로 프로젝트 만들기  
 순차 워크플로 마지막 작업이 완료 될 때까지 순서 대로 실행 되는 일련의 단계가 있습니다. 이 절차에서는 공유 문서 목록에 적용 되는 순차 워크플로 만듭니다. 워크플로 마법사 사용 하면 사이트 정의 또는 목록 정의 워크플로가 연결 하 고 워크플로가 시작 시기를 결정할 수 있습니다.  
  
#### <a name="to-create-a-sharepoint-sequential-workflow-project"></a>SharePoint 순차 워크플로 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로**, **프로젝트** 표시 하는 **새 프로젝트** 대화 상자.  
  
3.  확장 하 고는 **SharePoint** 노드 아래의 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **2010** 노드.  
  
4.  에 **템플릿** 창, 선택는 **SharePoint 2010 프로젝트** 서식 파일입니다.  
  
5.  에 **이름** 상자에 입력 **MySharePointWorkflow** 선택한 후는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
6.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지를 선택 합니다는 **팜 솔루션으로 배포** 옵션 단추를 선택한 후는 **마침** 적용할 단추는 신뢰 수준 및 기본 사이트입니다.  
  
     이 단계는 팜 솔루션으로 워크플로 프로젝트에 대 한 옵션만 사용할 수 솔루션에 대 한 신뢰 수준을 설정합니다. 자세한 내용은 참조 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)합니다.  
  
7.  **솔루션 탐색기**, 프로젝트 노드를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **새 항목 추가**합니다.  
  
8.  아래의 **Visual C#** 또는 **Visual Basic**를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
9. 에 **템플릿** 창 선택는 **순차 워크플로 (팜 솔루션에만 해당)** 서식 파일을 선택한 후는 **추가** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
10. 에 **디버깅에 대 한 워크플로 이름을 지정** 페이지에서 기본 이름을 적용 (**MySharePointWorkflow-Workflow1**). 기본 워크플로 템플릿 형식 값을 유지 **목록 워크플로**를 선택한 후는 **다음** 단추입니다.  
  
11. 에 **Visual Studio 디버그 세션에서 워크플로 자동으로 연결 하 시겠습니까?** 페이지를 선택 합니다는 **다음** 단추의 모든 기본 설정을 그대로를 합니다.  
  
     이 단계는 워크플로 공유 문서 라이브러리를 자동으로 연결 합니다.  
  
12. 에 **워크플로 시작 방법에 대 한 조건을 지정** 페이지에서 기본 옵션을 선택는 **워크플로를 시작할 방법을 선택 하십시오?** 선택한 섹션의 **마침** 단추입니다.  
  
     이 페이지를 사용 하면 워크플로가 시작 되는 시기를 지정할 수 있습니다. 기본적으로 워크플로 시작 하거나 사용자 워크플로 연결 되는 항목을 만들 때 SharePoint에서가 수동으로 시작 합니다.  
  
## <a name="creating-workflow-activities"></a>워크플로 활동 만들기  
 워크플로가 하나 이상 포함 될 *활동* 작업을 수행할 동작을 나타냅니다. 워크플로 디자이너를 사용 하는 워크플로에 대 한 작업을 정렬 합니다. 이 절차에서는 추가 될 두 활동을 워크플로에: HandleExternalEventActivity 및 OnWorkFlowItemChanged 합니다. 에 있는 문서의 검토 상태를 모니터링 하는 이러한 활동은 **공유 문서** 목록  
  
#### <a name="to-create-workflow-activities"></a>워크플로 작업을 만들려면  
  
1.  워크플로 디자이너에서 워크플로 표시 합니다. 그렇지 않은 경우 다음 열고 **Workflow1.cs** 또는 **Workflow1.vb** 에 **솔루션 탐색기**합니다.  
  
2.  디자이너에서 선택 된 **OnWorkflowActivated1** 활동입니다.  
  
3.  에 **속성** 창 입력 **onWorkflowActivated** 옆에 **호출** 속성을 Enter 키를 선택 합니다.  
  
     코드 편집기가 열리고 onWorkflowActivated 라는 이벤트 처리기 메서드 Workflow1 코드 파일에 추가 됩니다.  
  
4.  워크플로 디자이너로 다시 전환 하 고, 도구 상자를 열고, 다음 확장은 **Windows Workflow v3.0** 노드.  
  
5.  에 **Windows Workflow v3.0** 의 노드는 **도구 상자**, 다음 단계 중 하나를 수행 합니다.  
  
    1.  에 대 한 바로 가기 메뉴를 열고는 **동안** 활동을 선택한 후 **복사**합니다. 워크플로 디자이너에서 아래의 줄에 대 한 바로 가기 메뉴를 열고는 **onWorkflowActivated1** 활동을 선택한 후 **붙여넣기**합니다.  
  
    2.  끌어서는 **동안** 활동을는 **도구 상자** 워크플로 디자이너에 활동 아래의 줄에 연결 하 고는 **onWorkflowActivated1** 활동입니다.  
  
6.  선택 된 **WhileActivity1** 활동입니다.  
  
7.  에 **속성** 창의 설정 **조건** 코드 조건에 있습니다.  
  
8.  확장의 **조건** 속성을 입력 **isWorkflowPending** 자식 옆에 있는 **조건** 속성을 Enter 키를 선택 합니다.  
  
     코드 편집기가 열리고 isWorkflowPending 라는 메서드가 Workflow1 코드 파일에 추가 됩니다.  
  
9. 워크플로 디자이너로 다시 전환 하 고, 도구 상자를 열고, 다음 확장은 **SharePoint 워크플로** 노드.  
  
10. 에 **SharePoint 워크플로** 의 노드는 **도구 상자**, 다음 단계 중 하나를 수행 합니다.  
  
    -   에 대 한 바로 가기 메뉴를 열고는 **OnWorkflowItemChanged** 활동을 선택한 후 **복사**합니다. 워크플로 디자이너에서 내부 줄에 대 한 바로 가기 메뉴를 열고는 **whileActivity1** 활동을 선택한 후 **붙여넣기**합니다.  
  
    -   끌어서는 **OnWorkflowItemChanged** 활동을는 **도구 상자** 워크플로 디자이너에 활동 내의 줄에 연결 하 고는 **whileActivity1** 활동입니다.  
  
11. 선택 된 **onWorkflowItemChanged1** 활동입니다.  
  
12. 에 **속성** 창에서 다음 표에 표시 된 대로 속성을 설정 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**CorrelationToken**|**workflowToken**|  
    |**호출**|**onWorkflowItemChanged**|  
  
## <a name="handling-activity-events"></a>작업 이벤트 처리  
 마지막으로, 각 작업에서 문서의 상태를 확인 합니다. 문서를 검토 하는 경우 워크플로가 완료 됩니다.  
  
#### <a name="to-handle-activity-events"></a>활동 이벤트를 처리 하려면  
  
1.  Workflow1.cs 또는 Workflow1.vb의 맨 위에 다음 필드를 추가 `Workflow1` 클래스입니다. 이 필드는 활동에서 워크플로 완료 했는지 확인 하려면 사용 합니다.  
  
    ```vb  
    Dim workflowPending As Boolean = True  
    ```  
  
    ```csharp  
    Boolean workflowPending = true;  
    ```  
  
2.  다음 메서드를 `Workflow1` 클래스에 추가합니다. 값을 확인 하는이 메서드는 `Document Status` 문서 검토 되었는지 여부를 결정 하는 문서 목록의 속성입니다. 경우는 `Document Status` 속성이로 설정 되어 `Review Complete`, 하면 `checkStatus` 메서드 설정은 `workflowPending` 필드를 **false** 워크플로를 완료할 수 임을 나타냅니다.  
  
    ```vb  
    Private Sub checkStatus()  
        If CStr(workflowProperties.Item("Document Status")) = "Review Complete" Then  
            workflowPending = False  
        End If  
    End Sub   
    ```  
  
    ```csharp  
    private void checkStatus()  
    {  
        if ((string)workflowProperties.Item["Document Status"] == "Review Complete")  
        workflowPending = false;  
    }  
    ```  
  
3.  다음 코드를 추가 하는 `onWorkflowActivated` 및 `onWorkflowItemChanged` 호출 하는 메서드는 `checkStatus` 메서드. 워크플로가 시작 될 때, `onWorkflowActivated` 메서드 호출에서 `checkStatus` 메서드 문서 이미 검토 여부를 확인 합니다. 워크플로 계속 하는 경우 그 검토 되지 않았습니다., 합니다. 문서를 저장 하는 경우는 `onWorkflowItemChanged` 메서드 호출에서 `checkStatus` 다시 문서 검토 되었는지 여부를 결정 하는 메서드. 반면는 `workflowPending` 필드가로 설정 된 **true**, 워크플로 계속 실행 합니다.  
  
    ```vb  
    Private Sub onWorkflowActivated(ByVal sender As System.Object, ByVal e As System.Workflow.Activities.ExternalDataEventArgs)  
        checkStatus()  
    End Sub  
  
    Private Sub onWorkflowItemChanged(ByVal sender As System.Object, ByVal e As System.Workflow.Activities.ExternalDataEventArgs)  
        checkStatus()  
    End Sub  
    ```  
  
    ```csharp  
    private void onWorkflowActivated(object sender, ExternalDataEventArgs e)  
    {  
        // Check the status.  
        checkStatus();  
    }  
  
    private void onWorkflowItemChanged(object sender, ExternalDataEventArgs e)  
    {  
        // Check the status.  
        checkStatus();  
    }  
    ```  
  
4.  다음 코드를 추가 하는 `isWorkflowPending` 의 상태를 확인 하는 `workflowPending` 속성입니다. 문서가 저장 될 때마다는 **whileActivity1** 작업 호출에서 `isWorkflowPending` 메서드. 이 메서드는 <xref:System.Workflow.Activities.ConditionalEventArgs.Result%2A> 속성의는 <xref:System.Workflow.Activities.ConditionalEventArgs> 확인할 개체 여부는 **WhileActivity1** 작업 계속 또는 완료 해야 합니다. 속성이로 설정 된 경우 **true**는 작업이 계속 실행 됩니다. 그렇지 않은 경우 작업이 완료 되 고 워크플로가 완료 합니다.  
  
    ```vb  
    Private Sub isWorkflowPending(ByVal sender As System.Object, ByVal e As System.Workflow.Activities.ConditionalEventArgs)  
        e.Result = workflowPending  
    End Sub  
    ```  
  
    ```csharp  
    private void isWorkflowPending(object sender, ConditionalEventArgs e)  
    {  
        e.Result = workflowPending;  
    }  
    ```  
  
5.  프로젝트를 저장합니다.  
  
## <a name="testing-the-sharepoint-workflow-template"></a>SharePoint 워크플로 템플릿 테스트  
 디버거를 시작할 때 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 워크플로 템플릿을 SharePoint 서버에 배포 하 고 사용 하 여 워크플로 연결의 **공유 문서** 목록입니다. 워크플로 테스트 하려면의 문서에서 워크플로 인스턴스를 시작는 **공유 문서** 목록입니다.  
  
#### <a name="to-test-the-sharepoint-workflow-template"></a>SharePoint 워크플로 템플릿을 테스트 하려면  
  
1.  Workflow1.cs 또는 Workflow1.vb 중단점 설정 옆에 **onWorkflowActivated** 메서드.  
  
2.  F5 키를 선택하여 솔루션을 빌드하고 실행합니다.  
  
     SharePoint 사이트가 나타납니다.  
  
3.  SharePoint의 탐색 창에서 선택 된 **공유 문서** 링크 합니다.  
  
4.  에 **공유 문서** 페이지에서 선택 된 **문서** 링크를 **라이브러리 도구** 탭을 선택 합니다는 **문서 업로드** 단추 .  
  
5.  에 **문서 업로드** 대화 상자에서 선택 하는 **찾아보기** 단추, 문서 파일 선택를 선택는 **열려** 단추를 선택한 후는 **확인** 단추입니다.  
  
     이 선택 된 문서를 업로드는 **공유 문서** 나열 하 고에서 워크플로 시작 합니다.  
  
6.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 디버거는 중단점에서 옆에 중지 확인는 `onWorkflowActivated` 메서드.  
  
7.  실행을 계속 F5 키를 선택 합니다.  
  
8.  여기서 문서에 대 한 설정을 변경할 수 있지만 기본값을 그대로 지금 선택 하 여는 **저장** 단추입니다.  
  
     이 반환 하는 **공유 문서** 기본 SharePoint 웹 사이트의 페이지입니다.  
  
9. 에 **공유 문서** 페이지에서 아래 값은 **MySharePointWorkflow-Workflow1** 열으로 설정 된 **진행 중인**합니다. 이 진행 중인 워크플로의 문서 검토 대기 중이 고 나타냅니다.  
  
10. 에 **공유 문서** 페이지 문서 선택을 선택 하 고 표시 되는 화살표를 선택는 **속성 편집** 메뉴 항목입니다.  
  
11. 설정 **문서 상태** 를 **검토 완료**를 선택한 후는 **저장** 단추입니다.  
  
     이 반환 하는 **공유 문서** 기본 SharePoint 웹 사이트의 페이지입니다.  
  
12. 에 **공유 문서** 페이지에서 아래 값은 **문서 상태** 열으로 설정 된 **검토 완료**합니다. 새로 고침는 **공유 문서** 되어 있는지 확인 하 고 페이지 아래 값은 **MySharePointWorkflow-Workflow1** 열으로 설정 된 **완료 됨**합니다. 이 나타내는 워크플로가 완료 되 고 문서를 검토 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 다음이 항목에서는 워크플로 템플릿을 만드는 방법에 대해 자세히 알아볼 수 있습니다.  
  
-   SharePoint 워크플로 활동에 대 한 자세한 참조 [SharePoint Foundation에 대 한 워크플로 활동](http://go.microsoft.com/fwlink/?LinkId=178992)합니다.  
  
-   Windows Workflow Foundation 활동에 대 한 자세한 참조 [System.Workflow.Activities Namespace](http://go.microsoft.com/fwlink/?LinkId=178993)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 워크플로 솔루션 만들기](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
  