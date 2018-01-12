---
title: "연습: Visual Studio에 SharePoint Designer의 재사용 가능한 워크플로 가져오기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.WSPImport.ImportWF
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing reusable workflows
- reusable workflows [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 05428f2e702643b88415663249e9f29a9f7d46bc
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio"></a>연습: Visual Studio에 SharePoint Designer의 다시 사용 가능한 워크플로 가져오기
  이 연습에 SharePoint Designer 2010에서 만든 다시 사용할 수 있는 워크플로 가져오는 방법을 보여 줍니다.는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 워크플로 프로젝트입니다.  
  
 SharePoint Designer에서 만든 워크플로 또는 *선언적 워크플로*, 이루어져 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 코드 대신 문입니다. SharePoint Designer 2010 소개 *재사용 가능한 워크플로*, SharePoint 사이트에 여러 목록에서 사용할 수 있는 휴대용, 선언적 워크플로 합니다.  
  
 만든 워크플로 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)], 순차 및 상태 시스템 워크플로 등 라고 *워크플로 코드*합니다. 코드 워크플로 구성 XML 파일 및 코드 모듈 사용자는 워크플로 동작을 지정할 수 있습니다.  
  
 Visual Studio에서는 SharePoint Designer 2010에서 만든 다시 사용할 수 있는 워크플로를 가져와서 SharePoint 사이트에서 사용할 수 있도록 코드 워크플로로 변환할 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   SharePoint Designer에서 간단 하 고 다시 사용할 수 있는 워크플로 만듭니다.  
  
-   .Wsp 파일 및 SharePoint에 SharePoint Designer의 다시 사용할 수 있는 워크플로를 내보냅니다.  
  
-   .Wsp 파일을 가져오는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 다시 사용할 수 있는 워크플로 가져오기 프로젝트를 사용 하 여 합니다.  
  
-   코드를 추가 하 여 워크플로 변경 합니다.  
  
-   SharePoint 사이트에서 가져온된 워크플로 사용합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원 되는 버전 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 합니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio.  
  
-   Microsoft [!INCLUDE[TLA2#tla_office](../sharepoint/includes/tla2sharptla-office-md.md)] SharePoint Designer 2010.  
  
## <a name="create-target-sharepoint-subsites"></a>대상 SharePoint 하위 사이트 만들기  
 두 개의 새 SharePoint 하위 사이트를 만들면 먼저: 변환 된 워크플로 호스트할 다른 SharePoint Designer에서 다시 사용할 수 있는 워크플로 호스트를 하나 있습니다.  
  
#### <a name="to-create-sharepoint-subsites"></a>SharePoint 하위 사이트를 만들려면  
  
1.  SharePoint Designer 2010의 메뉴 모음 선택 **파일**, **새 웹 사이트**합니다.  
  
2.  에 **새 웹 사이트** 대화 상자에서 워크플로 만들거나 http://의 값을 사용 하려는 SharePoint 사이트에는 찾은*SystemName*/ 선택한 후는 **확인** 단추입니다.  
  
     홈 페이지가 나타납니다.  
  
3.  에 **하위 사이트** 섹션에서 **새로** 단추입니다.  
  
4.  에 **새로** 대화 상자에서 선택 **SharePoint 템플릿** 왼쪽된 창에서 목록에서 선택 **팀 사이트** 오른쪽 창의 목록에서 합니다.  
  
5.  에 **웹 사이트의 위치를 지정** 단어를 바꾸고 **하위 사이트** URL에서 **SPD1**, 선택한 후는 **확인** 단추입니다.  
  
     새 하위 사이트에 SharePoint Designer가 열립니다. SharePoint Designer의이 인스턴스를 닫고 다시 첫 번째 인스턴스 (최상위 사이트)로 이동 합니다.  
  
6.  다음 단어이 이번 두 번째 하위 사이트를 만들려면 3-5 단계를 반복 **하위** 에 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] 와 **SPD2**합니다.  
  
## <a name="create-a-sharepoint-designer-reusable-workflow"></a>SharePoint Designer의 다시 사용할 수 있는 워크플로 만들기  
 SharePoint에이 예에 사용할 수 있는 재사용 가능한 워크플로 포함 되어 있지 않으므로, 만들어집니다. 이 간단한 워크플로 특정 타이틀에 있는 작업 목록에 새 작업을 입력 하는 경우 해당 사용자에 게 작업이 할당 됩니다.  
  
#### <a name="to-create-a-sharepoint-designer-reusable-workflow"></a>SharePoint Designer의 다시 사용할 수 있는 워크플로를 만들려면  
  
1.  에 **하위 사이트** 섹션에서 **SPD1** 사이트를 수정 합니다.  
  
2.  리본에서 선택 된 **다시 사용할 수 있는 워크플로** 단추입니다.  
  
     다시 사용할 수 있는 워크플로 만들기 마법사가 나타납니다.  
  
3.  에 **이름** 상자에 입력 **SPD Task Workflow**합니다.  
  
4.  에 **콘텐츠 형식** 목록에서 선택 **작업**를 선택한 후는 **확인** 단추입니다.  
  
     워크플로는 SharePoint Designer 워크플로 디자이너에서 열립니다.  
  
5.  워크플로 디자이너에서 1 단계를 선택한 다음 리본 메뉴는 **조건** 단추입니다.  
  
6.  조건 목록에서 선택 **현재 항목 값이 같은 경우**합니다.  
  
     이 단계 라는 조건을 추가 **값이 같은 경우**합니다.  
  
7.  에 **값이 같은 경우** 조건의 경우 선택 된 **필드** 링크 합니다.  
  
8.  값의 목록에서 선택 **제목**합니다.  
  
9. 에 **값이 같은 경우** 조건의 경우 선택 된 **값** 링크 합니다.  
  
10. 상자에 입력 **새 작업**합니다.  
  
     이제 조건문 **경우 현재 항목: Title이 새 작업과 일치**합니다.  
  
11. 고 조건문 아래의 줄을 선택한 다음 리본 메뉴는 **동작** 단추입니다.  
  
12. 동작의 목록에서 선택 **현재 항목의 필드 집합**합니다.  
  
13. 에 **집합 필드를 값** 동작을 선택 된 **필드** 링크를 선택한 다음 목록에서 선택 **에 할당 된**합니다.  
  
14. 에 **집합 필드를 값** 동작을 선택 된 **값** 링크를 선택한 다음, 기존 사용자 및 그룹의 목록에서 선택 **항목을 만든 사용자**합니다.  
  
15. 선택 된 **추가** 단추를 선택한 후는 **확인** 단추입니다.  
  
     이제이 작업 문은 **설정 할당에 현재 항목: CreatedBy를**합니다.  
  
## <a name="save-and-deploy-the-reusable-workflow"></a>저장 하 고 다시 사용할 수 있는 워크플로 배포 합니다.  
 때문에 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 만.wsp 파일을 가져올 수, 재사용 가능한 워크플로.wsp 파일로 저장 하 고로 가져오기 전에를 SharePoint에 배포 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
> [!IMPORTANT]  
>  다음 절차를 수행 하는 런타임 오류가 발생 하는 경우 SharePoint 사이트에 액세스할 수 있는 시스템에서 절차를 수행 해야 합니다.  
  
#### <a name="to-save-and-deploy-the-reusable-workflow"></a>저장 하 고 다시 사용할 수 있는 워크플로 배포 하려면  
  
1.  SharePoint Designer의 맨 선택는 **저장** 여 진행 상황을 저장 하려면 단추를 선택한 다음 선택에서 **게시** 워크플로를 배포 하는 단추는 **SPD1** SharePoint 사이트 .  
  
2.  탐색 창에서 선택 된 **워크플로** 개체입니다.  
  
3.  아래 **다시 사용할 수 있는 워크플로**, 선택 **SPD Task Workflow**합니다.  
  
4.  리본에서 선택 된 **템플릿으로 저장** 워크플로.wsp 파일로 저장 하려면 단추입니다.  
  
5.  열기는 **SPD1** SharePoint에서.wsp 파일을 보려면 브라우저에서 SharePoint 사이트입니다.  
  
6.  빠른 실행 모음에서 선택 된 **라이브러리** 링크 합니다.  
  
7.  에 **문서 라이브러리** 섹션에서 선택 된 **사이트 자산** 링크 합니다.  
  
     **SPD Task Workflow** 파일이 다른 사이트 자산 함께 나열 됩니다.  
  
8.  파일 목록에서 해당 파일의 이름을 선택합니다.  
  
9. 에 **파일 다운로드** 대화 상자에서 선택 하는 **저장** .wsp 파일을 로컬 시스템에 저장 하려면 단추입니다.  
  
## <a name="import-the-wsp-file-into-visual-studio"></a>Visual Studio에.wsp 파일 가져오기  
 .Wsp 파일을 가져올 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 다시 사용할 수 있는 워크플로 가져오기 프로젝트를 사용 하 여 합니다. 이 프로젝트에서 다시 사용할 수 있는, 선언적 워크플로 코드 워크플로로 워크플로 변환합니다. 워크플로 변환한 후에 동작을 수정할 수 코드를 사용 합니다.  
  
#### <a name="to-import-a-workflow-from-a-wsp-file-and-modify-it"></a>.Wsp 파일에서 워크플로 가져오고 수정  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 메뉴 모음에서 **파일**, **새로**, **프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **SharePoint** 노드 아래의 **Visual C#** 또는 **Visual Basic**는 선택**2010** 노드.  
  
3.  **템플릿** 창에서 선택는 **다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기** 서식 파일을 프로젝트의 이름을 **WorkflowImportProject1**를 선택한 후는 **확인** 단추입니다.  
  
     SharePoint 사용자 지정 마법사가 나타납니다.  
  
4.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지에서 입력 된 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] 이전에 만든 두 번째 SharePoint 하위 사이트에 대 한: http://*시스템 이름*/SPD2 합니다.  
  
5.  에 **이 SharePoint 솔루션에 대 한 신뢰 수준을?** 섹션에서 **팜 솔루션으로 배포** 옵션 단추를 선택한 후는 **다음** 단추입니다.  
  
     샌드박스가 적용 된에 대 한 자세한 내용은 참조는 팜 솔루션 비교 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)합니다.  
  
6.  에 **새 프로젝트 소스 지정** 페이지을 이전에.wsp 파일을 저장 하는 시스템에 위치를 찾아, 파일을 열고 선택 합니다는 **다음** 단추입니다.  
  
    > [!NOTE]  
    >  선택 된 **완료** .wsp 파일에서 사용 가능한 모든 항목을 가져오려면 단추입니다.  
  
     이 재사용 가능한 워크플로 가져오기에 사용할 수 있는 목록이 표시 됩니다.  
  
7.  에 **가져올 항목 선택** 상자에서 선택 하는 **SPD Task Workflow** 워크플로 선택한 후는 **완료** 단추입니다.  
  
     가져오기 작업이 완료 되 면 프로젝트 이라는 **WorkflowImportProject1** 라는 워크플로 포함 된 만들어집니다 **SPD_Workflow_TestFT**합니다. 이 폴더에는 워크플로 정의 파일 Elements.xml과 워크플로 디자이너 파일 (.xoml)입니다. 디자이너에는 두 개의 파일이 포함 되어: 규칙 파일 (.rules) 및 코드 숨김 파일 (.cs 또는.vb 프로젝트의 프로그래밍 언어에 따라).  
  
8.  **솔루션 탐색기**, 삭제는 **Other Imported Files** 폴더입니다.  
  
9. Elements.xml 파일에서 `InstantiationURL="_layouts/IniErkflIP.sspx"`를 삭제합니다.  
  
10. **솔루션 탐색기**, 선택 **WorkflowImportProject1**를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **시작 프로젝트로 설정** 를 설정 **WorkflowImportProject1** 시작 항목으로 합니다.  
  
     프로젝트를 디버깅할 때 바로 목록이 표시 됩니다.  
  
11. 때문에 **다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기** 템플릿이 가져온된 워크플로에 대 한 연결 속성 값을 가져오지 않기에 입력 해야 합니다. 가상 하드 디스크 파일에 대한 중요 정보를 제공하려면  
  
    1.  **솔루션 탐색기**, 선택는 **SPD_Workflow_TestFT** 노드.  
  
    2.  줄임표를 선택 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표"))와 같은 목록 속성 중 하나 옆에 있는 단추는 **대상 목록** 속성입니다.  
  
    3.  SharePoint 사용자 지정 마법사에서 누락 값에 입력 하 고 다음 선택에서 **마침** 단추입니다.  
  
12. .Xoml 파일을 선택한 다음 메뉴 모음에서 메뉴 **보기**, **디자이너** 워크플로 디자이너에서 가져온된 워크플로 볼 수 있습니다.  
  
13. 에 **Windows Workflow v3.0** 의 노드는 **도구 상자**, 다음 단계 중 하나를 수행 합니다.  
  
    -   에 대 한 바로 가기 메뉴를 열고는 **코드** 활동을 선택한 후 **복사**합니다. 워크플로 디자이너에서 아래의 줄에 대 한 바로 가기 메뉴를 열고는 **SequenceActivity1** 활동을 선택한 후 **붙여넣기**합니다.  
  
    -   끌어서는 **코드** 활동을는 **도구 상자** 워크플로 디자이너에 아래의 줄에 연결 하 고는 **SequenceActivity1** 활동입니다.  
  
     명명 된 워크플로 디자이너에 활동을 추가 하는이 **CodeActivity1**합니다. 이 활동에서 워크플로 시작할 때 알림 목록에 공지를 만드는 코드 작업을 추가 합니다.  
  
14. 다음 단계 중 하나를 수행합니다.  
  
    -   두 번 클릭 **CodeActivity1** 하 이벤트 처리기를 생성 하 고 코드를 확인 합니다.  
  
    -   에 **속성** 창에 대 한 **CodeActivity1**의 값을 설정할는 **ExecuteCode** 속성을 **codeActivity_ExecuteCode**합니다.  
  
15. 기존 아래에서 다음 추가 **를 사용 하 여** 또는 **Imports** 문:  
  
     [!code-csharp[SP_SPDWFImport#1](../sharepoint/codesnippet/CSharp/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.cs#1)]
     [!code-vb[SP_SPDWFImport#1](../sharepoint/codesnippet/VisualBasic/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.vb#1)]  
  
16. 대체 `codeActivity1_ExecuteCode` 다음:  
  
     [!code-csharp[SP_SPDWFImport#2](../sharepoint/codesnippet/CSharp/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.cs#2)]
     [!code-vb[SP_SPDWFImport#2](../sharepoint/codesnippet/VisualBasic/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.vb#2)]  
  
## <a name="deploy-the-project-and-associate-the-workflow"></a>프로젝트를 배포 하 고 워크플로 연결  
 다음으로 WorkflowImportProject1를 실행 하려면 SharePoint 사이트에 배포 하 고 워크플로를 보고 테스트할 수정 된 작업 목록에 다음 연결 변환 워크플로 합니다.  
  
#### <a name="to-deploy-the-project-and-associate-the-workflow"></a>프로젝트를 배포 하 고 워크플로 연결 하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 F5 키를 선택하여 변환된 워크플로 프로젝트를 실행하고 배포합니다.  
  
2.  빠른 실행 모음에서 선택 된 **작업** 링크 작업 목록을 표시 합니다.  
  
3.  에 **목록 도구** 탭, 선택는 **항목** 단추를 선택한 후는 **새 항목** 단추입니다.  
  
     **작업-새 항목** 대화 상자가 열립니다.  
  
4.  에 **제목** 상자에 입력 **새 작업**, 선택한 후는 **저장** 단추입니다.  
  
5.  에 **목록 도구** 탭을 선택는 **목록** 단추를 선택한 후는 **목록 설정** 단추입니다.  
  
     **목록 설정** 페이지가 나타납니다.  
  
6.  에 **사용 권한 및 관리** 섹션에서 선택 된 **워크플로 설정** 링크 합니다.  
  
     **워크플로 설정** 페이지가 나타납니다.  
  
7.  선택 된 **워크플로 추가** 링크 합니다.  
  
8.  에 **워크플로** 목록에서 선택 **WorkflowImportProject1-SPD Workflow Test**합니다.  
  
9. 에 **이름** 상자에 입력 **SPD Workflow Test**, 선택한 후는 **확인** 단추입니다.  
  
10. 빠른 실행 모음에서 선택 된 **작업** 목록입니다.  
  
11. 옆에 있는 화살표를 선택 **새 작업**, 한 다음 목록에서 선택 **워크플로**합니다.  
  
12. 에 **새 워크플로 시작** 섹션에 대 한 링크를 선택 합니다 **SPD Workflow Test**, 선택한 후는 **시작** 워크플로 시작 하려면 단추입니다.  
  
    > [!NOTE]  
    >  또는 하면 자동으로 연결할 수는 워크플로 목록이 있는 워크플로 설정 마법사를 실행 하 고 워크플로를 자동 연결을 설정 하 여 합니다.  
  
     두 작업은 워크플로 통해 수행 됩니다: 작업에 자신의 이름이 나타납니다 **담당자** 에 열 및 알림을 표시는 **공지** 목록입니다.  
  
## <a name="see-also"></a>참고 항목  
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)   
 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  