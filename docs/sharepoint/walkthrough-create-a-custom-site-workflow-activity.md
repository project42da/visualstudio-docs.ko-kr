---
title: "연습: 사용자 지정 사이트 워크플로 작업 만들기"
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
  - "사용자 지정 워크플로 활동[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 사용자 지정 워크플로 활동"
  - "Visual Studio에서 SharePoint 개발, 사이트 워크플로"
  - "사이트 워크플로[Visual Studio에서 SharePoint 개발]"
  - "워크플로 활동[Visual Studio에서 SharePoint 개발]"
ms.assetid: 8219a779-c27b-4186-92c9-5bda03328aa9
caps.latest.revision: 20
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 19
---
# 연습: 사용자 지정 사이트 워크플로 작업 만들기
  이 연습에서는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 사용하여 사이트 수준 워크플로에 대한 사용자 지정 작업을 만드는 방법을 보여 줍니다. 사이트 수준 워크플로는 사이트의 목록뿐 아니라 전체 사이트에 적용됩니다. 사용자 지정 작업은 백업 알림 목록을 만든 다음 알림 목록의 내용을 백업에 복사합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   사이트 수준 워크플로 만들기  
  
-   사용자 지정 워크플로 작업 만들기  
  
-   SharePoint 목록 만들기 및 삭제  
  
-   한 목록에서 다른 목록으로 항목 복사  
  
-   빠른 실행 모음에 목록 표시  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio  
  
## 사이트 워크플로 사용자 지정 작업 프로젝트 만들기  
 먼저 사용자 지정 워크플로 작업을 포함하고 테스트할 프로젝트를 만듭니다.  
  
#### 사이트 워크플로 사용자 지정 작업 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 을 선택합니다.  
  
3.  **템플릿** 창에서 **SharePoint 2010 프로젝트** 템플릿을 선택합니다.  
  
4.  **이름** 상자에 AnnouncementBackup을 입력한 후 **확인** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
5.  **사이트 지정 및 디버깅에 대한 보안 수준** 페이지에서 **팜 솔루션으로 배포** 옵션 버튼을 선택한 다음 **마침** 버튼을 선택하여 신뢰 수준 및 기본 사이트를 수락합니다.  
  
     이 단계에서는 솔루션의 신뢰 수준을 팜 솔루션으로 설정합니다. 이 옵션은 워크플로 프로젝트에 사용할 수 있는 유일한 옵션입니다.  
  
6.  **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음 메뉴 모음에서 **프로젝트**, **화면 추가**를 선택합니다.  
  
7.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
8.  **템플릿** 창에서 **순차 워크플로 \(팜 솔루션에서만\)** 템플릿을 선택한 후 **추가** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
9. **디버깅에 사용할 워크플로 이름 지정** 페이지에서 기본 이름\(AnnouncementBackup \- Workflow1\)을 적용합니다.  워크플로 템플릿 형식을 **사이트 워크플로**로 변경하고 **다음** 버튼을 선택합니다.  
  
10. **마침** 버튼을 선택하여 나머지 기본 설정을 적용합니다.  
  
## 사용자 지정 워크플로 작업 클래스 추가  
 다음으로, 사용자 지정 워크플로 작업에 대한 코드를 포함하기 위해 프로젝트에 클래스를 추가합니다.  
  
#### 사용자 지정 워크플로 작업 클래스를 추가하려면  
  
1.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택하여 **새 항목 추가** 대화 상자를 표시합니다.  
  
2.  **설치된 템플릿** 트리 뷰에서 **코드** 노드를 선택한 다음 프로젝트 항목 템플릿 목록에서 **클래스** 템플릿을 선택합니다.  기본 이름인 Class1을 사용합니다.  **추가** 단추를 선택합니다.  
  
3.  Class1의 모든 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[SP_AnnBackup#1](../snippets/csharp/VS_Snippets_OfficeSP/sp_annbackup/cs/class1.cs#1)]
     [!code-vb[SP_AnnBackup#1](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_annbackup/vb/class1.vb#1)]  
  
4.  프로젝트를 저장한 다음, 메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
     Class1 은 **AnnouncementBackup 구성 요소** 탭의 **도구 상자** 에서 사용자 지정 작업으로 표시됩니다.  
  
## 사이트 워크플로에 사용자 지정 작업 추가  
 다음으로, 사용자 지정 코드를 포함하기 위해 워크플로에 작업을 추가합니다.  
  
#### 사이트 워크플로에 사용자 지정 작업을 추가하려면  
  
1.  Workflow Designer의 디자인 뷰에서 Workflow1을 엽니다.  
  
2.  **도구 상자** 에서 Class1를 끌어와 `onWorkflowActivated1` 아래에 나타나도록 하거나, 또는 Class1에 대한 바로 가기 메뉴에서 **복사** 를 선택하고, `onWorkflowActivated1` 활동 아래의 줄에 대한 바로 가기 메뉴를 연 다음 **붙여넣기** 를 선택합니다.  
  
3.  프로젝트를 저장합니다.  
  
## 사이트 워크플로 사용자 지정 작업 테스트  
 그 다음, 프로젝트를 실행하고 사이트 워크플로를 시작합니다.  사용자 지정 작업은 백업 알림 목록을 만든 다음 현재 알림 목록의 내용을 백업에 복사합니다.  코드에서 백업 목록을 만들기 전에 이미 있는지 여부를 확인합니다.  백업 목록이 이미 있으면 삭제됩니다.  또한 코드에서 SharePoint 사이트의 빠른 실행 모음에 있는 새 목록에 링크를 추가합니다.  
  
#### 사이트 워크플로 사용자 지정 작업을 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행하고 SharePoint에 배포합니다.  
  
2.  빠른 실행 모음에서 **목록** 링크를 선택하여 SharePoint 사이트에서 사용 가능한 모든 목록을 표시합니다.  **알림**이라는 하나의 알림 목록만 있습니다.  
  
3.  SharePoint 웹 페이지의 맨 위에 있는 **사이트 워크플로** 링크를 선택합니다.  
  
4.  새 워크플로 시작 섹션 아래에서 **AnnouncementBackup \- Workflow1** 링크를 선택합니다.  이렇게 하면 사이트 워크플로가 시작되고 사용자 지정 작업의 코드가 실행됩니다.  
  
5.  빠른 실행 표시줄에서 **알림 백업** 링크를 선택합니다.  **알림** 목록에 포함된 모든 알림이 새 목록에 복사되었습니다.  
  
## 참고 항목  
 [방법: 이벤트 수신자 만들기](../sharepoint/how-to-create-an-event-receiver.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  