---
title: "연습: SharePoint 워크플로 솔루션 만들기 및 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.Workflow.WorkflowConditions"
  - "VS.SharePointTools.Workflow.WorkflowList"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 워크플로"
  - "워크플로[Visual Studio에서 SharePoint 개발]"
ms.assetid: 81756490-ab5a-4fa4-96c6-eed2cfbf8374
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# 연습: SharePoint 워크플로 솔루션 만들기 및 디버깅
  이 연습에서는 기본적인 순차 워크플로 템플릿을 만드는 방법을 보여 줍니다.  워크플로에서는 공유 문서 라이브러리의 속성을 검사하여 문서가 검토되었는지 여부를 확인합니다.  문서가 검토된 경우 워크플로가 완료됩니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 목록 정의 순차 워크플로 프로젝트 만들기  
  
-   워크플로 작업 만들기  
  
-   워크플로 작업 이벤트 처리  
  
> [!NOTE]  
>  이 연습에서는 순차 워크플로 프로젝트를 사용하지만 상태 시스템 워크플로 프로젝트의 경우에도 프로세스가 동일합니다.  
>   
>  또한 시스템에서 일부 Visual Studio 사용자 인터페이스 요소에 대해 다음 지침에서 설명한 것과 다른 이름 또는 위치를 표시할 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio  
  
## SharePoint 공유 문서 라이브러리에 속성 추가  
 **공유 문서** 라이브러리에 있는 문서의 검토 상태를 추적하려면 SharePoint 사이트의 공유 문서에 대해 `Status`, `Assignee` 및 `Review Comments`의 세 가지 속성을 만듭니다.  이러한 속성은 **공유 문서** 라이브러리에서 정의합니다.  
  
#### SharePoint 공유 문서 라이브러리에 속성을 추가하려면  
  
1.  웹 브라우저에서 SharePoint 사이트\(예: http:\/\/\<시스템 이름\>\/SitePages\/Home.aspx\)를 엽니다.  
  
2.  빠른 실행 모음에서 **공유문서**를 선택합니다.  
  
3.  **라이브러리 도구** 리본에서 **라이브러리** 를 선택한 다음 리본에서 **열 만들기** 버튼을 선택하여 새 열을 만듭니다.  
  
4.  열의 이름을 Document Status로 지정하고 형식을 **선택\(선택 메뉴\)**으로 설정한 후 다음 세 가지 선택 옵션을 지정하고 **확인** 버튼을 선택합니다.  
  
    -   **검토 필요**  
  
    -   **검토 완료**  
  
    -   **변경 요청**  
  
5.  두 개의 열을 더 만들고 해당 이름을 Assignee 및 Review Comments로 지정합니다.  Assignee 열 형식을 한 줄 텍스트로 설정하고 Review Comments 열 형식을 여러 줄 텍스트로 설정합니다.  
  
## 문서를 체크 아웃하지 않고도 편집할 수 있도록 설정  
 문서를 체크 아웃하지 않고 편집할 수 있는 경우 워크플로 템플릿을 보다 손쉽게 테스트할 수 있습니다.  다음 절차에서는 문서를 체크 아웃하지 않고 편집할 수 있도록 SharePoint 사이트를 구성합니다.  
  
#### 문서를 체크 아웃하지 않고도 편집할 수 있도록 설정하려면  
  
1.  빠른 실행 모음에서 **공유 문서** 링크를 선택합니다.  
  
2.  **라이브러리 도구** 리본에서 **라이브러리** 탭을 선택한 다음 **라이브러리 설정** 버튼를 선택하여 **문서 라이브러리 설정** 페이지를 표시합니다.  
  
3.  **일반 설정** 섹션에서 **버전 관리 설정** 링크를 선택하여 **버전 관리 설정** 페이지를 표시합니다.  
  
4.  **문서를 편집하려면 먼저 체크 아웃해야 합니다.**가 **아니요**로 설정되어 있는지 확인합니다.  설정이 이와 다르면 이 설정을 **아니요**로 변경하고 **확인** 버튼을 선택합니다.  
  
5.  브라우저를 닫습니다.  
  
## SharePoint 순차 워크플로 프로젝트 만들기  
 순차 워크플로는 마지막 작업이 끝날 때까지 순서대로 실행되는 일련의 단계입니다.  이 절차에서는 공유 문서 목록에 적용할 순차 워크플로를 만듭니다.  워크플로 마법사를 사용하면 워크플로를 사이트 정의나 목록 정의에 연결하고 워크플로 시작 시기를 결정할 수 있습니다.  
  
#### SharePoint 순차 워크플로 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
3.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 을 선택합니다.  
  
4.  **템플릿** 창에서 **SharePoint 2010 프로젝트** 템플릿을 선택합니다.  
  
5.  **이름** 상자에 MySharePointWorkflow를 입력한 후 **확인** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
6.  **사이트 지정 및 디버깅에 대한 보안 수준** 페이지에서 **팜 솔루션으로 배포** 옵션 버튼을 선택한 다음 **마침** 버튼을 선택하여 신뢰 수준 및 기본 사이트를 수락합니다.  
  
     이 단계에서는 솔루션의 신뢰 수준을 팜 솔루션으로 설정합니다. 이 옵션은 워크플로 프로젝트에 사용할 수 있는 유일한 옵션입니다.  자세한 내용은 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)을 참조하십시오.  
  
7.  **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음 메뉴 모음에서 **프로젝트**, **화면 추가**를 선택합니다.  
  
8.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
9. **템플릿** 창에서 **순차 워크플로 \(팜 솔루션에서만\)** 템플릿을 선택한 후 **추가** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
10. **디버깅에 사용할 워크플로 이름 지정** 페이지에서 기본 이름\(**MySharePointWorkflow \- Workflow1**\)을 적용합니다.  기본 워크플로 템플릿 형식 값인 **목록 워크플로**를 그대로 두고 **다음** 버튼을 선택합니다.  
  
11. **Visual Studio를 통해 디버그 세션에서 워크플로를 자동으로 연결하시겠습니까?** 페이지에서 **다음** 버튼을 선택하여 기본 설정을 모두 적용합니다.  
  
     이 단계에서는 워크플로를 공유 문서 라이브러리에 자동으로 연결합니다.  
  
12. **워크플로 시작 방법에 대한 조건 지정** 페이지의 **워크플로 시작 방법을 선택하십시오.** 섹션에서 기본 옵션이 선택된 상태로 두고 **마침** 버튼을 선택합니다.  
  
     이 페이지에서는 워크플로가 시작되는 시점을 지정할 수 있습니다.  기본적으로 워크플로는 SharePoint에서 사용자가 수동으로 워크플로를 시작하거나 워크플로와 연결된 항목이 만들어지면 시작됩니다.  
  
## 워크플로 작업 만들기  
 워크플로에는 수행할 작업을 나타내는 *작업*이 하나 이상의 포함됩니다.  Workflow Designer를 사용하여 워크플로의 작업을 정렬할 수 있습니다.  이 절차에서는 워크플로에 HandleExternalEventActivity 및 OnWorkFlowItemChanged라는 두 가지 작업을 추가합니다.  두 작업은 **공유 문서** 목록에서 문서의 검토 상태를 모니터링합니다.  
  
#### 워크플로 작업을 만들려면  
  
1.  Workflow Designer에 워크플로가 표시됩니다.  그렇지 않은 경우 **솔루션 탐색기**에서 **Workflow1.cs** 또는 **Workflow1.vb**를 엽니다.  
  
2.  디자이너에서 **OnWorkflowActivated1** 작업을 선택합니다.  
  
3.  **속성** 창에서 **Invoked** 속성 옆에 onWorkflowActivated를 입력하고 Enter 키를 누릅니다.  
  
     코드 편집기가 열리고 onWorkflowActivated라는 이벤트 처리기 메서드가 Workflow1 코드 파일에 추가됩니다.  
  
4.  Workflow Designer로 돌아가서 도구 상자를 열고 **Windows Workflow v3.0** 노드를 확장합니다.  
  
5.  **도구상자** 의 **Windows Workflow v3.0** 노드에서 다음 단계 중 하나를 수행합니다:  
  
    1.  **While** 작업에 대한 바로 가기 메뉴를 열고 **복사** 를 선택합니다.  워크플로 디자이너에서 **onWorkflowActivated1** 작업의 아래 줄에 대한 바로 가기 메뉴의 연 다음 **붙여넣기** 를 선택합니다.  
  
    2.  **While** 작업을 **도구 상자** 에서 워크플로 디자이너로 끌어오고 **onWorkflowActivated1** 작업 아래의 줄에 연결합니다.  
  
6.  **WhileActivity1** 작업을 선택합니다.  
  
7.  **속성** 창에서 **Condition** 을 Code Condition으로 설정합니다.  
  
8.  **Condition** 속성을 확장하고 자식 **Condition** 속성 옆에 isWorkflowPending을 입력한 다음 Enter 키를 누릅니다.  
  
     코드 편집기가 열리고 isWorkflowPending이라는 메서드가 Workflow1 코드 파일에 추가됩니다.  
  
9. Workflow Designer로 돌아가서 도구 상자를 열고 **SharePoint 워크플로** 노드를 확장합니다.  
  
10. **도구상자** 의 **SharePoint Workflow** 노드에서 다음 단계 중 하나를 수행합니다:  
  
    -   **OnWorkflowItemChanged** 작업의 바로 가기 메뉴를 열고 **복사**를 선택합니다.  워크플로 디자이너에서 **whileActivity1** 작업 안의 줄에 대한 바로 가기 메뉴의 연 다음 **붙여넣기** 를 선택합니다.  
  
    -   **OnWorkflowItemChanged** 작업을 **도구상자** 에서 워크플로 디자이너로 끌어오고 **whileActivity1** 작업 내의 줄에 연결합니다.  
  
11. **onWorkflowItemChanged1** 작업을 선택합니다.  
  
12. **속성** 창에서 속성을 다음 표와 같이 설정합니다.  
  
    |Property|값|  
    |--------------|-------|  
    |**CorrelationToken**|**workflowToken**|  
    |**Invoked**|**onWorkflowItemChanged**|  
  
## 작업 이벤트 처리  
 마지막으로 각 작업에서 문서 상태를 확인합니다.  문서가 검토된 경우 워크플로가 완료됩니다.  
  
#### 작업 이벤트를 처리하려면  
  
1.  Workflow1.cs 또는 Workflow1.vb에서 `Workflow1` 클래스의 맨 위에 다음 필드를 추가합니다.  작업에서 이 필드를 사용하여 워크플로를 완료할지 여부를 결정합니다.  
  
    ```vb  
    Dim workflowPending As Boolean = True  
    ```  
  
    ```csharp  
    Boolean workflowPending = true;  
    ```  
  
2.  `Workflow1` 클래스에 다음 메서드를 추가합니다.  이 메서드는 문서 목록의 `Document Status` 속성 값을 검사하여 문서가 검토되었는지 여부를 확인합니다.  `Document Status` 속성이 `Review Complete`로 설정되어 있으면 `checkStatus` 메서드는 `workflowPending` 필드를 **false**로 설정하여 워크플로를 완료할 수 있음을 나타냅니다.  
  
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
  
3.  `onWorkflowActivated` 및 `onWorkflowItemChanged` 메서드에 다음 코드를 추가하여 `checkStatus` 메서드를 호출합니다.  워크플로가 시작되면 `onWorkflowActivated` 메서드는 `checkStatus` 메서드를 호출하여 문서가 이미 검토되었는지 여부를 확인합니다.  문서가 검토되지 않았으면 워크플로가 계속 실행됩니다.  문서를 저장할 때 `onWorkflowItemChanged` 메서드는 `checkStatus` 메서드를 다시 호출하여 문서가 검토되었는지 여부를 확인합니다.  `workflowPending` 필드가 **true**로 설정되어 있는 동안에는 워크플로가 계속 실행됩니다.  
  
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
  
4.  `isWorkflowPending` 메서드에 다음 코드를 추가하여 `workflowPending` 속성의 상태를 확인합니다.  문서가 저장될 때마다 **whileActivity1** 작업에서는 `isWorkflowPending` 메서드를 호출합니다.  이 메서드는 <xref:System.Workflow.Activities.ConditionalEventArgs> 개체의 <xref:System.Workflow.Activities.ConditionalEventArgs.Result%2A> 속성을 검사하여 **WhileActivity1** 작업을 계속해야 할지 마쳐야 할지를 결정합니다.  속성이 **true**로 설정되어 있으면 해당 작업이 계속 실행됩니다.  그렇지 않으면 작업이 완료되고 워크플로가 완료됩니다.  
  
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
  
## SharePoint 워크플로 템플릿 테스트  
 디버거를 시작하면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 워크플로 템플릿을 SharePoint 서버에 배포하고 워크플로를 **공유 문서** 목록에 연결합니다.  워크플로를 테스트하려면 **공유 문서** 목록에 있는 문서에서 워크플로 인스턴스를 시작합니다.  
  
#### SharePoint 워크플로 템플릿을 테스트하려면  
  
1.  Workflow1.cs 또는 Workflow1.vb에서 **onWorkflowActivated** 메서드 옆에 중단점을 설정합니다.  
  
2.  솔루션을 빌드하고 실행하려면 F5 키를 선택합니다.  
  
     SharePoint 사이트가 나타납니다.  
  
3.  SharePoint의 탐색 창에서 **공유 문서** 링크를 선택합니다.  
  
4.  **공유 문서** 페이지에서 **라이브러리 도구** 탭의 **문서** 링크를 선택한 다음 **문서 업로드** 버튼을 선택합니다.  
  
5.  **문서 업로드** 대화 상자에서 **찾아보기** 버튼을 선택하고, 문서 파일을 선택하고, **열기** 버튼을 선택한 다음 **확인** 버튼을 선택합니다.  
  
     이렇게 하면 선택한 문서가 **공유 문서** 목록에 업로드되고 워크플로가 시작됩니다.  
  
6.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 디버거가 `onWorkflowActivated` 메서드 옆의 중단점에서 중지되는지 확인합니다.  
  
7.  F5 키를 선택하여 계속 실행합니다.  
  
8.  여기서 문서 설정을 변경할 수 있지만 일단은 **저장** 버튼을 선택하여 기본값을 그대로 유지합니다.  
  
     이렇게 하면 기본 SharePoint 웹 사이트의 **공유 문서** 페이지로 돌아갑니다.  
  
9. **공유 문서** 페이지에서 **MySharePointWorkflow \- Workflow1** 열 아래의 값이 **진행 중** 으로 설정되어 있는지 확인합니다.  이는 워크플로가 진행 중이고 문서 검토가 대기 중임을 나타냅니다.  
  
10. **공유 문서** 페이지에서, 문서를 선택하고, 나타나는 화살표를 선택한 다음 **속성 편집** 메뉴 항목을 선택합니다.  
  
11. **Document Status** 를 **Review Complete** 로 설정하고 **저장** 버튼을 선택합니다.  
  
     이렇게 하면 기본 SharePoint 웹 사이트의 **공유 문서** 페이지로 돌아갑니다.  
  
12. **공유 문서** 페이지에서 **문서 상태** 열 아래의 값이 **검토 완료**로 설정되어 있는지 확인합니다.  **공유 문서** 페이지를 새로고침하고 **MySharePointWorkflow \- Workflow1** 열 아래의 값이 **완료됨** 으로 설정되어 있는지 확인합니다.  이는 워크플로가 완료되고 문서가 검토되었음을 나타냅니다.  
  
## 다음 단계  
 다음 항목에서는 워크플로 템플릿을 만드는 방법에 대해 더 자세히 설명합니다.  
  
-   SharePoint 워크플로 작업에 대한 자세한 내용은 [SharePoint Foundation의 워크플로 작업](http://go.microsoft.com/fwlink/?LinkId=178992) 을 참조하십시오.  
  
-   Windows Workflow Foundation 작업에 대한 자세한 내용은 [System.Workflow.Activities 네임스페이스](http://go.microsoft.com/fwlink/?LinkId=178993) 을 참조하십시오.  
  
## 참고 항목  
 [SharePoint 워크플로 솔루션 만들기](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
  