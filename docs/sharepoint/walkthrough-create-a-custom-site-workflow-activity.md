---
title: "연습: 사용자 지정 사이트 워크플로 작업 만들기 | Microsoft Docs"
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
- custom workflow activities [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, custom workflow activities
- site workflows [SharePoint development in Visual Studio]
- workflow activities [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, site workflows
ms.assetid: 8219a779-c27b-4186-92c9-5bda03328aa9
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1b7a24c793755cdd5102407d1a3a5cbfad103c92
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-create-a-custom-site-workflow-activity"></a>연습: 사용자 지정 사이트 워크플로 작업 만들기
  이 연습에서는를 사용 하 여 사이트 수준 워크플로 대 한 사용자 지정 활동을 만드는 방법을 보여 줍니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. (사이트 수준 워크플로 사이트에서 목록 뿐 아니라 전체 사이트에 적용 합니다.) 사용자 지정 활동 백업 알림 목록을 만들고 공지 목록의 내용을 그 안에 복사 합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   사이트 수준 워크플로 만드는 중입니다.  
  
-   사용자 지정 워크플로 활동을 만드는 중입니다.  
  
-   만들고 SharePoint 목록을 삭제 합니다.  
  
-   다른 하나의 목록에서 항목을 복사 합니다.  
  
-   빠른 실행 모음에서 목록을 표시 합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원 되는 버전 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 합니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio.  
  
## <a name="creating-a-site-workflow-custom-activity-project"></a>사이트 워크플로 사용자 지정 활동 프로젝트 만들기  
 먼저 프로젝트를 포함 하 고 테스트할 사용자 지정 워크플로 활동을 만듭니다.  
  
#### <a name="to-create-a-site-workflow-custom-activity-project"></a>사이트 워크플로 사용자 지정 활동 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로**, **프로젝트** 표시 하는 **새 프로젝트** 대화 상자.  
  
2.  확장 하 고는 **SharePoint** 노드 아래의 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **2010** 노드.  
  
3.  에 **템플릿** 창, 선택는 **SharePoint 2010 프로젝트** 서식 파일입니다.  
  
4.  에 **이름** 상자에 입력 **AnnouncementBackup**, 선택한 후는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
5.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지를 선택 합니다는 **팜 솔루션으로 배포** 옵션 단추를 선택한 후는 **마침** 적용할 단추는 신뢰 수준 및 기본 사이트입니다.  
  
     이 단계는 팜 솔루션으로 워크플로 프로젝트에 대 한 옵션만 사용할 수 솔루션에 대 한 신뢰 수준을 설정합니다.  
  
6.  **솔루션 탐색기**, 프로젝트 노드를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **새 항목 추가**합니다.  
  
7.  아래의 **Visual C#** 또는 **Visual Basic**를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
8.  에 **템플릿** 창 선택는 **순차 워크플로 (팜 솔루션에만 해당)** 서식 파일을 선택한 후는 **추가** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
9. 에 **디버깅에 대 한 워크플로 이름을 지정** 페이지에서 기본 이름을 (AnnouncementBackup-Workflow1). 워크플로 템플릿 형식을 변경 하 **사이트 워크플로**를 선택한 후는 **다음** 단추입니다.  
  
10. 선택 된 **마침** 단추 나머지 기본 설정을 그대로 적용 합니다.  
  
## <a name="adding-a-custom-workflow-activity-class"></a>사용자 지정 워크플로 활동 클래스 추가  
 다음으로, 사용자 지정 워크플로 활동에 대 한 코드를 포함 하도록 프로젝트에 클래스를 추가 합니다.  
  
#### <a name="to-add-a-custom-workflow-activity-class"></a>사용자 지정 워크플로 활동 클래스를 추가 하려면  
  
1.  메뉴 모음에서 **프로젝트**, **새 항목 추가** 표시 하는 **새 항목 추가** 대화 상자.  
  
2.  에 **설치 된 템플릿** 트리 보기를 선택는 **코드** 노드를 선택한 후는 **클래스** 프로젝트 항목 템플릿 목록에서 서식 파일입니다. Class1 기본 이름을 사용 합니다. **추가** 단추를 선택합니다.  
  
3.  다음으로 모든 Class1의 코드를 대체 합니다.  
  
     [!code-csharp[SP_AnnBackup#1](../sharepoint/codesnippet/CSharp/announcementbackup/class1.cs#1)]
     [!code-vb[SP_AnnBackup#1](../sharepoint/codesnippet/VisualBasic/announcementbackupvb/class1.vb#1)]  
  
4.  프로젝트를 저장 한 다음 메뉴 모음에서 선택 **빌드**, **솔루션 빌드**합니다.  
  
     사용자 지정 작업으로 Class1 표시는 **도구 상자** 에 **AnnouncementBackup 구성 요소** 탭 합니다.  
  
## <a name="adding-the-custom-activity-to-the-site-workflow"></a>사이트 워크플로를 사용자 지정 활동을 추가합니다.  
 그런 다음 워크플로 사용자 지정 코드를 포함 하는 활동을 추가 합니다.  
  
#### <a name="to-add-a-custom-activity-to-the-site-workflow"></a>워크플로 사이트에 사용자 지정 활동을 추가 하려면  
  
1.  워크플로 디자이너의 디자인 뷰에 Workflow1를 엽니다.  
  
2.  Class1 끌어는 **도구 상자** 아래에 나타나는 `onWorkflowActivated1` 활동 또는 Class1에 대 한 바로 가기 메뉴 열기 선택 **복사**, 아래의 줄에 대 한 바로 가기 메뉴를 열고는 `onWorkflowActivated1` 활동을 선택한 후 **붙여넣기**합니다.  
  
3.  프로젝트를 저장합니다.  
  
## <a name="testing-the-site-workflow-custom-activity"></a>사이트 워크플로 사용자 지정 작업 테스트  
 다음으로 프로젝트를 실행 하 고 사이트 워크플로 시작 합니다. 사용자 지정 활동 백업 알림 목록을 만들고 그 안에 현재 공지 사항 목록에서 내용을 복사 합니다. 또한 코드는 백업 목록 만들기 전에 이미 있는지 여부를 확인 합니다. 백업 목록에 이미 있으면 삭제 됩니다. 코드는 또한 SharePoint 사이트의 빠른 실행 모음에서 새 목록에 대 한 링크를 추가합니다.  
  
#### <a name="to-test-the-site-workflow-custom-activity"></a>사이트 워크플로 사용자 지정 작업을 테스트 하려면  
  
1.  프로젝트를 실행 하 고 SharePoint에 배포 F5 키를 선택 합니다.  
  
2.  빠른 실행 모음에서 선택 된 **나열** 모든 SharePoint 사이트에서 사용할 수 있는 목록을 표시 하려면 링크 합니다. 하나의 목록에 대 한 알림 라는 것을 볼 수 **공지**합니다.  
  
3.  SharePoint 웹 페이지 맨 위에 있는 선택 된 **사이트 워크플로** 링크 합니다.  
  
4.  새 워크플로 섹션 시작에서 선택 된 **AnnouncementBackup-Workflow1** 링크 합니다. 사이트 워크플로 시작 하 고 사용자 지정 작업에서 코드를 실행 합니다.  
  
5.  빠른 실행 모음에서 선택 된 **알림 백업** 링크 합니다. 모든 알림이 포함 되어 있는 **공지** 새 목록에 복사 된 목록입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 이벤트 수신기 만들기](../sharepoint/how-to-create-an-event-receiver.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  