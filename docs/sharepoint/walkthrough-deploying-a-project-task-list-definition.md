---
title: "연습: 프로젝트 작업 목록 정의 배포 | Microsoft Docs"
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
helpviewer_keywords: SharePoint development in Visual Studio, deploying
ms.assetid: 18b62016-ed30-4dd1-9dfc-0d7e82c6767f
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 16cccaf9a8639ef2d7213140121b087cd15e72d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-deploying-a-project-task-list-definition"></a>연습: 프로젝트 작업 목록 정의 배포
  이 연습에서는 프로젝트 작업을 추적하기 위해 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)]를 사용하여 SharePoint 목록을 만들고, 사용자 지정하고, 디버깅하고, 배포하는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [SharePoint 목록 만들기](#CreatingListDef)합니다.  
  
-   [SharePoint 목록 만들기](#CreatingListDef)합니다.  
  
-   [이벤트 수신기 추가](#AddEventRcvr)합니다.  
  
-   [프로젝트 작업 목록 기능을 사용자 지정](#CustomizeFeature)합니다.  
  
-   [빌드 및 테스트 프로젝트 작업 목록](#BuildTest)합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   [!INCLUDE[vs_pro_current_short](../sharepoint/includes/vs-pro-current-short-md.md)]또는 버전의 Visual Studio ALM 응용 프로그램 수명 주기 관리 ()을 지정 합니다.  
  
##  <a name="CreatingListDef"></a>SharePoint 목록 만들기  
 SharePoint 목록 프로젝트를 만들고 목록 정의를 작업과 연결합니다.  
  
#### <a name="to-create-a-sharepoint-list-project"></a>SharePoint 목록 프로젝트를 만들려면  
  
1.  열기는 **새 프로젝트** 대화 상자에서 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
2.  에 **템플릿** 창 선택는 **SharePoint 2010 프로젝트** 서식 파일을 프로젝트 이름 **ProjectTaskList**, 선택한 후는 **확인**단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
3.  디버깅을 위해 사용 하는 로컬 SharePoint 사이트 지정 선택는 **팜 솔루션으로 배포** 옵션 단추를 선택한 후는 **마침** 단추입니다.  
  
4.  프로젝트에 대 한 바로 가기 메뉴를 연 다음 선택 **추가**, **새 항목**합니다.  
  
5.  에 **템플릿** 창 선택는 **목록** 서식 파일을 선택한 후는 **추가** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
6.  에 **어떤 이름을 목록에 표시 하 시겠습니까?** 상자에 입력 **프로젝트 작업 목록**합니다.  
  
7.  선택는 **의 기존 목록 형식을 기반으로 사용자 지정할 목록을 만들** 옵션 단추를 선택한 다음 해당 목록에 선택 **작업**, 선택한 후는 **마침** 단추입니다.  
  
     목록, 기능 및 패키지에 표시 **솔루션 탐색기**합니다.  
  
##  <a name="AddEventRcvr"></a>이벤트 수신기 추가  
 작업 목록에서 작업의 기한과 설명을 자동으로 설정하는 이벤트 수신기를 추가할 수 있습니다. 다음 절차를 이벤트 수신자로 목록 인스턴스를 간단한 이벤트 처리기를 추가합니다.  
  
#### <a name="to-add-an-event-receiver"></a>이벤트 수신기를 추가 하려면  
  
1.  프로젝트 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 항목**합니다.  
  
2.  SharePoint 템플릿의 목록에서 선택 된 **이벤트 수신기** 서식 파일을 다음 이름을 **ProjectTaskListEventReceiver**합니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
3.  에 **이벤트 수신기 설정 선택** 페이지에서 선택 **목록 항목 이벤트** 에서 이벤트 수신기 유형으로는 **이벤트 수신기 유형을 사용할** 목록입니다.  
  
4.  에 **이벤트 소스를 사용할 항목을** 목록에서 선택 **작업**합니다.  
  
5.  처리할 이벤트 목록에서 확인란을 옆에 선택 **항목이 추가 되었습니다**를 선택한 후는 **마침** 단추입니다.  
  
     새 이벤트 수신기 노드 라는 코드 파일을 프로젝트에 추가 됩니다 **ProjectTaskListEventReceiver**합니다.  
  
6.  코드를 추가 하는 `ItemAdded` 에서 메서드는 **ProjectTaskListEventReceiver** 코드 파일. 새 작업을 추가할 때마다 기한 및 설명은 기본 작업에 추가 됩니다. 기본 기한은 날짜가 2009 년 7 월 1 일입니다.  
  
     [!code-vb[SPProjectTaskList#1](../sharepoint/codesnippet/VisualBasic/projecttasklist1/projecttasklisteventreceiver/projecttasklisteventreceiver.vb#1)]
     [!code-csharp[SPProjectTaskList#1](../sharepoint/codesnippet/CSharp/projecttasklist/projecttasklisteventreceiver/projecttasklisteventreceiver.cs#1)]  
  
##  <a name="CustomizeFeature"></a>프로젝트 작업 목록 기능을 사용자 지정  
 SharePoint 솔루션을 만들 때 Visual Studio 자동으로 기능을 만듭니다 기본값에 대 한 프로젝트 항목입니다. 기능 디자이너를 사용 하 여 SharePoint 사이트에 대 한 프로젝트 작업 목록 설정을 사용자 지정할 수 있습니다.  
  
#### <a name="to-customize-the-project-task-list-feature"></a>프로젝트 작업 목록 기능을 사용자 지정 하려면  
  
1.  **솔루션 탐색기**를 확장 하 고 **기능**합니다.  
  
2.  에 대 한 바로 가기 메뉴를 열고 **Feature1**를 선택한 후 **뷰 디자이너**합니다.  
  
3.  에 **제목** 상자에 입력 **프로젝트 작업 목록 기능**합니다.  
  
4.  에 **범위** 목록에서 선택 **웹**합니다.  
  
5.  에 **속성** 창 입력 **1.0.0.0** 에 대 한 값으로는 **버전** 속성입니다.  
  
##  <a name="CustomizePackage"></a>프로젝트 작업 목록 패키지를 사용자 지정  
 SharePoint 프로젝트를 만들 때 Visual Studio 패키지에 기본 프로젝트 항목을 포함 하는 기능을 자동으로 추가 합니다. 패키지 디자이너를 사용 하 여 SharePoint 사이트에 대 한 프로젝트 작업 목록 설정을 사용자 지정할 수 있습니다.  
  
#### <a name="to-customize-the-project-task-list-package"></a>프로젝트 작업 목록 패키지를 사용자 지정 하려면  
  
1.  **솔루션 탐색기**, 바로 가기 메뉴를 열고 **패키지**를 선택한 후 **뷰 디자이너**합니다.  
  
2.  에 **이름** 상자에 입력 **ProjectTaskListPackage**합니다.  
  
3.  선택 된 **웹 서버를 다시 설정** 확인란 합니다.  
  
##  <a name="BuildTest"></a>빌드 및 테스트 프로젝트 작업 목록  
 프로젝트를 실행 하는 경우 SharePoint 사이트가 열립니다. 그러나 작업 목록의 위치로 이동 수동으로 해야 합니다.  
  
#### <a name="to-test-the-project-task-list"></a>프로젝트 작업 목록 테스트 하려면  
  
1.  F5 키를 선택하여 프로젝트 작업 목록을 빌드하고 배포합니다.  
  
     SharePoint 사이트가 열립니다.  
  
2.  선택 된 **홈** 탭 합니다.  
  
3.  왼쪽된 세로 막대에서 선택 된 **프로젝트 작업 목록** 링크 합니다.  
  
     프로젝트 작업 목록 페이지가 나타납니다.  
  
4.  에 **목록 도구** 탭에서 선택 된 **항목** 탭 합니다.  
  
5.  에 **항목** 그룹에서 선택 된 **새 항목** 단추입니다.  
  
6.  에 **제목** 텍스트 상자에 입력 **Task1**합니다.  
  
7.  선택 된 **저장** 단추입니다.  
  
     사이트를 새로 고친 후의 **Task1** 7/1/2009의 기한 작업이 나타납니다.  
  
8.  선택 **Task1**합니다.  
  
     작업의 자세히 보기에 나타나고 "중요 한 작업입니다." 설명을 표시합니다  
  
##  <a name="Deploy"></a>배포 프로젝트 작업 목록  
 빌드하고 프로젝트 작업 목록을 테스트 한 후에 배포할 수 있습니다는 *로컬 시스템* 또는 *원격 시스템*합니다. 로컬 시스템에는 동일한 컴퓨터에 솔루션을 개발한는 원격 시스템의 다른 컴퓨터 반면 합니다.  
  
#### <a name="to-deploy-the-project-task-list-to-the-local-system"></a>로컬 시스템에 프로젝트 작업 목록을 배포 하려면  
  
1.  Visual Studio 메뉴 모음에서 **빌드**, **솔루션 배포**합니다.  
  
     IIS 응용 프로그램 풀을 재생 하는 솔루션의 기존 버전을 제거 SharePoint 솔루션 패키지 (.wsp) 파일을 복사 및 다음 해당 기능을 활성화 하는 visual Studio 합니다. 이제 SharePoint에서 솔루션을 사용할 수 있습니다. 배포 구성 단계에 대 한 자세한 내용은 참조 [하는 방법: SharePoint 배포 구성 편집](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md)합니다.  
  
#### <a name="to-deploy-the-project-task-list-to-a-remote-system"></a>원격 시스템에 프로젝트 작업 목록을 배포 하려면  
  
1.  Visual Studio 메뉴 모음에서 **빌드**, **게시**합니다.  
  
2.  에 **게시** 대화 상자에서 선택 하는 **파일 시스템에 게시** 옵션 단추입니다.  
  
     위치에서 대상 위치를 변경할 수 있습니다는 **게시** 대화 상자에서 줄임표 단추를 선택 하 여 ![줄임표 아이콘](../sharepoint/media/ellipsisicon.gif "줄임표 아이콘") 후 다른 위치로 이동 합니다.  
  
3.  선택 된 **게시** 단추입니다.  
  
     .wsp 파일이 솔루션에 대해 만들어집니다.  
  
4.  원격 SharePoint 시스템에.wsp 파일을 복사 합니다.  
  
5.  PowerShell을 사용 하 여 `Add-SPUserSolution` 원격 SharePoint 설치에서 패키지를 설치 하는 명령입니다. (사용 하 여 팜 솔루션에 대 한는 `Add-SPSolution` 명령입니다.)  
  
     예를 들어, `Add-SPUserSolution C:\MyProjects\ProjectTaskList\ProjectTaskList\bin\Debug\ProjectTaskList.wsp`을 입력합니다.  
  
6.  PowerShell을 사용 하 여 `Install-SPUserSolution` 솔루션을 배포 하는 명령입니다. (사용 하 여 팜 솔루션에 대 한는 `Install-SPSolution` 명령입니다.)  
  
     예를 들어, `Install-SPUserSolution -Identity ProjectTaskList.wsp -Site http://NewSiteName`을 입력합니다.  
  
     원격 배포에 대 한 자세한 내용은 참조 [를 사용 하 여 솔루션](http://go.microsoft.com/fwlink/?LinkId=217680) 및 [추가 및 SharePoint 2010에서 PowerShell 사용한 솔루션 배포](http://go.microsoft.com/fwlink/?LinkId=217682)합니다.  
  
## <a name="next-steps"></a>다음 단계  
 사용자 지정 및 다음 항목에서 SharePoint 솔루션을 배포 하는 방법에 대 한 자세히 알아볼 수 있습니다.  
  
-   [연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)  
  
-   [방법: 이벤트 수신기 만들기](../sharepoint/how-to-create-an-event-receiver.md)  
  
-   [SharePoint Server 2010 용 Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=217684)  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  