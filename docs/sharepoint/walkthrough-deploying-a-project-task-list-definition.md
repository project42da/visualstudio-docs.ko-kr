---
title: "연습: 프로젝트 작업 목록 정의 배포"
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
  - "Visual Studio에서 SharePoint 개발, 배포"
ms.assetid: 18b62016-ed30-4dd1-9dfc-0d7e82c6767f
caps.latest.revision: 34
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 33
---
# 연습: 프로젝트 작업 목록 정의 배포
  이 연습에서는 프로젝트 작업을 추적하기 위해 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)]을 사용하여 SharePoint 목록을 만들고 사용자 지정, 디버깅 및 배포하는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [SharePoint 목록 만들기](#CreatingListDef)  
  
-   [SharePoint 목록 만들기](#CreatingListDef)  
  
-   [이벤트 수신자 추가](#AddEventRcvr)  
  
-   [프로젝트 작업 목록 기능 사용자 지정](#CustomizeFeature)  
  
-   [프로젝트 작업 목록 빌드 및 테스트](#BuildTest)  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   [!INCLUDE[vs_pro_current_short](../sharepoint/includes/vs-pro-current-short-md.md)] 또는 Visual Studio ALM\(Application Lifecycle Management\)의 버전  
  
##  <a name="CreatingListDef"></a> SharePoint 목록 만들기  
 SharePoint 목록 프로젝트를 만들고 목록 정의와 작업을 연결합니다.  
  
#### SharePoint 목록 프로젝트를 만들려면  
  
1.  **새 프로젝트** 대화 상자를 열고 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
2.  **템플릿** 창에서 **SharePoint 2010 프로젝트** 템플릿을 선택하고, 프로젝트 이름을 ProjectTaskList로 변경한 다음, **확인** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
3.  디버깅을 위해 사용하는 로컬 SharePoint 사이트를 지정하고, **팜 솔루션으로 배포** 옵션 버튼을 선택한 다음, **완료** 버튼을 선택합니다.  
  
4.  이 프로젝트에 대한 바로 가기 메뉴를 연 다음, **추가**, **새 항목** 을 선택합니다.  
  
5.  **템플릿** 창에서 **항목** 템플릿을 선택한 다음 **추가** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
6.  **이름을 목록에 표시 하시겠습니까?** 상자에서, 프로젝트 작업 목록을 입력 합니다.  
  
7.  **기존 목록 형식에 따라 사용자 지정할 수 없는 목록 만들기** 옵션 버튼을 선택한 다음, 해당 목록에서 **작업**을 선택한 다음, **완료** 버튼을 선택합니다.  
  
     목록, 기능 및 패키지가 **솔루션 탐색기** 에 표시됩니다.  
  
##  <a name="AddEventRcvr"></a> 이벤트 수신자 추가  
 작업 목록에서 작업의 기한과 설명을 자동으로 설정하는 이벤트 수신자를 추가할 수 있습니다.  다음 절차에서는 목록 인스턴스에 간단한 이벤트 처리기를 이벤트 수신자로 추가합니다.  
  
#### 이벤트 수신자를 추가하려면  
  
1.  프로젝트 노드에 대한 바로 가기 메뉴를 열고 **추가**를 선택한 다음 **새 항목**을 선택합니다.  
  
2.  SharePoint 2010 템플릿 목록에서 **이벤트 수신자** 템플릿을 선택한 다음, 이름을 **ProjectTaskListEventReceiver**로 지정합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
3.  **이벤트 수신자 설정 선택** 페이지에서, **이벤트 수신자 유형을 선택 하십시오** 목록에서의 이벤트 수신자 형식으로 **목록 항목 이벤트** 을 선택합니다.  
  
4.  **이벤트 소스에 대한 항목을 지정하십시오** 목록에서 **작업** 을 선택합니다.  
  
5.  처리할 이벤트 목록에서 **항목 추가됨** 옆에 있는 확인 상자를 선택한 다음 **마침**을 선택합니다.  
  
     새 이벤트 수신자 노드가 **ProjectTaskListEventReceiver**라는 코드 파일과 함께 프로젝트에 추가됩니다.  
  
6.  **ProjectTaskListEventReceiver** 코드 파일의 `ItemAdded` 메서드에 코드를 추가합니다.  새 작업을 추가할 때마다 기본 기한과 설명이 작업에 추가됩니다.  기본 기한은 2009년 7월 1일입니다.  
  
     [!code-csharp[SPProjectTaskList#1](../snippets/csharp/VS_Snippets_OfficeSP/spprojecttasklist/cs/projecttasklisteventreceiver/projecttasklisteventreceiver.cs#1)]
     [!code-vb[SPProjectTaskList#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spprojecttasklist/vb/projecttasklisteventreceiver/projecttasklisteventreceiver.vb#1)]  
  
##  <a name="CustomizeFeature"></a> 프로젝트 작업 목록 기능 사용자 지정  
 SharePoint 솔루션을 만들면 기본 프로젝트 항목에 대한 기능이 자동으로 만들어집니다.  기능 디자이너를 사용하여 SharePoint 사이트에 대해 프로젝트 작업 목록 설정을 사용자 지정할 수 있습니다.  
  
#### 프로젝트 작업 목록 기능을 사용자 지정하려면  
  
1.  **솔루션 탐색기**에서 **기능**을 확장합니다.  
  
2.  **Feature1**의 바로 가기 메뉴를 열고 **디자이너 보기**를 선택합니다.  
  
3.  **제목** 상자에서 **프로젝트 작업 목록 기능**을 입력합니다.  
  
4.  **범위** 목록에서 **웹**을 선택합니다.  
  
5.  **속성** 창에서 **버전** 속성 값으로 **1.0.0.0** 을 입력합니다.  
  
##  <a name="CustomizePackage"></a> 프로젝트 작업 목록 패키지 사용자 지정  
 SharePoint 프로젝트를 만들면 기본 프로젝트 항목이 포함된 기능이 패키지에 자동으로 추가됩니다.  패키지 디자이너를 사용하여 SharePoint 사이트에 대해 프로젝트 작업 목록 설정을 사용자 지정할 수 있습니다.  
  
#### 프로젝트 작업 목록 패키지를 사용자 지정하려면  
  
1.  **솔루션탐색기** 에서, **패키지** 의 바로 가기 메뉴를 연 다음, **디자이너 보기** 를 선택합니다.  
  
2.  **이름** 상자에 **ProjectTaskListPackage**를 입력합니다.  
  
3.  **웹 서버 재설정** 확인란을 선택합니다.  
  
##  <a name="BuildTest"></a> 프로젝트 작업 목록 빌드 및 테스트  
 프로젝트를 실행하면 SharePoint 사이트가 열립니다.  하지만 작업 목록 위치를 수동으로 탐색해야 합니다.  
  
#### 프로젝트 작업 목록을 테스트하려면  
  
1.  F5 키를 눌러 프로젝트 작업 목록을 빌드하고 배포합니다.  
  
     SharePoint 사이트가 열립니다.  
  
2.  **홈** 탭을 선택합니다.  
  
3.  왼쪽 사이드 바에서 **프로젝트 작업 목록** 링크를 선택합니다.  
  
     프로젝트 작업 목록 페이지가 나타납니다.  
  
4.  **목록 도구** 탭에서 **항목** 탭을 선택합니다.  
  
5.  **항목** 그룹에서 **새 항목** 버튼을 선택합니다.  
  
6.  **제목** 텍스트 상자에 Task1을 입력합니다.  
  
7.  **저장** 단추를 선택합니다.  
  
     사이트를 새로 고치면 기한이 2009\/7\/1인 **Task1** 작업이 나타납니다.  
  
8.  **Task1**을 선택합니다.  
  
     작업의 상세 뷰가 나타나고 "This is a critical task."이라는 설명이 표시됩니다.  
  
##  <a name="Deploy"></a> 프로젝트 작업 목록 배포  
 프로젝트 작업 목록을 빌드 및 테스트한 후 *로컬 시스템* 또는 *원격 시스템*에 배포할 수 있습니다.  로컬 시스템은 솔루션을 개발한 컴퓨터와 동일한 컴퓨터인 반면 원격 시스템은 이와 다른 컴퓨터입니다.  
  
#### 프로젝트 작업 목록을 로컬 시스템에 배포하려면  
  
1.  Visual Studio 메뉴 모음에서 **빌드**, **솔루션 배포** 를 선택합니다.  
  
     Visual Studio에서는 IIS 응용 프로그램 풀을 재생하고, 기존 버전의 솔루션을 제거하고, 솔루션 패키지 파일\(.wsp\)을 SharePoint에 복사한 다음, 기능을 활성화합니다.  이제 SharePoint에서 솔루션을 사용할 수 있습니다.  배포 구성 단계에 대한 자세한 내용은 [방법: SharePoint 배포 구성 편집](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md)을 참조하십시오.  
  
#### 프로젝트 작업 목록을 원격 시스템에 배포하려면  
  
1.  Visual Studio 메뉴 모음에서 **빌드**, **게시** 를 선택합니다.  
  
2.  **게시** 대화 상자에서 **파일 시스템에 게시** 옵션 버튼을 선택합니다.  
  
     줄임표 버튼 ![가변 매개 변수 아이콘](~/docs/sharepoint/media/ellipsisicon.gif "가변 매개 변수 아이콘") 을 선택하고 다른 위치로 탐색하여 **게시** 대화 상자의 대상 위치를 변경할 수 있습니다.  
  
3.  **게시** 버튼을 선택합니다.  
  
     .Wsp 파일은 솔루션에 대해 만들어집니다.  
  
4.  .wsp 파일을 원격 SharePoint 시스템에 복사합니다.  
  
5.  PowerShell `Add-SPUserSolution` 명령을 사용하여 원격 SharePoint 설치에 패키지를 설치합니다. 팜 솔루션의 경우에는 `Add-SPSolution` 명령을 사용합니다.  
  
     예를 들어 `Add-SPUserSolution C:\MyProjects\ProjectTaskList\ProjectTaskList\bin\Debug\ProjectTaskList.wsp`를 입력합니다.  
  
6.  PowerShell `Install-SPUserSolution` 명령을 사용하여 솔루션을 배포합니다. 팜 솔루션의 경우에는 `Install-SPSolution` 명령을 사용합니다.  
  
     예를 들어 `Install-SPUserSolution –Identity ProjectTaskList.wsp –Site http://NewSiteName`을 입력합니다.  
  
     원격 배포에 대한 자세한 내용은 [솔루션 사용](http://go.microsoft.com/fwlink/?LinkId=217680) 및 [SharePoint 2010에서 PowerShell을 사용하여 솔루션을 배포 및 추가](http://go.microsoft.com/fwlink/?LinkId=217682) 을 참조하십시오.  
  
## 다음 단계  
 다음 항목에서는 SharePoint 솔루션을 사용자 지정하고 배포하는 방법에 대해 더 자세히 설명합니다.  
  
-   [연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)  
  
-   [방법: 이벤트 수신자 만들기](../sharepoint/how-to-create-an-event-receiver.md)  
  
-   [SharePoint Server 2010에 대한 Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=217684)  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  