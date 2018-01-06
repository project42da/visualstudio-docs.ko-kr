---
title: "SharePoint 워크플로 솔루션 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VSTO.NewSharePointWorkflowWizard.Page3
- VS.SharePointTools.Workflow.WorkflowName
- VSTO.NewSharePointWorkflowWizard.Page2
- VSTO.NewSharePointWorkflowWizard.Page1
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
ms.assetid: fe79b99a-cb7c-4a14-8d9f-bce0c0805ba0
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 97283921205eaf70c77c054b269ee56f0e1adcd7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-sharepoint-workflow-solutions"></a>SharePoint 워크플로 솔루션 만들기
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]문서 및 SharePoint 웹 사이트에서 목록 항목의 수명 주기를 관리 하는 사용자 지정 워크플로 만드는 데 도움이 되는 도구를 제공 합니다. 제공되는 항목에는 디자이너, 작업 컨트롤 집합 및 필수 어셈블리 참조가 있습니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]도 포함 되어는 **SharePoint 사용자 지정 마법사**를 만들고 워크플로 구성 합니다.  
  
 목록에서 SharePoint 프로젝트를 만들기 위한 필수 구성 요소에 대해 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다. SharePoint에 대 한 자세한 내용은 참조 [Microsoft SharePoint 제품 및 기술](http://go.microsoft.com/fwlink/?LinkId=178470)합니다.  
  
## <a name="workflows-in-sharepoint"></a>SharePoint에서 워크플로  
 SharePoint 라이브러리 또는 목록에는 워크플로 추가 하는 경우에 비즈니스 프로세스 라이브러리 또는 목록에 있는 모든 항목에 적용 합니다. 워크플로 시스템 또는 사용자가을 편집 하 고 검토 한 다음 항목을 보내는 등의 각 항목에 수행 해야 하는 작업을 설명 합니다. 라고 하는 이러한 동작을 *활동*, 워크플로의 구성 요소입니다.  
  
 SharePoint 워크플로 만들 수 있습니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 웹 사이트를 배포 합니다. 워크플로 SharePoint에 배포 된 후에 라이브러리 또는 목록으로 연결 합니다. 또는 수동으로 사용자 프로세스에 의해 자동으로 시작 후 하려면. 워크플로 작업에 대 한 자세한 내용은 참조 [워크플로 사용 하 여 프로세스를 관리할](http://go.microsoft.com/fwlink/?LinkId=79757)합니다.  
  
## <a name="creating-custom-sharepoint-workflows"></a>사용자 지정 SharePoint 워크플로 만들기  
 2 개의 SharePoint 워크플로 프로젝트에서 사용할 수는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]: **순차 워크플로** 및 **상태 시스템 워크플로**합니다.  
  
 A *순차 워크플로* 일련의 단계를 나타냅니다. 단계는 마지막 작업이 완료 될 때까지 차례로 수행 됩니다. 순차 워크플로 항상 엄격 하 게 순서 대로 실행 합니다. 외부 이벤트를 수신 하 고 병렬 논리 흐름 수를 정확 하 게 실행 순서는 달라질 수 있습니다. 다음 그림에는 순차 워크플로의 예가 나와 있습니다.  
  
 ![순차 워크플로](../sharepoint/media/sp-sequential.png "순차 워크플로")  
  
 A *상태 시스템 워크플로* 상태, 전환 및 동작의 집합을 나타냅니다. 상태 시스템 워크플로의 단계를 비동기적으로 실행 합니다. 즉, 차례로 반드시 수행 되지 않습니다 있지만 대신 작업 및 상태에 의해 트리거되는 것입니다. 하나의 상태는 시작 상태로 할당 하 고 그런 다음 이벤트에 따라 전환 되 다른 상태로 키를 누릅니다. 상태 시스템 워크플로의 끝을 결정 하는 최종 상태에 있을 수 있습니다. 다음 다이어그램에는 상태 시스템 워크플로의 예가 나와 있습니다.  
  
 ![상태 시스템 워크플로](../sharepoint/media/sp-state.png "상태 시스템 워크플로")  
  
 워크플로 형식에 대 한 자세한 내용은 참조 [워크플로 유형](http://go.microsoft.com/fwlink/?LinkId=178995)합니다.  
  
### <a name="using-the-wizard"></a>마법사를 사용 하 여  
 SharePoint 워크플로 프로젝트를 만들 때 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 먼저의 설정에 지정 된 **SharePoint 사용자 지정 마법사**합니다. 마법사에서 프로젝트를 만드는 이러한 설정을 사용 **솔루션 탐색기**합니다. 이 프로젝트에는 사용자 지정 SharePoint 워크플로 만드는 데 필요한 어셈블리에 대 한 참조 및 코드 파일, 워크플로 배포 하는 데 사용 되는 여러 파일을 포함 합니다.  
  
 워크플로 만든 후 속성 창에서 해당 속성을 수정할 수 있습니다. 속성 창에서 직접 대부분의 워크플로 속성을 변경할 수 있지만 일부 해야 줄임표 단추를 클릭 하 여 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표"))를 해당 값을 변경 합니다. 이 단추를 다시 시작은 **SharePoint 사용자 지정 마법사**합니다. 값이 변경을 선택 하는 속성을 변경한 후는 **마침** 단추 하 여 종료 합니다.  
  
> [!NOTE]  
>  **워크플로 유형** 속성은 읽기 전용 이며 변경할 수 없습니다. 워크플로 형식을 변경 하려는 경우 다른 워크플로에서 만들어야 합니다.  
  
## <a name="designing-a-sharepoint-workflow"></a>SharePoint 워크플로 설계  
 사용 하 여 비즈니스 프로세스의 모든 단계를 정의 하 고 나면는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 워크플로 디자이너는 SharePoint 워크플로를 설계 합니다. 디자이너를 열려면 두 번 클릭 Workflow1.cs 또는 Workflow1.vb에 **솔루션 탐색기**, 또는 해당 파일 중 하나에 대 한 바로 가기 메뉴를 열고 선택한 후 **열고**합니다.  
  
### <a name="activities"></a>활동  
 워크플로 디자인 하려면 활동을 추가 **도구 상자** 에 *워크플로 일정* 디자이너입니다. 워크플로 일정에는 일련의 활동을 수행 해야 하는 순서에 포함 되어 있습니다.  
  
 두 가지 유형의 활동에는  
  
-   *단순 작업* "1 일에 대 한 지연" 또는 "웹 서비스를 시작 합니다."과 같은 작업의 단일 단위를 수행  
  
-   *복합 활동* 다른 활동을 포함할; 예를 들어 조건부 작업 두 개의 분기를 포함 될 수 있습니다.  
  
 두 형식의 작업 모두에서 사용할 수는 **도구 상자**합니다.  
  
 활동 속성, 메서드 및 이벤트를 가질 수 있습니다. 사용 하 여는 **속성** 활동의 속성을 설정 하는 창입니다.  
  
 사용자 지정 활동을 만들 수도 있습니다. 자세한 내용은 참조 [연습: 사용자 지정 사이트 워크플로 작업 만들기](../sharepoint/walkthrough-create-a-custom-site-workflow-activity.md)합니다.  
  
 작업의 다음 탭에서 구성 된 **도구 상자**:  
  
-   **SharePoint 워크플로**  
  
-   **Windows Workflow v3.0**  
  
-   **Windows Workflow v 3.5**  
  
 일부 핵심 워크플로 활동 SharePoint에서 사용할 수 있습니다. 자세한 내용은 참조 [워크플로 활동에 대 한 Windows SharePoint Services 개요](http://go.microsoft.com/fwlink/?LinkID=156094)합니다.  
  
#### <a name="sharepoint-workflow-activities"></a>SharePoint 워크플로 활동  
 **SharePoint 워크플로** 탭에서 사용 하기 위해 특수 한 활동을 포함할 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]합니다. 이러한 작업은 간단 하 고 문서 수명 주기 워크플로 개발을 간소화 합니다. 에 나열 된 활동에 대 한 자세한 내용은 **SharePoint 워크플로** 탭, 참조 [워크플로 활동에 대 한 Windows SharePoint Services 개요](http://go.microsoft.com/fwlink/?LinkID=156094)합니다.  
  
#### <a name="windows-workflow-activities"></a>Windows 워크플로 활동  
 **Windows Workflow** 탭에서 제공 되는 활동을 포함할는 [!INCLUDE[TLA#tla_workflow](../sharepoint/includes/tlasharptla-workflow-md.md)]합니다. 모든 종류의 Windows workflow 응용 프로그램에 대 한 워크플로 일정을 만들려면 이러한 활동을 사용할 수 있습니다.  
  
 에 나열 된 활동에 대 한 자세한 내용은 **Windows 워크플로** 탭, 참조 [Windows Workflow Foundation 활동](http://go.microsoft.com/fwlink/?LinkID=156096)합니다. Windows Workflow Foundation에 대 한 자세한 내용은 참조 [Windows Workflow Foundation 개요](http://go.microsoft.com/fwlink/?LinkID=128632)합니다.  
  
### <a name="working-with-activities-in-the-designer"></a>활동 디자이너에서 작업  
 워크플로 일정 Windows 워크플로 활동 및 SharePoint 워크플로 활동의 조합을 포함할 수 있습니다.  
  
 디자이너 위치를 지정 하 고 작업을 올바르게 구성할 수 있도록 시각적 표시를 표시 합니다. 작업을 워크플로 일정으로 끌거나 복사하면 워크플로에서 해당 작업의 올바른 위치를 보여 주는 녹색 더하기 기호(+) 아이콘이 디자이너에 표시됩니다. 여기서 됩니다 유효한 위치에 활동을 배치할 수 없습니다. 예를 들어 대기 작업 분기에는 첫 번째 활동으로 보내기 활동을 배치할 수 없습니다. 자세한 내용은 참조 [SharePoint Designer 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=178476)합니다.  
  
## <a name="collecting-information-during-the-workflow"></a>워크플로 중에 정보를 수집합니다.  
 사용자 로부터 정보를 수집 하려는 경우에 미리 정의 된 워크플로에서 시간입니다. 양식 또는 항목 속성을 사용 하 여 정보를 수집할 수 있습니다.  
  
### <a name="forms"></a>양식  
 양식의 질문을 포함 하 고 사용자가 대답에 대 한 방법으로 제공 하는 대화 상자와 비슷합니다.  
  
 네 가지 종류의 워크플로에서 사용할 수 있는 양식이 있습니다.  
  
-   연결  
  
-   시작  
  
-   수정  
  
-   작업  
  
 이러한 조건의 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 연결 및 초기화 폼에 대 한 항목 템플릿을 포함 합니다. 예로 *연결 양식을* 는 워크플로 설치 하는 관리자 수 있는 비용 워크플로의 대 한 지출 한도 같은 워크플로 관련 매개 변수를 입력은 합니다. 예는 *초기화 폼* 는 비용 워크플로의 사용자가 워크플로에 지출 하 금액을 입력 수 있는 하나입니다. 이러한 유형의 폼에 대 한 자세한 내용은 참조 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)합니다.  
  
### <a name="item-properties"></a>항목 속성  
 SharePoint 라이브러리 또는 목록에 있는 항목의 속성을 사용 하 여 사용자 로부터 정보를 수집할 수 있습니다. 주 코드 파일 (Workflow1.cs 또는 Workflow1.vb) 라는 Microsoft.SharePoint.Workflow.SPWorkflowActivationProperties.WorkflowProperties 클래스의 인스턴스를 선언 `workflowProperties`합니다. 사용 된 `workflowProperties` 라이브러리 또는 목록에서 코드의 속성에 액세스 하는 개체입니다. 예를 들어 참조 [연습: 만들기 및 SharePoint 워크플로 솔루션을 디버깅](../sharepoint/walkthrough-creating-and-debugging-a-sharepoint-workflow-solution.md)합니다.  
  
## <a name="debugging-a-sharepoint-workflow-template"></a>SharePoint 워크플로 템플릿 디버깅  
 디버깅할 수 SharePoint 워크플로 프로젝트를 동일한 다른를 디버깅할 때 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 웹 기반 프로젝트입니다. 시작 하는 경우는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버거, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 지정 하는 설정을 사용 하 여는 **SharePoint 사용자 지정 마법사** 를 적절 한 SharePoint 웹 사이트를 열고 워크플로 템플릿을 자동으로 연결 적절 한 라이브러리 또는 목록입니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]또한 연결 된 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 하도록 설정할 디버거는 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 이라는 w3wp.exe 프로세스입니다.  
  
 워크플로 테스트 하려면 수동으로 시작 해야 것입니다. 자세한 내용은 "워크플로에 디버깅" 섹션을 참조 [SharePoint 솔루션 디버깅](../sharepoint/debugging-sharepoint-solutions.md)합니다. 에 대 한 자세한 내용은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 웹 응용 프로그램 디버깅, 참조 [웹 응용 프로그램 디버깅 및 스크립트](/visualstudio/debugger/debugging-web-applications-and-script)합니다.  
  
## <a name="deploying-a-sharepoint-workflow-template"></a>SharePoint 워크플로 템플릿을 배포합니다.  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]SharePoint 워크플로 프로젝트를 다른와 동일 하 게 배포 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트. 자세한 내용은 참조 [패키징 및 SharePoint 솔루션 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)합니다.  
  
## <a name="importing-globally-reusable-workflows"></a>전역으로 재사용 가능한 워크플로 가져오기  
 사이트별 재사용 가능한 워크플로 만들 뿐만 아니라 SharePoint Designer 만들 수 있습니다 *전체적으로 재사용 가능한 워크플로*, 모든 SharePoint 사이트에서 사용할 수 있는 워크플로 합니다. 재사용 가능한 워크플로 가져오기 프로젝트 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 현재 전역으로 재사용 가능한 워크플로 가져오지 않습니다. 그러나 SharePoint Designer를 사용 하 여 전역적으로 다시 사용할 수 있는 워크플로 다시 사용할 수 있는 워크플로로 변환할 하거나 변환 되지 않은 선언적 워크플로로 워크플로 가져옵니다. 자세한 내용은 참조 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[연습: SharePoint 워크플로 솔루션 만들기 및 디버깅](../sharepoint/walkthrough-creating-and-debugging-a-sharepoint-workflow-solution.md)|만들기 및 단순 디버깅 과정을 단계별로 안내 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 워크플로 합니다.|  
|[연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)|완벽 한 기능의 만드는을 단계별로 안내 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 연결 및 초기화 폼으로 워크플로 완료 합니다.|  
|[연습: 워크플로에 응용 프로그램 페이지 추가](../sharepoint/walkthrough-add-an-application-page-to-a-workflow.md)|항목 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md) 워크플로로 입력 된 데이터를 보고 하는 추가.aspx 응용 프로그램 페이지를 추가 하 여 합니다.|  
|[연습: 사용자 지정 사이트 워크플로 작업 만들기](../sharepoint/walkthrough-create-a-custom-site-workflow-activity.md)|두 가지 중요 작업을 수행 하는 방법을 보여 줍니다: 사이트 수준 워크플로 만들고 사용자 지정 워크플로 활동을 만듭니다.|  
|[연습: Visual Studio에 SharePoint Designer의 다시 사용 가능한 워크플로 가져오기](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)|에 SharePoint Designer 2010에서 만든 다시 사용할 수 있는 선언적 워크플로 가져오는 방법을 보여 줍니다.는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트.|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)  
  
  