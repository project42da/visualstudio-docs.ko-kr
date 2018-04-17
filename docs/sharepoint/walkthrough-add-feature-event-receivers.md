---
title: '연습: 기능 이벤트 수신자 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, advanced packaging tools
- SharePoint development in Visual Studio, event receivers
- SharePoint development in Visual Studio, feature event receivers
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cda3967d0fc95fdd8f28503f209a5f2208d07031
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-add-feature-event-receivers"></a>연습: 기능 이벤트 수신자 추가
  기능 이벤트 수신기는 SharePoint에서 다음과 같은 기능 관련 이벤트 중 하나가 발생할 때 실행 하는 메서드:  
  
-   기능을 설치 합니다.  
  
-   기능을 활성화 합니다.  
  
-   기능이 비활성화 됩니다.  
  
-   기능 제거 됩니다.  
  
 이 연습에는 SharePoint 프로젝트의 기능에는 이벤트 수신기를 추가 하는 방법을 보여 줍니다. 다음 작업을 보여 줍니다.  
  
-   기능 이벤트 수신기를 사용 하 여 빈 프로젝트 만들기  
  
-   처리는 **FeatureDeactivating** 메서드.  
  
-   SharePoint 프로젝트 개체 모델을 사용 하 여 알림을 알림 목록에 추가 합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio.  
  
## <a name="creating-a-feature-event-receiver-project"></a>기능 이벤트 수신기 프로젝트 만들기  
 첫째, 기능 이벤트 수신기를 포함 하도록 프로젝트를 만듭니다.  
  
#### <a name="to-create-a-project-with-a-feature-event-receiver"></a>기능 이벤트 수신기를 사용 하 여 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로**, **프로젝트** 표시 하는 **새 프로젝트** 대화 상자.  
  
2.  확장 하 고는 **SharePoint** 노드 아래의 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **2010** 노드.  
  
3.  에 **템플릿** 창, 선택는 **SharePoint 2010 프로젝트** 서식 파일입니다.  
  
     프로젝트 템플릿은 했기 때문에 기능 이벤트 수신자에 대 한이 프로젝트 형식을 사용 합니다.  
  
4.  에 **이름** 상자에 입력 **FeatureEvtTest**, 선택한 후는 **확인** 표시 하려면 단추는 **SharePoint 사용자 지정 마법사**합니다.  
  
5.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지, 새 사용자 지정 필드 항목을 추가 하려는 SharePoint 서버 사이트에 대 한 URL을 입력 하거나 기본 위치를 사용 하 여 (http://\<*시스템 이름*> /).  
  
6.  에 **이 SharePoint 솔루션에 대 한 신뢰 수준을?** 섹션에서 선택 된 **팜 솔루션으로 배포** 옵션 단추입니다.  
  
     샌드박스 솔루션과 팜 솔루션 비교에 대 한 자세한 내용은 참조 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)합니다.  
  
7.  선택 된 **마침** 단추를 클릭 한 다음 Feature1 라고 하는 기능 나타나는지 확인는 **기능** 노드.  
  
## <a name="adding-an-event-receiver-to-the-feature"></a>기능 이벤트 수신기 추가  
 다음으로, 기능 이벤트 수신기를 추가 하 고이 기능이 비활성화 되 면 실행 되는 코드를 추가 합니다.  
  
#### <a name="to-add-an-event-receiver-to-the-feature"></a>기능 이벤트 수신기를 추가 하려면  
  
1.  기능 노드에 대 한 바로 가기 메뉴를 연 다음 선택 **기능 추가** 기능을 만들려고 합니다.  
  
2.  아래는 **기능** 노드를에 대 한 바로 가기 메뉴를 열고 **Feature1**를 선택한 후 **이벤트 수신기 추가** 기능 이벤트 수신기를 추가 하려면.  
  
     Feature1 있는 코드 파일을 추가 합니다. 이 경우 프로젝트의 개발 언어에 따라 Feature1.EventReceiver.cs 또는 Feature1.EventReceiver.vb의 이름은입니다.  
  
3.  프로젝트에서 작성 된 경우 [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)], 아직 없는 경우 이벤트 수신기의 위쪽에 다음 코드를 추가 합니다.  
  
     [!code-csharp[SP_FeatureEvt#1](../sharepoint/codesnippet/CSharp/featureevttest2/features/feature1/feature1.eventreceiver.cs#1)]  
  
4.  이벤트 수신기 클래스는 이벤트로 작동 하는 여러 주석 메서드를 포함 합니다. 대체는 **FeatureDeactivating** 메서드를 다음:  
  
     [!code-vb[SP_FeatureEvt#2](../sharepoint/codesnippet/VisualBasic/featureevt2vb/features/feature1/feature1.eventreceiver.vb#2)]
     [!code-csharp[SP_FeatureEvt#2](../sharepoint/codesnippet/CSharp/featureevttest2/features/feature1/feature1.eventreceiver.cs#2)]  
  
## <a name="testing-the-feature-event-receiver"></a>기능 이벤트 수신기를 테스트합니다.  
 다음으로 테스트 하는 기능을 비활성화 여부는 **FeatureDeactivating** 메서드 SharePoint 알림 목록에 대 한 공지를 출력 합니다.  
  
#### <a name="to-test-the-feature-event-receiver"></a>기능 이벤트 수신기를 테스트 하려면  
  
1.  프로젝트의 값을 설정 **활성 배포 구성** 속성을 **활성화 없음**합니다.  
  
     이 속성을 설정 기능이 SharePoint에서 활성화 되지 않으며 기능 이벤트 수신자를 디버깅할 수 있습니다. 자세한 내용은 참조 [SharePoint 솔루션 디버깅](../sharepoint/debugging-sharepoint-solutions.md)합니다.  
  
2.  선택 된 **F5** 키 프로젝트를 실행 하 고 SharePoint에 배포 합니다.  
  
3.  SharePoint 웹 페이지의 위쪽 엽니다는 **사이트 작업** 메뉴를 선택한 후 **사이트 설정**합니다.  
  
4.  아래는 **사이트 작업** 섹션은 **사이트 설정** 페이지를 선택 합니다는 **사이트 기능 관리** 링크 합니다.  
  
5.  에 **기능** 페이지를 선택 합니다는 **Activate** 단추 옆에 **FeatureEvtTest Feature1** 기능입니다.  
  
6.  에 **기능** 페이지를 선택 합니다는 **비활성화** 단추 옆에 **FeatureEvtTest Feature1** 기능을 선택한 후는 **이 기능을 비활성화**  확인 기능을 비활성화 하는 링크입니다.  
  
7.  선택 된 **홈** 단추입니다.  
  
     에 알림을 표시는 **공지** 기능이 비활성화 된 후에 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 이벤트 수신기 만들기](../sharepoint/how-to-create-an-event-receiver.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  