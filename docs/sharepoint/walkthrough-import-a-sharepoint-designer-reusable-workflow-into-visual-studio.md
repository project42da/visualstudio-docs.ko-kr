---
title: "연습: Visual Studio에 SharePoint Designer의 다시 사용 가능한 워크플로 가져오기"
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
  - "VS.SharePointTools.WSPImport.ImportWF"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 재사용 가능한 워크플로 가져오기"
  - "재사용 가능한 워크플로[Visual Studio에서 SharePoint 개발]"
ms.assetid: a6550615-4433-4aba-8bdf-0fcbf8dbcf97
caps.latest.revision: 35
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 34
---
# 연습: Visual Studio에 SharePoint Designer의 다시 사용 가능한 워크플로 가져오기
  이 연습에서는 SharePoint Designer 2010에서 만든 다시 사용할 수 있는 워크플로를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 워크플로 프로젝트로 가져오는 방법을 보여 줍니다.  
  
 SharePoint Designer에서 만든 워크플로, 즉 *선언적 워크플로*는 코드 대신 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 문으로 구성됩니다.  SharePoint Designer 2010에서는 SharePoint 사이트의 여러 목록에서 사용할 수 있는 이식 가능한 선언적 워크플로인 *다시 사용할 수 있는 워크플로*를 소개합니다.  
  
 순차 워크플로, 상태 시스템 워크플로 등 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] 에서 만든 워크플로를 *코드 워크플로* 라고 합니다.  코드 워크플로는 사용자가 워크플로 동작을 사용자 지정할 수 있는 코드 모듈과 XML 파일로 구성됩니다.  
  
 Visual Studio을 사용하면 SharePoint Designer 2010에서 만든 다시 사용할 수 있는 워크플로를 가져와 SharePoint 사이트에서 사용할 코드 워크플로로 변환할 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   SharePoint Designer에서 간단한 다시 사용할 수 있는 워크플로 만들기  
  
-   SharePoint Designer의 다시 사용할 수 있는 워크플로를 .wsp 파일 및 SharePoint로 내보내기  
  
-   다시 사용할 수 있는 워크플로 가져오기 프로젝트를 사용하여 .wsp 파일을 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]로 가져오기  
  
-   코드를 추가하여 워크플로 변경  
  
-   SharePoint 사이트에서 가져온 워크플로 사용  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio  
  
-   Microsoft [!INCLUDE[TLA2#tla_office](../sharepoint/includes/tla2sharptla-office-md.md)] SharePoint Designer 2010  
  
## 대상 SharePoint 하위 사이트 만들기  
 먼저 SharePoint Designer의 다시 사용할 수 있는 워크플로를 호스팅할 하위 사이트와 변환된 워크플로를 호스팅할 하위 사이트 등 두 개의 새로운 SharePoint 하위 사이트를 만듭니다.  
  
#### SharePoint 하위 사이트를 만들려면  
  
1.  SharePoint 디자이너 2010의 메뉴 모음에서 **파일**, **새 웹 사이트** 를 선택합니다.  
  
2.  **새 빈 웹 사이트** 대화 상자에서 워크플로를 만들려는 SharePoint 사이트로 이동하거나 http:\/\/*SystemName* 의 값을 사용하고 **확인** 버튼을 선택합니다.  
  
     홈 페이지가 나타납니다.  
  
3.  **하위 사이트** 섹션에서 **새로 만들기** 버튼을 선택합니다.  
  
4.  **새로 만들기** 대화 상자에서, 왼쪽 창의 목록에서 **SharePoint 템플릿** 을 선택하고 오른쪽 창의 목록에선 **팀 사이트** 를 선택합니다.  
  
5.  **웹 사이트의 위치를 지정하십시오.** 상자에서 URL의 단어 **subsite** 를 SPD1로 바꾼 다음 **확인** 버튼을 선택합니다.  
  
     SharePoint Designer에 새 하위 사이트가 열립니다.  이 SharePoint Designer 인스턴스를 닫고 첫 번째 인스턴스\(최상위 사이트\)로 돌아갑니다.  
  
6.  3 \- 5단계를 반복하여 둘째 하위 사이트를 만듭니다. 이번에는 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)]의 단어 **subsite**를 SPD2로 바꿉니다.  
  
## SharePoint Designer에서 다시 사용할 수 있는 워크플로 만들기  
 SharePoint에는 이 예제에 사용할 수 있는 다시 사용할 수 있는 워크플로가 없으므로 새로 만듭니다.  이 간단한 워크플로에서는 사용자가 특정 제목을 가진 새 작업을 작업 목록에 입력하면 작업이 해당 사용자에게 할당됩니다.  
  
#### SharePoint Designer에서 다시 사용할 수 있는 워크플로를 만들려면  
  
1.  **하위사이트** 섹션에서 **SPD1** 사이트를 선택하여 수정합니다.  
  
2.  리본 메뉴에서 **다시 사용할 수 있는 워크플로** 버튼을 선택합니다.  
  
     다시 사용할 수 있는 워크플로 만들기 마법사가 나타납니다.  
  
3.  **이름** 상자에 SPD Task Workflow를 입력합니다.  
  
4.  **콘텐츠 형식** 목록에서 **작업** 을 선택한 다음 **확인** 버튼을 선택합니다.  
  
     SharePoint Designer Workflow Designer에서 워크플로가 열립니다.  
  
5.  워크플로 디자이너에서 1 단계를 선택한 다음, 리본 메뉴에서 **조건** 버튼을 선택합니다.  
  
6.  조건 목록에서 **현재 항목 필드와 값이 일치 하는 경우** 를 선택합니다.  
  
     이 단계에선 **값이 같은 경우** 조건을 추가합니다.  
  
7.  **필드와 값이 일치하는 경우** 조건에서 **필드** 링크를 선택합니다.  
  
8.  값 목록에서 **제목**을 선택합니다.  
  
9. **필드와 값이 일치하는 경우** 조건에서 **값** 링크를 선택합니다.  
  
10. 상자에 New task를 입력합니다.  
  
     이제 조건문이 **현재 항목:Title이 새 작업과 일치하는 경우**로 표시됩니다.  
  
11. 조건 문 아래 줄을 선택한 다음, 리본 메뉴에서 **작업** 버튼을 선택합니다.  
  
12. 작업 목록에서 **현재 항목의 필드 설정** 을 선택합니다.  
  
13. **필드를 값으로 설정** 작업에서 **필드** 링크를 선택한 다음, 목록에서 **담당자** 를 선택합니다.  
  
14. **필드 값을 설정** 작업에서 **값** 링크를 선택한 다음, 기존 사용자 및 그룹 목록에서 **항목을 만든 사용자** 을 선택합니다.  
  
15. **추가** 단추를 선택한 후 **확인** 단추를 선택합니다.  
  
     이제 동작 문이 **담당자를 현재 항목으로 설정:CreatedBy**로 표시됩니다.  
  
## 다시 사용할 수 있는 워크플로 저장 및 배포  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 .wsp 파일만 가져올 수 있기 때문에 다시 사용할 수 있는 워크플로를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]로 가져오기 전에 .wsp 파일로 저장하고 SharePoint에 배포해야 합니다.  
  
> [!IMPORTANT]  
>  다음 절차를 수행하는 동안 런타임 오류가 표시되는 경우 SharePoint 사이트에 액세스할 수 있는 시스템에서 절차를 수행해야 합니다.  
  
#### 다시 사용할 수 있는 워크플로를 저장 및 배포하려면  
  
1.  SharePoint Designer의 맨 위에 있는 **저장** 단추를 선택하여 진행 상황을 저장하고 **게시** 단추를 선택하여 **SPD1** SharePoint 사이트에 워크플로를 배포합니다.  
  
2.  탐색 창에서 **워크플로** 개체를 선택합니다.  
  
3.  **재 사용 가능한 워크플로** 에서 **SPD 작업 워크플로** 를 선택합니다.  
  
4.  리본 메뉴에서 **템플릿으로 저장** 버튼을 선택하여 워크플로를 .wsp 파일로 저장합니다.  
  
5.  브라우저에서 **SPD1** SharePoint 사이트를 열고 SharePoint에서 .wsp 파일을 확인합니다.  
  
6.  빠른 실행 표시줄에서 **라이브러리** 링크를 선택합니다.  
  
7.  **문서 라이브러리** 섹션에서 **사이트 자산** 링크를 선택합니다.  
  
     **SPD 작업 워크플로** 파일이 다른 사이트 자산과 함께 나열됩니다.  
  
8.  파일 목록에서 해당 파일의 이름을 선택합니다  
  
9. **파일 다운로드** 대화 상자에서 **저장** 버튼을 선택하여 .wsp 파일을 로컬 시스템에 저장합니다.  
  
## .wsp 파일을 Visual Studio로 가져오기  
 다시 사용할 수 있는 워크플로 가져오기 프로젝트를 사용하여 .wsp 파일을 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]로 가져옵니다.  이 프로젝트에서는 워크플로를 다시 사용할 수 있는 선언적 워크플로에서 코드 워크플로로 변환합니다.  워크플로가 변환된 후 코드를 사용하여 동작을 수정합니다.  
  
#### .wsp 파일에서 워크플로를 가져오고 수정하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 의 메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트** 를 차례로 선택합니다.  
  
2.  **새 프로젝트** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
3.  **템플릿** 창에서 **다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기** 템플릿을 선택하고 프로젝트의 이름을 **WorkflowImportProject1** 로 입력한 다음, **확인** 버튼을 선택합니다.  
  
     SharePoint 사용자 지정 마법사가 나타납니다.  
  
4.  **디버깅에 사용할 사이트 및 보안 수준 지정** 페이지에서 이전에 만든 두 번째 SharePoint 하위 사이트인 http:\/\/*system name*\/SPD2 로 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] 을 입력합니다.  
  
5.  **이 SharePoint 솔루션의 신뢰 수준을 선택하십시오.** 섹션에서 **팜 솔루션으로 배포** 옵션 버튼을 선택한 다음, **다음** 버튼을 선택합니다.  
  
     샌드박스가 적용된 솔루션과 팜 솔루션 비교에 대한 자세한 내용은 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)을 참조하십시오.  
  
6.  **새 프로젝트 소스 지정** 페이지에서, 이전에 .wsp 파일을 저장한 시스템 위치로 이동하고 파일을 연 후 **다음** 을 클릭합니다.  
  
    > [!NOTE]  
    >  **완료** 버튼을 선택하여 .wsp 파일의 사용할 수 있는 모든 항목을 가져옵니다.  
  
     이렇게 하면 다시 사용 가능한 워크플로 중 가져올 수 있는 워크플로의 목록이 표시됩니다.  
  
7.  **가져올 항목 선택** 상자에서 **SPD Task Workflow** 워크플로를 선택한 다음 **마침** 버튼을 선택합니다.  
  
     가져오기 작업이 완료되면 **SPD\_Workflow\_TestFT**라는 워크플로가 포함된 **WorkflowImportProject1** 프로젝트가 만들어집니다.  이 폴더에는 워크플로의 정의 파일인 Elements.xml과 워크플로 디자이너 파일\(.xoml\)이 들어 있습니다.  디자이너에는 규칙 파일\(.rules\)과 코드 숨김 파일\(프로젝트의 프로그래밍 언어에 따라 .cs 또는 .vb\)의 두 개 파일이 있습니다.  
  
8.  **솔루션 탐색기** 에서 **기타 가져올 파일** 폴더를 삭제합니다.  
  
9. Elements.xml 파일에서 `InstantiationURL="_layouts/IniErkflIP.sspx"` 을 삭제합니다.  
  
10. **솔루션 탐색기** 에서 **WorkflowImportProject1** 를 선택한 다음, 메뉴 표시줄에서 **프로젝트**, **시작 프로젝트로 설정** 을 선택하여 **WorkflowImportProject1** 을 시작 항목으로 설정합니다.  
  
     이렇게 하면 프로젝트를 디버깅하는 즉시 목록이 표시됩니다.  
  
11. **다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기** 템플릿은 가져온 워크플로에 대한 연결 속성 값을 가져올 수 없으므로, 이 값은 직접 입력되어야 합니다.  이를 위해 다음을 수행합니다.  
  
    1.  **솔루션 탐색기**에서 **SPD 워크플로 TestFT** 노드를 선택합니다.  
  
    2.  **대상 목록** 속성과 같은 목록 속성 옆에 있는 줄임표 \(![ASP.NET 모바일 디자이너 줄임표](~/sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")\) 버튼을 선택합니다.  
  
    3.  SharePoint 사용자 지정 마법사에서 누락 된 값을 입력 한 다음, **완료** 버튼을 선택합니다.  
  
12. .xoml 파일을 선택한 다음, 메뉴 표시줄에서 **보기**, **디자이너** 를 선택하여 워크플로 디자이너의 가져온 워크플로를 볼 수 있습니다.  
  
13. **도구상자** 의 **Windows Workflow v3.0** 노드에서 다음 단계 중 하나를 수행합니다:  
  
    -   **Code** 작업에 대한 바로 가기 메뉴를 열고 **복사**를 선택합니다.  워크플로 디자이너에서 **SequenceActivity1** 작업의 아래 줄에 대한 바로 가기 메뉴의 연 다음 **붙여넣기** 를 선택합니다.  
  
    -   **코드** 작업을 **도구 상자** 에서 워크플로 디자이너로 끌어오고 **SequenceActivity1** 작업 아래의 줄에 연결합니다.  
  
     **CodeActivity1**이라는 작업이 Workflow Designer에 추가됩니다.  이 작업에서는 사용자가 워크플로를 시작할 때 알림 목록에 알림을 만드는 코드 동작을 추가합니다.  
  
14. 다음 단계 중 하나를 수행합니다.  
  
    -   **CodeActivity1**을 두 번 클릭하여 이벤트 처리기를 생성하고 코드를 봅니다.  
  
    -   **CodeActivity1** 의 **속성** 창에서 **ExecuteCode** 속성의 값을 **codeActivity\_ExecuteCode** 로 설정합니다.  
  
15. 다음 내용을 기존의 **using** 또는 **Imports** 문 아래 추가합니다.  
  
     [!code-csharp[SP_SPDWFImport#1](../snippets/csharp/VS_Snippets_OfficeSP/sp_spdwfimport/cs/workflows/spd_task_workflowft/spd task workflow.xoml.cs#1)]
     [!code-vb[SP_SPDWFImport#1](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_spdwfimport/vb/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.vb#1)]  
  
16. `codeActivity1_ExecuteCode`를 다음 코드로 바꿉니다.  
  
     [!code-csharp[SP_SPDWFImport#2](../snippets/csharp/VS_Snippets_OfficeSP/sp_spdwfimport/cs/workflows/spd_task_workflowft/spd task workflow.xoml.cs#2)]
     [!code-vb[SP_SPDWFImport#2](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_spdwfimport/vb/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.vb#2)]  
  
## 프로젝트 배포 및 워크플로 연결  
 다음으로, WorkflowImportProject1을 실행하여 SharePoint 사이트에 배포하고 워크플로를 작업 목록과 연결하여 수정 및 변환된 워크플로를 보고 테스트합니다.  
  
#### 프로젝트를 배포하고 워크플로를 연결하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 F5 키를 눌러 변환된 워크플로 프로젝트를 실행하고 배포합니다.  
  
2.  빠른 실행 모음에서 **작업** 링크를 선택하여 작업 목록을 표시합니다.  
  
3.  **목록 도구** 탭에서 **항목** 버튼을 선택한 다음 **새 항목** 버튼을 선택합니다.  
  
     **작업 \- 새 항목** 대화 상자가 열립니다.  
  
4.  **제목** 상자에 새 작업을 입력한 후 **저장** 버튼을 선택합니다.  
  
5.  **목록 도구** 탭에서 **목록** 버튼을 선택한 다음 **목록 설정** 버튼을 선택합니다.  
  
     **목록 설정** 페이지가 나타납니다.  
  
6.  **사용 권한 및 관리** 섹션에서 **워크플로 설정** 링크를 선택합니다.  
  
     **워크플로 설정** 페이지가 나타납니다.  
  
7.  **워크플로 추가** 링크를 선택합니다.  
  
8.  **워크플로** 목록에서 **WorkflowImportProject1 \- SPD Workflow Test**를 선택합니다.  
  
9. **이름** 상자에 SPD 워크플로 테스트 를 입력한 후 **확인** 버튼을 선택합니다.  
  
10. 빠른 실행 표시줄에서 **작업** 목록을 선택합니다.  
  
11. **새 작업** 옆에 있는 화살표를 선택한 다음, 목록에서 **워크플로** 를 선택합니다.  
  
12. **새 워크플로 시작** 섹션에서, **SPD 워크플로 테스트** 의 링크를 선택한 다음, **시작** 버튼을 선택하여 워크플로를 시작합니다.  
  
    > [!NOTE]  
    >  또는 워크플로 설정 마법사를 실행하고 워크플로를 자동 연결로 설정하여 워크플로를 목록과 자동으로 연결할 수 있습니다.  
  
     워크플로에서 두 가지 동작이 수행됩니다. 작업의 **담당자** 열에 사용자 이름이 표시되고 **알림** 목록에 알림이 표시됩니다.  
  
## 참고 항목  
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)   
 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  