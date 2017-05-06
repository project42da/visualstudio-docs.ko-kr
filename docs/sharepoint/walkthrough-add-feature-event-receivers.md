---
title: "연습: 기능 이벤트 수신자 추가"
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
  - "Visual Studio에서 SharePoint 개발, 고급 패키징 도구"
  - "Visual Studio에서 SharePoint 개발, 이벤트 수신자"
  - "Visual Studio에서 SharePoint 개발, 기능 이벤트 수신자"
ms.assetid: fbd44c33-2c27-4d57-abca-21cddc16fbc3
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 23
---
# 연습: 기능 이벤트 수신자 추가
  기능 이벤트 수신자는 다음과 같은 기능 관련 이벤트 중 하나가 SharePoint에서 발생할 때 실행되는 메서드입니다.  
  
-   기능이 설치된 경우  
  
-   기능이 활성화된 경우  
  
-   기능이 비활성화된 경우  
  
-   기능이 제거된 경우  
  
 이 연습에서는 SharePoint 프로젝트의 기능에 이벤트 수신자를 추가하는 방법을 보여 줍니다.  다음과 같은 작업을 보여 줍니다.  
  
-   기능 이벤트 수신자가 포함된 빈 프로젝트 만들기  
  
-   **FeatureDeactivating** 메서드 처리  
  
-   SharePoint 프로젝트 개체 모델을 사용하여 알림 목록에 알림 추가  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio  
  
## 기능 이벤트 수신자 프로젝트 만들기  
 먼저 기능 이벤트 수신자가 포함될 프로젝트를 만듭니다.  
  
#### 기능 이벤트 수신자가 포함된 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 을 선택합니다.  
  
3.  **템플릿** 창에서 **SharePoint 2010 프로젝트** 템플릿을 선택합니다.  
  
     기능 이벤트 수신자에는 프로젝트 템플릿이 없으므로 이 프로젝트 형식이 사용됩니다.  
  
4.  **이름** 상자에 FeatureEvtTest를 입력한 다음 **확인** 버튼을 선택하여 **SharePoint 사용자 지정 마법사**를 표시합니다.  
  
5.  **디버깅에 사용할 사이트 및 보안 수준 지정** 페이지에서 새 사용자 지정 필드 항목을 추가할 SharePoint 서버 사이트의 URL을 입력하거나 기본 위치\(http:\/\/\<*system name*\>\/\)를 사용합니다.  
  
6.  **이 SharePoint 솔루션의 신뢰 수준을 선택하십시오.** 섹션에서 **팜 솔루션으로 배포** 옵션 단추를 선택합니다.  
  
     샌드박스가 적용된 솔루션과 팜 솔루션 비교에 대한 자세한 내용은 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)을 참조하십시오.  
  
7.  **완료** 버튼을 선택한 다음 **기능** 노드 밑에 Feature1 라는 기능이 나타나는지 확인합니다.  
  
## 기능에 이벤트 수신자 추가  
 다음으로, 기능에 이벤트 수신자를 추가하고 기능이 비활성화될 때 실행되는 코드를 추가합니다.  
  
#### 기능에 이벤트 수신자를 추가하려면  
  
1.  기능 노드의 바로 가기 메뉴를 열고 **기능 추가** 를 선택하여 기능을 생성합니다.  
  
2.  **기능** 노드 아래의 **Feature1** 에 대한 바로 가기 메뉴를 연 다음, **이벤트 수신자 추가** 를 선택하여 기능에 이벤트 수신자를 추가합니다.  
  
     Feature1 아래에 코드 파일이 추가됩니다.  이 경우 프로젝트의 개발 언어에 따라 파일 이름이 Feature1.EventReceiver.cs 또는 Feature1.EventReceiver.vb로 지정됩니다.  
  
3.  프로젝트가 [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)]로 작성 된 경우, \(아직 없을 경우\) 이벤트 수신자의 맨 앞에 다음 코드를 추가 합니다.  
  
     [!code-csharp[SP_FeatureEvt#1](../snippets/csharp/VS_Snippets_OfficeSP/sp_featureevt/cs/features/feature1/feature1.eventreceiver.cs#1)]  
  
4.  이벤트 수신자 클래스에는 이벤트로 작동하는 주석 처리된 여러개의 메서드가 포함되어 있습니다.  **FeatureDeactivating** 메서드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[SP_FeatureEvt#2](../snippets/csharp/VS_Snippets_OfficeSP/sp_featureevt/cs/features/feature1/feature1.eventreceiver.cs#2)]
     [!code-vb[SP_FeatureEvt#2](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_featureevt/vb/features/feature1/feature1.eventreceiver.vb#2)]  
  
## 기능 이벤트 수신자 테스트  
 다음으로, **FeatureDeactivating** 메서드가 SharePoint 알림 목록에 알림을 출력하는지 여부를 테스트하는 기능을 비활성화합니다.  
  
#### 기능 이벤트 수신자를 테스트하려면  
  
1.  프로젝트의 **활성 배포 구성** 속성의 값을 **활성화 없음**으로 설정합니다.  
  
     이 속성을 설정하면 기능이 SharePoint에서 활성화되지 않으며 기능 이벤트 수신자를 디버깅할 수 있습니다.  자세한 내용은 [SharePoint 솔루션 디버깅](../sharepoint/debugging-sharepoint-solutions.md)을 참조하십시오.  
  
2.  **F5** 키를 눌러 프로젝트를 실행하고 SharePoint에 배포합니다.  
  
3.  SharePoint 웹 페이지의 맨 위에서 **사이트 작업** 메뉴를 선택한 다음 **사이트 설정**을 선택합니다.  
  
4.  **사이트 설정** 페이지의 **사이트 작업** 섹션에서 **사이트 기능 관리** 링크를 선택합니다.  
  
5.  **사이트 기능** 페이지에서 **FeatureEvtTest Feature1** 기능 옆에 있는 **활성화** 단추를 선택합니다.  
  
6.  **기능** 페이지에서 **FeatureEvtTest Feature1** 기능 옆에 있는 **비활성화** 버튼을 선택한 다음, **이 기능을 비활성화** 확인 링크를 선택하여 기능을 비활성화 합니다.  
  
7.  **홈** 버튼을 선택합니다.  
  
     기능이 비활성화된 후 **알림** 목록에 알림이 표시되는 것을 확인합니다.  
  
## 참고 항목  
 [방법: 이벤트 수신자 만들기](../sharepoint/how-to-create-an-event-receiver.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  