---
title: "알림 및 Visual Studio에 대 한 진행률 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0ef65e9-0f1f-45f4-9f25-6e2398691168
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 00ab0622820777f556eff667e6de5f769196e6b0
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="notifications-and-progress-for-visual-studio"></a>알림 및 Visual Studio에 대 한 진행률
##  <a name="BKMK_NotificationSystems"></a>알림 시스템  
  
### <a name="overview"></a>개요  
 여러 가지 방법으로에서 일어나는 Visual Studio 소프트웨어 개발 작업에 대 한 사용자에 게 알립니다.  
  
 모든 종류의 알림 구현 하는 경우:  
  
-   **최소 수준으로 알림 수를 유지** 효과적인 수 있습니다. 알림 메시지의 특정 기능/기능 영역의 사용자 또는 대부분의 Visual Studio 사용자에 적용 해야 합니다. 알림의 과도 하 게 사용 사용자 sidetrack 수도 감소 하 여 인지 된 시스템의 사용 편의성 있습니다.  
  
-   **메시지를 명확 하 고 조치 가능한 상태로 표시 하는 확인** 사용자 더 복잡 한 선택 및 추가 작업을 수행 하는 것에 대 한 적절 한 컨텍스트를 호출 하는 데 사용할 수 있습니다.  
  
-   **동기 및 비동기 메시지를 적절 하 게 제공 합니다.** 동기 알림을 나타내는 즉각적인 주의가 필요한 웹 서비스가 충돌 하는 경우 또는 코드 같은 예외가 throw 됩니다. 사용자와 같은 모달 대화 상자에서 해당 입력이 필요한 방식 바로 이러한 경우 알려 주어 야 합니다. 비동기 알림을는 사용자에 대해 알아야 하지만 필요가 없습니다 즉시 사용 될 웹 사이트 배포 완료 된 빌드 작업이 완료 될 때 또는 같은 것입니다. 이러한 메시지 더 앰비언트와 사용자의 작업 흐름이 중단 합니다.  
  
-   **사용자 추가 작업을 수행 하는 것을 금지 하는 데 필요한 경우에 모달 대화 상자를 사용 하 여** 메시지를 승인 하거나 대화 상자에 제공 된 결정을 내리기 전에 합니다.  
  
-   **더 이상 사용할 때 앰비언트 알림을 제거 합니다.** 에 대 한 알림이 표시 된 문제를 해결 하는 작업이 이미 도달한 경우 알림을 해제 하려면 사용자는 필요 하지 않습니다.  
  
-   **주의 알림을 잘못 된 상관 관계를 발생할 수 있습니다.** 사용자는 하나 이상의 작업을 트리거 했습니다 알림을 실제로 인과 관계가 없는 판단할 수도 있습니다. 컨텍스트, 트리거 및 알림 메시지의 원본에 대 한 알림 메시지에 분명 수 있습니다.  
  
### <a name="choosing-the-right-method"></a>적합 한 방법 선택  
 이 표를 사용 하 여 메시지의 사용자에 게 적합 한 방법 선택 하는 데 도움이 됩니다.  
  
|메서드|사용|사용 하지 마십시오|  
|------------|---------|----------------|  
|[모달 오류 메시지 대화 상자](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ModalErrorMessageDialogs)|계속 하기 전에 사용자 응답을 요청할 때 사용 합니다.|사용자를 차단 하 고의 흐름을 중단할 필요가 없을 때 사용 하지 마십시오. 개입 수준이 낮습니다 다른 방법으로 메시지를 표시 하려면 가능한 경우 모달 대화 상자를 사용 하지 마십시오.|  
|[IDE 상태 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_IDEStatusBar)|프로세스의 상태와 관련 된 앰비언트 텍스트 정보 경우 사용 합니다.|단독 사용 하지 마십시오. 다른 의견 보내기 메커니즘와 함께에서 가장 적합합니다.|  
|[포함 된 정보 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_EmbeddedInfobar)|도구 창이 나 문서 창에 진행률, 오류 상태, 결과 및/또는 동작 가능한 정보에 알리기 위해 사용 합니다.|정보 표시줄을 배치할 위치와 관련이 없는 경우 사용 하지 마십시오.<br /><br /> 문서/도구 창 외부 사용 하지 마십시오.|  
|[마우스 커서 변경 사항](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_MouseCursorChanges)|작업이 진행 되에 알리기 위해 사용할 수 있습니다. 또한 마우스 커서가 그리기 모드 같은 특정 모드에서 끌기/놓기 진행 중이거나 하는 경우와 같은 마우스에 상태 변화가 있다는 알리는 데 사용 합니다.|짧은 진행 중인 변경에 대 한 사용 하지 않거나의 펄럭이는 커서 호스팅되고 (예를 들어 경우에 전체 프로세스 대신 오래 실행 중인 프로세스의 부분에 연관 됨).|  
|[진행률 표시기](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_NotSysProgressIndicators)|(비활성화 상태 또는 결정 되지 않은) 진행률을 보고 필요한 경우 사용 합니다. 진행률 표시기 유형이 및 각각에 대 한 특정 사용의 여러 가지가 있습니다. 참조 [진행률 표시기](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ProgressIndicators)합니다.||  
|[Visual Studio 알림 창](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_VSNotificationsToolWindow)|알림 창이 공개적으로 확장할 수는 없습니다. 그러나 다양 한 라이선스와 Visual Studio 또는 패키지 업데이트의 정보 알림 중요 한 문제를 포함 하 여 Visual Studio에 대 한 메시지를 통신에 사용 됩니다.|다른 유형의 알림 사용 하지 마십시오.|  
|[오류 목록](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ErrorList)|문제가 문제가 발생 (오류/경고/정보) 사용자의 현재 열려 있는 솔루션에 직접 연결을 하는 경우 코드에 어떤 작업도 할 수 있습니다.<br /><br /> 이 예를 포함 합니다.<br /><br /> -컴파일러 메시지 (오류/경고/정보)<br /><br /> 코드에 대 한 코드 분석기/진단 메시지<br /><br /> 빌드 메시지<br /><br /> 솔루션 탐색기 표시를 먼저 고려 아니라 프로젝트 또는 솔루션 파일에 관련 된 문제에 대 한 적절 한 수 있습니다.|사용자의 열려 있는 솔루션 코드에 모든 관계를 갖지 않는 항목에 대 한 사용 하지 마십시오.|  
|편집기 알림: 전구|열려 있는 파일에 존재 하는 문제를 해결할 수 있는 문제를 해결 해야 하는 경우 사용 합니다.<br /><br /> 전구 빠른 작업, 리팩터링 등 필요에 따라 사용자의 코드에 대해 수행 하지만 경우 "알림 스타일입니다." 나타나지 것입니다 호스팅용 또한 사용 해야 하는 참고|열린 파일에 모든 관계를 갖지 않는 항목에 대 한 사용 하지 마십시오.|  
|편집기 알림: 물결선|특정 범위에가 열려 있는 코드 (예를 들어 오류에 대 한 빨간색 물결)의 문제가 사용자에 게 알리도록 하려면 사용 합니다.|가 열려 있는 코드의 특정 범위와 관련 되지 않는 항목에 대 한 사용 하지 마십시오.|  
|[포함 된 상태 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_EmbeddedStatusBars)|사용 하 여 콘텐츠 또는 특정 도구 창, 문서 창 또는 대화 상자 창의 컨텍스트 내에서 프로세스와 관련 된 상태를 제공 합니다.|일반적인 제품 알림, 프로세스 또는 특정 창 내에서 콘텐츠를 모든 관계를 갖지 않는 항목에 대 한 사용 하지 마십시오.|  
|[Windows 트레이에서 알림](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_WindowsTray)|Proc 아웃 프로세스에 대 한 알림 화면 또는 응용 프로그램 도우미를 사용 합니다.|IDE에 관련 된 알림을 사용 하지 마십시오.|  
|[알림 거품형](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_NotificationBubbles)|원격 프로세스의 변경 또는를 사용 하 여 **외부** IDE의 합니다.|프로세스의 사용자에 게 알리기 위한 수단으로 사용 하지 마십시오 **내** IDE.|  
  
### <a name="notification-methods"></a>알림 방법  
  
####  <a name="BKMK_ModalErrorMessageDialogs"></a>모달 오류 메시지 대화 상자  
 모달 오류 메시지 대화 상자가 사용자의 휴지통 또는 확인 작업을 필요로 하는 오류 메시지를 표시 하는 데 사용 됩니다.  
  
 ![모달 오류 메시지](../../extensibility/ux-guidelines/media/0901-01_modalerrormessage.png "0901 01_ModalErrorMessage")  
  
 **데이터베이스에 잘못 된 연결 문자열의 사용자에 게 알리는 모달 오류 메시지 대화 상자**  
  
####  <a name="BKMK_IDEStatusBar"></a>IDE 상태 표시줄  
 사용자 상태 표시줄 텍스트를 표시 하는 가능성 최고의 컴퓨터 환경 및 Windows 플랫폼 특정 경험을 연관 시킵니다. Visual Studio 고객 기반 경향이 두 영역에서 숙련 된 경우에 잘 알고 있는 Windows 사용자는 상태 표시줄에 변경 내용을 놓칠 수 있기 때문입니다. 따라서 상태 표시줄은 적합 정보 제공의 목적 또는 중복 신호로 정보가 다른 곳에서 표시에 대 한 합니다. 알림 도구 창에서 또는 대화 상자에서 모든 종류의 사용자는 즉시 확인 해야 하는 중요 한 정보를 제공 합니다.  
  
 Visual Studio 상태 표시줄은 여러 유형의 정보 표시 될 수 있도록 설계 되었습니다. 피드백, 디자이너, 진행률 표시줄, 애니메이션 및 클라이언트에 대 한 영역으로 구분 됩니다.  
  
 피드백 영역와 디자이너 영역 항상 표시 됩니다. 진행률 표시줄 및 애니메이션 영역은 항상 동적이 고 사용자 컨텍스트를 기반 합니다. 디자이너 영역에 문자 메시지에 대 한 해당 리소스에서 가져온 문자열의 길이 의해 결정 고정 폭이 지정 합니다. 따라서 지역화를를 코드 변경 하지 않고도 너비를 조정할 수 있습니다. 영어의 경우이 문자열의 너비는 대략 220 픽셀입니다. 디자이너 영역을 정상적으로 작동 하 고 피드백 영역 나머지 공간을 처리 합니다.  
  
 상태 표시줄은도 IDE이 디버그 모드에 있을 때와 같은 다양 한 IDE 상태 변경을 통신 하 여 시각적 효과 기능 값을 추가 하 여 색이 지정 합니다.  
  
 ![IDE 상태 표시줄 색 변경](../../extensibility/ux-guidelines/media/0901-02_idestatusbar.png "0901 02_IDEStatusBar")  
  
 **IDE 상태 표시줄 색상**  
  
####  <a name="BKMK_EmbeddedInfobar"></a>포함 된 정보 표시줄  
 정보 표시줄과 문서 창이 나 도구 창의 맨 위에 있는 시 / 조건 사용자에 게 알리는 데 사용할 수 있습니다. 또한 사용자를 쉽게 작업을 수행 하는 방법을 가질 수 있습니다 명령을 제공할 수 있습니다. 정보 표시줄 표준 셸 컨트롤입니다. 작동 되며 IDE에서 다른 사용자와 일치 하지 않는 표시를 직접 만들지는 마십시오. 참조 [정보 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars) 구현 세부 정보 및 사용 지침에 대 한 합니다.  
  
 ![Embedded infobar](../../extensibility/ux-guidelines/media/0901-03_embeddedinfobar.png "0901-03_EmbeddedInfobar")  
  
 **기록 디버깅 모드에서 IDE 되 고 편집기에서 표준 디버깅 모드와 같은 방식으로 응답 하지 않을 사용자에 게 알려주는 문서 창에 포함 된 정보 표시줄입니다.**  
  
####  <a name="BKMK_MouseCursorChanges"></a>마우스 커서 변경 사항  
 마우스 커서를 변경할 때는 VSColor 서비스에 연결 되 고 이미 커서와 연결 되어 있는 색을 사용 합니다. 커서 변경 사항 진행 중인 작업을 나타내는 데 사용할 수 있습니다으로 끌어을 끌어다 놓을 하거나 개체를 선택 하려면 사용할 수 있는 대상 사용자가 마우스로 영역을 적중 합니다.  
  
 모든 추가 입력 표현에서 때문에 사용자는 작업에 대 한 모든 사용 가능한 CPU 시간을 예약 해야 하는 경우에 사용 중/대기 마우스 커서를 사용 합니다. 다중 스레딩을 사용 하 여는 잘 작성 된 응용 프로그램으로 대부분의 경우 때 수 없는 사용자에서 다른 작업을 수행 하는 시간이 거의 발생 하지 않아야 합니다.  
  
 정보에 대 한 중복 큐 다른 곳에서 제시 된 커서 변경 사항 유용 하다는 것을 명심 하십시오. 유일한 방법으로 무언가 전달 하려고 하는 경우에 특히 사용자와 통신 하는 사용자 해결 해야 하는 커서 변경에 의존 하지 마십시오.  
  
####  <a name="BKMK_NotSysProgressIndicators"></a>진행률 표시기  
 진행률 표시기는 프로세스를 완료 하려면 몇 초를 사용 하는 동안 사용자에 게 피드백을 제공 하는 것에 대 한 중요 합니다. 진행률 표시기 나타날 수 있는 원위치 (시작 지점 부근 작업 진행 중), 포함 된 상태 표시줄, 모달 대화 상자 또는 Visual Studio 상태 표시줄에 합니다. 지침에 따라 [진행률 표시기](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ProgressIndicators) 용도 구현에 대 한 합니다.  
  
####  <a name="BKMK_VSNotificationsToolWindow"></a>Visual Studio 알림 창  
 Visual Studio 알림 창 라이선스, 환경 (Visual Studio), 확장명 및 업데이트 하는 방법에 대 한 개발자를 게 알립니다. 개별 알림을 해제할 사용자나 특정 종류의 알림 무시 하도록 선택할 수 있습니다. 무시 된 알림 목록에서 관리 되는 **도구 > 옵션** 페이지.  
  
 알림 창이 현재 확장할 수는 없습니다.  
  
 ![Visual Studio 알림 창](../../extensibility/ux-guidelines/media/0901-06_vsnotificationswindow.png "0901 06_VSNotificationsWindow")  
  
 **Visual Studio 알림 도구 창**  
  
####  <a name="BKMK_ErrorList"></a>오류 목록  
 오류 목록에서 알림을 컴파일하는 동안 발생 또는 및 빌드 프로세스 및 해당 특정 코드 오류가 발생 하는 코드를 탐색할 수 있도록 하는 오류 및 경고를 나타냅니다.  
  
 ![오류 목록](../../extensibility/ux-guidelines/media/0901-08_errorlist.png "0901 08_ErrorList")  
  
 **Visual Studio의 오류 목록**  
  
####  <a name="BKMK_EmbeddedStatusBars"></a>포함 된 상태 표시줄  
 IDE 상태 표시줄에는 현재 문서 창 및 사용자의 컨텍스트 및/또는 시스템 응답에 업데이트 된 정보로 설정 하는 클라이언트 영역 컨텍스트와 동적, 어렵습니다 정보의 연속 표시 유지 관리 또는 장기의 상태를 지정 하려면 비동기 프로세스입니다. 예를 들어 IDE 상태 표시줄에 대 한 여러 실행 및/또는 즉시 실행 가능한 항목이 선택 항목에 대 한 테스트 실행 결과 알림을 적합 하지 않습니다. 사용자가 항목을 선택 하거나 프로세스를 시작 있는 문서 또는 도구 창 컨텍스트에서 이러한 상태 정보를 유지 하는 것이 유용 합니다.  
  
 ![포함 된 상태 표시줄](../../extensibility/ux-guidelines/media/0901-09_embeddedstatusbar.png "0901 09_EmbeddedStatusBar")  
  
 **Visual Studio에 포함 된 상태 표시줄**  
  
####  <a name="BKMK_WindowsTray"></a>Windows 트레이에서 알림  
 Windows 작업 표시줄에서 Windows 알림 영역 옆에 있는 시스템은 클록입니다. 다양 한 유틸리티와 소프트웨어 구성 요소는 사용자는 화면 해상도 변경 하거나 소프트웨어 업데이트를 가져오는 등의 시스템 차원의 작업에 대 한 상황에 맞는 메뉴를 볼 수 있도록이 영역에서 아이콘을 제공 합니다.  
  
 환경 수준 알림 Visual Studio 알림 허브 Windows 알림 영역에에서 표시 되어야 합니다.  
  
####  <a name="BKMK_NotificationBubbles"></a>알림 거품형  
 알림 거품형 정보는 편집기/디자이너 내에서 또는 Windows 알림 영역의 일부로 나타날 수 있습니다. 사용자에 게 이러한 거품 나중 해결할 수 있는 문제 단순한 알림에 대 한 이점은입니다. 거품은 사용자를 즉시 해결 해야 하는 중요 한 정보에 대 한 적합 하지 않습니다. 알림 거품을 사용 하 여 Visual Studio에서 수행, 경우에 따라는 [알림 거품에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742472\(v=vs.85\).aspx)합니다.  
  
 ![알림 거품형](../../extensibility/ux-guidelines/media/0901-07_notificationbubbles.png "0901 07_NotificationBubbles")  
  
 **Visual Studio에 사용 되는 Windows 알림 영역에서 알림 거품형**  
  
##  <a name="BKMK_ProgressIndicators"></a>진행률 표시기  
  
### <a name="overview"></a>개요  
 진행률 표시기는 사용자에 게 피드백을 제공 하기 위한 알림 시스템의 중요 한 부분입니다. 사용자를 알 프로세스와 작업을 완료 합니다. 친숙 한 표시기 유형에 진행률 표시줄, 회전 커서 및 애니메이션된 아이콘입니다. 진행률 표시기의 배치와 유형을 보고 내용을 포함 하 여 컨텍스트 및 기간 프로세스 또는 작업 완료에 소요 될에 따라 달라 집니다.  
  
#### <a name="factors"></a>요소  
 적절 한 표시기 유형이 인지를 확인 하기 위해서는 다음과 같은 요소를 결정 해야 합니다.  
  
1.  **타이밍:** 시간의 길이 작업 걸립니다  
  
2.  **형식:** 작업 (잠금 프로세스가 완료 될 때까지 UI) 환경에 모달 인지 여부  
  
3.  **영구/일시적:** 진행률의 최종 결과 나중에 보고 된 및/또는 볼 수 있는 수 해야 하는 여부  
  
4.  **활성화 상태의/비활성:** 작업 종료 시간 및 진행률을 계산할 수 있는지 여부  
  
5.  **그래픽/Textual 위치:** 진행률 또는 프로세스 메시지나 트리 컨트롤 같은 특정 컨트롤의 본문에서 캡처된 인라인 인지 여부  
  
6.  **근접:** 근접 관련이 UI 진행률 여야 하는지 여부입니다. (예를 들어 멀리 떨어져 될 수 있는 상태 표시줄에 방식일 수 또는 프로세스를 시작 하는 단추의 전화기가 옆에 있습니까)?  
  
#### <a name="determinate-progress"></a>활성화 상태의 진행률  
  
|진행률 유형|시기 및 사용 하는 방법|노트|  
|-------------------|-------------------------|-----------|  
|진행률 표시줄 (비활성화 상태)|예상 기간의 > 5 초입니다.<br /><br /> 프로세스 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.|**안 함** 애니메이션에 텍스트를 포함 합니다.|  
|정보 표시줄|메시징 상황별 UI와 연결 합니다. 참조 [정보 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars)합니다.<br /><br /> 프로세스 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.|**안 함** 여러 프로세스를 표시 해야 할 때 여러 정보 표시줄을 사용 합니다. 누적된 진행률 표시줄을 대신 사용 합니다.|  
|출력 창|일시적인 알림: 해당 사용자가 하고자 할 앱 수준 프로세스 **검토** 완료 된 후의 세부 정보입니다.|**안 함** 는 사용자가 나중에 데이터를 참조 해야 하는 경우 사용 합니다.|  
|로그 파일|이를 중요 한 경우에서 intransient 알림 쌍을 이루는 **저장** 완료 한 후 세부 정보입니다.||  
|상태 표시줄|일시적인 알림: 응용 프로그램 수준 프로세스 해당 사용자는 **필요는 없습니다** 완료 된 후의 세부 정보입니다.<br /><br /> 포함 된 진행률 표시줄을 포함합니다.<br /><br /> 프로세스 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.||  
  
#### <a name="indeterminate-progress"></a>비활성화 상태의 진행률  
  
|진행률 유형|시기 및 사용 하는 방법|노트|  
|-------------------|-------------------------|-----------|  
|진행률 표시줄 (비활성화 상태)|예상 기간의 > 5 초입니다.<br /><br /> 프로세스 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.|**안 함** 애니메이션에 텍스트를 포함 합니다.|  
|개미 (애니메이션된 가로 점)|서버에 왕복 합니다.<br /><br /> 컨텍스트의 near 지점 부모 컨테이너의 위쪽에 배치합니다.|**안 함** 전체 컨테이너의 자식이 있는 경우 사용 합니다.|  
|스핀 상자 (진행률 링)|프로세스 또는와 관련 된 상황별 UI 공간은 고려 사항입니다.<br /><br /> 프로세스 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.||  
|정보 표시줄|메시징 상황별 UI와 연결 합니다. 참조 [정보 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars)합니다.|**안 함** 여러 프로세스를 표시 해야 할 때 여러 정보 표시줄을 사용 합니다. 누적된 진행률 표시줄을 대신 사용 합니다.|  
|출력 창|일시적인 알림: 응용 프로그램 수준 프로세스 해당 사용자는 하려면 **검토** 완료 된 후의 세부 정보입니다.|**안 함** 세션 간에 유지 하는 정보를 사용 합니다.|  
|로그 파일|이를 중요 한 경우에서 intransient 알림 쌍을 이루는 **저장** 완료 한 후 세부 정보입니다.||  
|상태 표시줄|일시적인 알림: 응용 프로그램 수준 프로세스 해당 사용자는 **필요는 없습니다** 완료 된 후의 세부 정보입니다.<br /><br /> 포함 된 진행률 표시줄을 포함합니다.<br /><br /> 프로세스 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.||  
  
### <a name="progress-indicator-types"></a>진행률 표시기 유형이  
  
#### <a name="progress-bars"></a>진행률 표시줄  
  
##### <a name="indeterminate"></a>비활성화 상태  
 ![비활성화 상태의 진행률 표시줄](../../extensibility/ux-guidelines/media/0901-04_indeterminate.png "0901 04_Indeterminate")  
  
 **비활성화 상태의 진행률 표시줄**  
  
 "비활성화"는 작업의 전반적인 진행 상황을 의미 하거나 프로세스를 확인할 수 없습니다. 시간 제한 없이 만큼을 필요로 하는 원본 또는 대상 개체의 수 알된 수를 액세스 하는 작업에 대 한 비활성화 상태의 진행률 표시줄을 사용 합니다. 발생 하는 작업에 대 한 텍스트 설명을 사용 합니다. 시간 제한을 사용 하 여 시간 기반 연산으로 경계를 제공 합니다. 비활성화 상태의 진행률 표시줄 표시 진행 상황을 않지만 없는 다른 정보를 제공 하려면 애니메이션을 사용 합니다. 비활성화 상태의 진행률 표시줄의 정확도 가능한 때문에만 선택 하지 마십시오.  
  
##### <a name="determinate"></a>비활성화 상태  
 ![활성화 상태의 진행률 표시줄](../../extensibility/ux-guidelines/media/0901-05_determinate.png "0901 05_Determinate")  
  
 **활성화 상태의 진행률 표시줄**  
  
 "비활성화"는 작업 또는 프로세스는 해야 함을 의미는 제한 된 기간 1 시간을 정확 하 게 예측할 수 없는 경우에 합니다. 명확 하 게 완료를 표시 합니다. 작업이 완료 된 경우가 아니면 100%로 이동 하는 동안 진행률 표시줄이 주저 하지 마시기 바랍니다. 활성화 상태의 진행률 표시줄 애니메이션 0에서 100% 왼쪽에서 오른쪽 이동합니다.  
  
 작업 하는 동안 이전 버전과 진행률 표시기를 이동 하지 않습니다. 막대 앞으로 이동 꾸준히는 작업이 시작 되 고 끝날 때 100%에 도달 해야 합니다. 진행률 표시줄의 지점 사용자의 전체 작업의 소요 시간, 관련 된 단계 수에 관계 없이 예측을 제공 하는 것입니다.  
  
##### <a name="concurrent-reporting-stacked-progress-bars"></a>동시 (누적된 진행률 표시줄)를 보고 합니다.  
 작업-시간이 오래 걸리는 경우 아마도 몇 분-다음 두 개의 진행률 표시줄 사용할 수 있습니다., 작업에 대 한 전반적인 진행률 및 현재 단계의 진행에 대 한 다른 표시 하는 하나입니다. 예를 들어 설치 프로그램 파일을 복사 하는 경우 개의 진행률 표시줄을 나타내는 전체 프로세스의 소요 시간 동안 두 번째 현재 파일의 비율을 나타낼 수 있습니다 또는 디렉터리를 복사 하는 동안 사용 수 있습니다. 6 개 이상의 동시 작업 또는 누적된 진행률 표시줄을 사용 하 여 프로세스를 보고 하지 않습니다. 6 개 이상의 동시 작업 또는 보고서에 대 한 프로세스를 설정한 경우 사용 모달 대화 상자 "취소" 단추가 및 보고서를 출력 창에 진행률 세부 정보.  
  
##### <a name="textual-descriptions"></a>텍스트 설명  
 발생 하는 작업에 대 한 텍스트 설명을 완료 될 때까지 예상된 시간을 사용 합니다. 작업 시간이 얼마나 알 수 없는 경우 진행률 표시줄 보다는 애니메이션된 아이콘 피드백 제공에 대 한 더 적합할 수 있습니다.  
  
 Visual Studio는 Visual Studio에 통합 하는 모든 제품에서 사용할 수 있는 상태 표시줄에 표준 진행률 표시줄을 제공 합니다. 진행률 표시줄에 애니메이션 효과가 적용 되어 하는 동안 발생 하는 작업의 텍스트 설명에 대 한 상태 표시줄의 텍스트를 업데이트할 수 있습니다.  
  
#### <a name="other-progress-indicators"></a>다른 진행률 표시기  
  
##### <a name="ants-animated-horizontal-dots"></a>개미 (애니메이션된 가로 점)  
 ![진행률 ants](../../extensibility/ux-guidelines/media/0903-01_ants.png "0903 01_Ants")  
  
 "개미" 애니메이션된 가로 점에 왕복 비활성화 상태 서버 프로세스에 대 한 시각적 참조를 제공 합니다.  
  
##### <a name="spinner-progress-ring"></a>스핀 상자 (진행률 링)  
 ![진행률 회전자](../../extensibility/ux-guidelines/media/0903-02_spinner.png "0903 02_Spinner")  
  
 스핀 상자 ("진행률 링" 라고도 함)은 비활성화 상태의 진행률 표시기 상황별 UI와 관련 하 여 주로 사용 됩니다. 텍스트 범주 헤더, 메시징, 또는 컨트롤 같은 관련 콘텐츠에 맞게 서로 가까이 있는 회전자를 표시 합니다.  
  
##### <a name="cursor-feedback"></a>커서 피드백  
 2-7 초 사이 하는 작업에 대 한 커서 피드백을 제공 합니다. 일반적으로이 운영 체제에서 제공 하는 대기 커서를 사용 하 여 의미 합니다. 지침은 MSDN 문서를 참조 [Cursors.Wait 속성](https://msdn.microsoft.com/en-us/library/system.windows.input.cursors.wait\(v=vs.110\).aspx)합니다.  
  
#### <a name="progress-indicator-locations"></a>진행률 표시기 위치  
  
##### <a name="status-bar"></a>상태 표시줄  
 상태 표시줄을 통해 응용 프로그램에서 사용자의 작업을 중단 하지 않고 사용자에 게 메시지 및 기타 유용한 정보를 표시 하는 곳입니다. 진행률에 대 한 상태는 일반적으로 창 맨 아래에 표시 됩니다, 진행률 표시줄 표시기와 함께에서 진행률을 측정 하는 방법에 대 한 메시지를 포함 하는 도구 설명 창 수 있습니다.  
  
 ![진행률 표시줄 상태 표시줄](../../extensibility/ux-guidelines/media/0903-03_statusbarprogressbar.png "0903 03_StatusBarProgressBar")  
  
 **진행률 표시줄 상태 표시줄**  
  
 ![상태 표시줄 messaging과 함께](../../extensibility/ux-guidelines/media/0903-04_statusbarmessage.png "0903 04_StatusBarMessage")  
  
 **상태 표시줄 텍스트 설명과 함께**  
  
##### <a name="infobar"></a>정보 표시줄  
 근사치 정보 표시줄 상태 표시줄에 제공 하 컨텍스트 알림 및 메시징는 진행률 표시줄 또는 회전자 같은 비활성화 상태의 진행률 표시기와도 연결할 수 있습니다. 정보 표시줄 세분화 된 수준 진행률 이나 활성화 상태의 진행률 표시를 제공 하지 않아야 합니다. 참조 [정보 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars)합니다.  
  
 ![진행률 표시줄 및 메시징을 포함 된 정보 표시줄](../../extensibility/ux-guidelines/media/0903-05_infobar.png "0903 05_InfoBar")  
  
 **진행률 표시줄 및 텍스트 설명에 포함 된 정보 표시줄**  
  
 ![창 내의 정보 표시줄](../../extensibility/ux-guidelines/media/0903-06_infobarinwindow.png "0903 06_InfoBarInWindow")  
  
##### <a name="inline"></a>인라인  
 인라인 진행률 표시 진행률 로더 형식으로 나타낼 수 있습니다. 진행률 표시기는 메시징, 이룹니다 일반적으로 있지만 이것이 요구 사항은 없습니다.  
  
 ![인라인 진행률 회전자](../../extensibility/ux-guidelines/media/0903-07_inlinespinner.png "0903 07_InlineSpinner")  
  
 **회전자 텍스트 설명과 함께 결합**  
  
 ![인라인 누적 진행률 표시줄](../../extensibility/ux-guidelines/media/0903-08_inlinestackedprogress.png "0903 08_InlineStackedProgress")  
  
 **활성화 상태의 누적된 진행률 표시줄**  
  
 ![인라인 진행률 메시징](../../extensibility/ux-guidelines/media/0903-09_inlinetext.png "0903 09_InlineText")  
  
 **서버 탐색기 인라인 텍스트: 새로 고침 중...**  
  
##### <a name="tool-windows"></a>도구 창  
 전역 진행률 표시의 도구 모음 바로 아래에 배치 하는 비활성화 상태의 진행률 표시줄 표시 됩니다.  
  
 ![전역 비활성화 상태의 진행률 표시줄](../../extensibility/ux-guidelines/media/0903-23_globalindeterminate.png "0903 23_GlobalIndeterminate")  
  
 **팀 탐색기 전역 비활성화 상태의 진행률 표시줄**  
  
##### <a name="dialogs"></a>대화 상자  
 대화는 진행률 로더 형식 중 하나를 포함할 수 있습니다. 진행률 표시기 수 수 메시징 쌍을 이루는 뿐만 아니라 여러 수준의 하위 프로세스를 나타내는 세분화 된 진행률 표시와 결합 합니다.  
  
 ![여러 진행률 표시기 유형이 있는 대화 상자](../../extensibility/ux-guidelines/media/0903-11_dialog.png "0903 11_Dialog")  
  
 **동시 프로세스 및 여러 진행률 표시기 유형이 있는 visual Studio 대화 상자**  
  
 ![진행률 로더 및 메시징와 함께 대화 상자가](../../extensibility/ux-guidelines/media/0903-12_dialog2.png "0903 12_Dialog2")  
  
 **진행률 로더 및 메시징 인라인 명령으로 visual Studio 대화 상자**  
  
##### <a name="document-well"></a>문서 저장소  
 잘 문서 컨트롤과 조합에 여러 진행률 로더 형식을 표시할 수 있습니다.  
  
 ![문서에 잘 메시징 진행률](../../extensibility/ux-guidelines/media/0903-13_documentwell.png "0903 13_DocumentWell")  
  
 **도구 모음 아래 비활성화 상태의 진행률 표시줄**  
  
##### <a name="output-window"></a>출력 창  
 출력 창은 프로세스 진행 및 인라인 텍스트 메시징을 통해 진행 상황을 처리 하기 위한 적합 합니다. 모든 출력 창의 진행률 보고와 함께 상태 표시줄을 사용 해야 합니다.  
  
 ![출력 창에 메시징 진행률](../../extensibility/ux-guidelines/media/0903-14_outputwindow.png "0903 14_OutputWindow")  
  
 **프로세스 진행 상태와 함께 출력 창 및 메시징 대기**  
  
##  <a name="BKMK_Infobars"></a> Infobars  
  
### <a name="overview"></a>개요  
 정보 표시줄 사용자 관심 지점에 가까운 표시기를 제공 하 고 시각적 모양 및 상호 작용의 일관성을 유지 하는 공유 정보 표시줄 컨트롤을 사용 하 여 키를 누릅니다.  
  
 ![Infobar](../../extensibility/ux-guidelines/media/0904-01_infobar.png "0904-01_Infobar")  
  
 **Visual Studio에서 정보 표시줄**  
  
#### <a name="appropriate-uses-for-an-infobar"></a>정보 표시줄과 대 한 적절 한 사용  
  
-   현재 컨텍스트와 관련 된 비 블록 킹 하지만 중요 한 메시지를 사용자에 게 부여 하려면  
  
-   특정 상태 또는 기록 디버깅 하는 등 일부 상호 작용 의미를 전달 하는 조건에는 UI 임을 나타내기 위해  
  
-   사용자에 게 알리도록는 시스템에서 확장 성능 문제를 발생 시키는 경우 등의 문제를 감지 했습니다  
  
-   사용자를 쉽게 파일에 탭과 공백 혼합 된 편집기를 감지 하는 경우 등의 작업을 사용 하는 방법을 제공 하기 위해  
  
##### <a name="do"></a>수행 합니다.  
  
-   간단히 말해 더 간결 하 고 정보 표시줄 메시지 텍스트를 유지 합니다.  
  
-   간결한 링크와 단추에 텍스트를 유지 합니다.  
  
-   사용자에 게 제공 하는 "action" 옵션은 최소만 필요한 동작을 보여 주는 것을 확인 합니다.  
  
##### <a name="dont"></a>안 함:  
  
-   도구 모음에 배치 해야 하는 표준 명령을 제공 하는 정보 표시줄을 사용 합니다.  
  
-   모달 대화 상자 대신 정보 표시줄을 사용 합니다.  
  
-   기간을 벗어나도 부동 메시지를 만듭니다.  
  
-   같은 창 내에서 여러 위치에서 여러 정보 표시줄을 사용 합니다.  
  
#### <a name="can-multiple-infobars-show-at-the-same-time"></a>동시에 여러 정보 표시줄 표시할 수 있습니다.  
 예, 여러 정보 표시줄은 동시에 표시할 수 있습니다. 첫 번째 정보 표시줄 위쪽 및 추가 정보 표시줄 보여 주는 아래에 표시 된 대로, 처음 들어간 것부터 순서 대로 표시 됩니다.  
  
 사용자는 한 번에 최대 3 개의 정보 표시줄을 확인할를 사용할 수 있는 자세한 정보 표시줄 정보 표시줄 영역 됩니다 스크롤 가능한 후 합니다.  
  
### <a name="creating-an-infobar"></a>정보 표시줄과 만들기  
 정보 표시줄에 왼쪽에서 오른쪽 4 개의 섹션이 있습니다.  
  
-   **아이콘:** 아이콘을 추가할 위치입니다. 예: 경고 아이콘 정보 표시줄에 표시 하려는 합니다.  
  
-   **Text:** 필요한 경우 텍스트에 있는 링크와 함께 시나리오/상황 사용자를 설명 하는 텍스트가 중인 추가할 수 있습니다. 간단한 텍스트를 유지 해야 합니다.  
  
-   **작업의 경우:** 링크와 단추를 사용자 프로그램 정보 표시줄에 수행할 수 있는 작업에 대 한이 섹션에 포함 해야 합니다.  
  
-   **닫기 단추가:** 오른쪽 마지막 섹션에서 닫기 단추를 가질 수 있습니다.  
  
#### <a name="creating-a-standard-infobar-in-managed-code"></a>관리 코드에서 표준 정보 표시줄 만들기  
 InfoBarModel 클래스 정보 표시줄에 대 한 데이터 소스를 만드는 데 사용할 수 있습니다. 이러한 네 가지 생성자 중 하나를 사용 합니다.  
  
```  
public InfoBarModel(IEnumerable<IVsInfoBarTextSpan> textSpans, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
  
```  
  
```  
public InfoBarModel(string text, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
  
```  
  
```  
public InfoBarModel(IEnumerable<IVsInfoBarTextSpan> textSpans, IEnumerable<IVsInfoBarActionItem> actionItems, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
  
```  
  
```  
public InfoBarModel(string text, IEnumerable<IVsInfoBarActionItem> actionItems, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
```  
  
 하이퍼링크, 실행 단추, 아이콘와 일부 텍스트를 포함 한 InfoBarModel 만드는 예제는 다음과 같습니다.  
  
 ![하이퍼링크와 정보 표시줄](../../extensibility/ux-guidelines/media/0904-02_infobarhyperlink.png "0904 02_InfobarHyperlink")  
  
```  
var infoBar = new InfoBarModel(  
    textSpans: new[]  
    {  
        new InfoBarTextSpan("This is a "),  
        new InfoBarHyperlink("hyperlink"),  
        new InfoBarTextSpan(" InfoBar.")  
    },  
    actionItems: new[]  
    {  
        new InfoBarButton("Click Me")  
    },  
    image: KnownMonikers.StatusInformation,  
    isCloseButtonVisible: true);  
  
```  
  
#### <a name="creating-a-standard-infobar-in-native-code"></a>네이티브 코드에서 표준 정보 표시줄 만들기  
 네이티브 코드에서 정보 표시줄과 제공 하기 위해 The IVsInfoBar 인터페이스를 구현 합니다.  
  
```  
public interface IVsInfoBar  
{  
    IVsInfoBarActionItemCollection ActionItems { get; }  
    ImageMoniker Image { get; }  
    bool IsCloseButtonVisible { get; }  
    IVsInfoBarTextSpanCollection TextSpans { get; }  
}  
  
```  
  
#### <a name="getting-an-infobar-uielement-from-an-infobar"></a>정보 표시줄과 UIElement 정보 표시줄에서 가져오기  
 InfoBarModel 또는 IVsInfoBar 구현에는 UI에 표시 하기 위해는 UIElement로 설정 해야 하는 데이터 모델입니다. SVsInfoBarUIFactory/IVsInfoBarUIFactory 서비스와는 UIElement은 검색할 수 있습니다.  
  
```  
private bool TryCreateInfoBarUI(IVsInfoBar infoBar, out IVsInfoBarUIElement uiElement)  
{  
    IVsInfoBarUIFactory infoBarUIFactory = serviceProvider.GetService(typeof(SVsInfoBarUIFactory)) as IVsInfoBarUIFactory;  
    if (infoBarUIFactory == null)  
    {  
        uiElement = null;  
        return false;  
    }  
  
    uiElement = infoBarUIFactory.CreateInfoBar(infoBar);  
    return uiElement != null;  
}  
```  
  
### <a name="placement"></a>배치  
 다음 위치 중 하나 이상의 정보 표시줄을 표시할 수 있습니다.  
  
-   도구 창  
  
-   문서 탭 내에서  
  
> [!IMPORTANT]
>  전역 컨텍스트에 대 한 메시지를 제공 하는 정보 표시줄 위치를 지정할 것 같습니다. 이 도구 모음과 문서 저장소 간의 나타납니다. "점프 및 jerk" 문제가 발생 하기 때문에 권장 되지는 않습니다 IDE의 하지 않는 한 피해 야 반드시 필요 하 고 적절 한 합니다.  
  
#### <a name="placing-an-infobar-in-a-toolwindowpane"></a>정보 표시줄과 ToolWindowPane에 배치  
 정보 표시줄과 도구 창에 추가할 ToolWindowPane.AddInfoBar(IVsInfoBar) 메서드를 사용할 수 있습니다. 이 API는 IVsInfoBar (어떤 InfoBarModel의 기본 구현은)를 추가 하거나 또는 IVsUIElement 합니다.  
  
#### <a name="placing-an-infobar-in-a-document-or-non-toolwindowpane"></a>정보 표시줄과 문서 또는 비 ToolWindowPane에서 배치  
 정보 표시줄과 모든 한 IVsWindowFrame를 배치 하려면 프레임은 IVsInfoBarHost를 가져오려면 실패 속성을 사용 하 고 UIElement 정보 표시줄을 추가 합니다.  
  
```  
private void AddInfoBar(IVsWindowFrame frame, IVsUIElement uiElement)  
{  
    IVsInfoBarHost infoBarHost;  
    if (TryGetInfoBarHost(frame, out infoBarHost))  
    {  
        infoBarHost.AddInfoBar(uiElement);  
    }  
}  
private bool TryGetInfoBarHost(IVsWindowFrame frame, out IVsInfoBarHost infoBarHost)  
{  
    object infoBarHostObj;  
    if (ErrorHandler.Failed(frame.GetProperty((int)__VSFPROPID7.VSFPROPID_InfoBarHost, out infoBarHostObj)))  
    {  
        infoBarHost = null;  
        return false;  
    }  
  
    infoBarHost = infoBarHostObj as IVsInfoBarHost;  
    return infoBarHost != null;  
}  
  
```  
  
#### <a name="placing-an-infobar-in-the-main-window"></a>정보 표시줄과 주 창에 배치  
 정보 표시줄과 주 창에 배치 하려면 VSSPROPID_MainWindowInfoBarHost IVsShell 서비스를 사용 하 여 주 창의 IVsInfoBarHost 가져올 하 고에 UIElement 정보 표시줄을 추가 합니다.  
  
### <a name="will-i-know-when-the-user-takes-action-in-my-infobar"></a>내 정보 표시줄에는 사용자가 작업 수행 하는 경우를 알 수 있습니까?  
 예,에서는 정보 표시줄 작성자에 게 이벤트 작업을 수행할 때마다 반환 합니다. 다음 정보 표시줄 작성자 정보 표시줄에 사용자 선택에 따라 IDE에서 작업을 수행 하는 합니다. 정보 표시줄 인 닫기 단추가 클릭 되었으며, 호스트에서 자동으로 제거 되지만 추가 작업은 다른 정보 표시줄 제거 해야 후 닫을 경우 필요 합니다. 또한 원격 분석 각 정보 표시줄에서 독립적으로 기록 되도록 할 수 있습니다.  
  
#### <a name="receiving-infobar-events-in-a-toolwindowpane"></a>정보 표시줄 이벤트는 ToolWindowPane에서 수신  
 ToolWindowPane 정보 표시줄에 대 한 두 개의 이벤트에 있습니다. InfoBarClosed 이벤트는 정보는 ToolWindowPane에서 표시줄이 닫힐 때 발생 합니다. InfoBarActionItemClicked 이벤트는 하이퍼링크 또는 단추 정보 표시줄 내부를 클릭할 때 발생 합니다.  
  
#### <a name="receiving-infobar-events-directly-from-the-uielement"></a>UIElement에서 직접 정보 표시줄 이벤트 수신  
 IVsInfoBarUIElement.Advise 정보 표시줄의 UIElement에서 직접 이벤트를 구독할 데 사용할 수 있습니다. IVsInfoBarUIEvents 구현 작성자 닫기 수신 하 고 클릭 이벤트를 허용 합니다.  
  
```  
public interface IVsInfoBarUIEvents  
{  
    void OnActionItemClicked(IVsInfoBarUIElement infoBarUIElement, IVsInfoBarActionItem actionItem);  
    void OnClosed(IVsInfoBarUIElement infoBarUIElement);  
}  
  
```  
  
##  <a name="BKMK_ErrorValidation"></a>유효성 검사 오류  
 필수 필드를 건너뜁니다 같은 또는 잘못 된 형식의 데이터를 입력할 때 허용 되지 않는 정보를 입력 하는 경우 유효성 검사를 사용 하 여 제어 또는 차단 팝업 오류 대화 상자를 사용 하는 대신 컨트롤 근처 피드백 하는 것이 좋습니다.  
  
### <a name="field-validation"></a>필드 유효성 검사  
 세 가지 구성 요소로 이루어져 있습니다 폼 및 필드 유효성 검사: 컨트롤, 아이콘 및 도구 설명 합니다. 여러 유형의 컨트롤을 사용할 수 있지만이 텍스트 상자가 예로 사용 됩니다.  
  
 ![필드 유효성 검사 &#40; 공백 &#41; ] (../../extensibility/ux-guidelines/media/0905-01_fieldvalidation.png "0905 01_FieldValidation")  
  
 필드가 필요한 경우 있어야 않았다는 텍스트가 워터 마크  **\<필요한 >** 필드 배경 light 해야 노란색 (VSColor: `Environment.ControlEditRequiredBackground`) 전경 회색 이어야 하 고 (VSColor: `Environment.ControlEditRequiredHintText`):  
  
 ![유효성 검사 "필수" 레이블이 있는 필드](../../extensibility/ux-guidelines/media/0905-02_fieldvalidationrequired.png "0905 02_FieldValidationRequired")  
  
 컨트롤의 상태 인지 결정할 수 *입력 잘못 된 콘텐츠* 를 다른 컨트롤로 포커스를 이동할 때 또는 사용자 [확인] 커밋 단추를 클릭할 때 또는 사용자는 문서 또는 폼을 저장 하는 경우.  
  
 잘못 된 콘텐츠 상태를 확인할 때 컨트롤 내부 또는 바로 그 옆에 아이콘이 나타납니다. 오류를 설명 하는 도구 설명이 아이콘 또는 컨트롤의 가리킨 항목에 표시 됩니다. 또한 1 픽셀 테두리는 잘못 된 상태를 만드는 컨트롤 주위에 표시 됩니다.  
  
 ![유효성 검사 레이아웃 사양 필드](../../extensibility/ux-guidelines/media/0905-03_layoutspecs.png "0905 03_LayoutSpecs")  
  
 **에 대 한 필드 유효성 검사 레이아웃 사양**  
  
#### <a name="acceptable-variations-for-icon-location"></a>아이콘 위치에 대 한 허용 가능한 변형  
 유효성 검사 오류에 대 한 알림을 받을 사용자 해야 무수 한 고유 경우가 있습니다. 컨트롤 유형과 UI의 구성을 고려 하면 상황에 맞는 배치할 아이콘을 선택 합니다.  
  
 ![아이콘 위치에 대 한 허용 가능한 위치](../../extensibility/ux-guidelines/media/0905-04_iconlocation.png "0905 04_IconLocation")  
  
 **필드 유효성 검사 아이콘 위치에 대 한 허용 가능한 변형**  
  
#### <a name="validation-requiring-a-round-trip-to-a-server-or-network-connection"></a>서버 또는 네트워크 연결으로 라운드트립을 수행 하는 유효성 검사  
 경우에 따라 서버에 왕복 콘텐츠를 확인 하는 데 필요 하 고는 것이 확인 된 사용자 진행 상황 및 오류 상태를 표시 하는 것이 중요 합니다. 아래 그림이이 사례 및 권장 되는 UI의 예를 보여 줍니다.  
  
 ![서버에 왕복과 관련 된 유효성 검사](../../extensibility/ux-guidelines/media/0905-05_roundtrip.png "0905 05_RoundTrip")  
  
 **서버에 왕복과 관련 된 유효성 검사**  
  
 "확인 하는 중..."와 "다시 시도" 텍스트를 수용 하기 위해 컨트롤의 오른쪽에 적절 한 사용 가능한 공간을 제공 해야 하는 참고 합니다.  
  
#### <a name="in-place-warning-text"></a>내부 경고 텍스트  
 오류의 상태에 가깝게 컨트롤 오류 메시지를 저장 하는 사용 가능한 공간이 있으면이 단독 도구 설명을 사용 하 여 보다 선호 됩니다.  
  
 ![&#45; 내부 경고](../../extensibility/ux-guidelines/media/0905-06_inplacewarning.png "0905 06_InPlaceWarning")  
  
 **내부 경고 텍스트**  
  
#### <a name="watermarks"></a>워터 마크  
 경우에 따라 전체 컨트롤 또는 창 오류 상태에서입니다. 이 경우 워터 마크를 사용 하 여 해당 오류를 나타냅니다.  
  
 ![Watermark](../../extensibility/ux-guidelines/media/0905-07_watermark.png "0905-07_Watermark")  
  
 **워터 마크 필드 유효성 검사**