---
title: "알림 및 Visual Studio에 대 한 진행률 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0ef65e9-0f1f-45f4-9f25-6e2398691168
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# 알림 및 Visual Studio에 대 한 진행률
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

##  <a name="a-namebkmknotificationsystemsa-notification-systems"></a><a name="BKMK_NotificationSystems"></a> 알림 시스템  
  
### <a name="overview"></a>개요  
 사용자에 게 소프트웨어 개발 작업에 대 한 Visual Studio에서 일어나는 방법은 여러 가지가 있습니다.  
  
 모든 종류의 알림 구현 하는 경우:  
  
-   **최소한으로 알림 횟수를 유지** 효과적인 수 있습니다. 알림 메시지는 대부분의 Visual Studio 사용자 또는 특정 기능/기능 영역 사용자에 게 적용 해야 합니다. 알림의 과도 하 게 사용 사용자 sidetrack 수도 인식된 시스템의 사용 편의성을 저하 됩니다.  
  
-   **명확 하 고 조치 가능한 메시지를 제공 하려는 경우 확인** 좀 더 복잡 한 선택 및 추가 작업을 수행 하는 것에 대 한 적절 한 컨텍스트를 호출 하는 사용자를 사용할 수 있습니다.  
  
-   **동기 및 비동기 메시지를 적절 하 게 제공 합니다.** 동기 알림을 나타내는 즉각적인 주의가 필요한 웹 서비스가 충돌 하는 경우 또는 코드 같은 예외가 throw 됩니다. 사용자와 같은 모달 대화 상자에는 입력을 필요로 하는 방식 바로 이러한 경우 알려 주어 야 합니다. 비동기 알림은 사용자에 대해 알아야 하지만 필요가 즉시 작동 하도록 웹 사이트 배포를 완료 하는 빌드 작업이 완료 될 때 또는 같은 것입니다. 이러한 메시지 더 앰비언트와 사용자의 작업 흐름이 중단 합니다.  
  
-   **사용자 추가 작업을 수행 하는 것을 금지 하는 데 필요한 경우에 모달 대화 상자를 사용 하 여** 메시지를 승인 하거나 대화 상자에 제공 된 결정을 내리기 전에 합니다.  
  
-   **더 이상 사용할 때 앰비언트 알림을 제거 합니다.** 알릴 된 문제를 해결 하는 작업이 이미 도달한 경우에 알림을 해제 하려면 사용자는 필요 하지 않습니다.  
  
-   **잘못 된 상관 관계 알림이 발생할 수 있음을 유의 합니다.** 사용자가 하나 이상의 작업을 트리거한 알림이 실제로 있었던 인과 관계가 없는 판단할 수도 있습니다. 컨텍스트, 트리거 및 알림 메시지의 소스에 대 한 알림 메시지에 분명 수 있습니다.  
  
### <a name="choosing-the-right-method"></a>적합 한 방법 선택  
 이 표를 사용 하 여 메시지의 사용자에 게 적합 한 방법 선택에 도움을 주고 있습니다.  
  
|메서드|기능|사용 하지 마십시오|  
|------------|---------|----------------|  
|[모달 오류 메시지 대화 상자](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ModalErrorMessageDialogs)|계속 하기 전에 사용자 응답을 요청할 때 사용 됩니다.|사용자를 차단 하 고 해당 흐름을 중단 하지 않아도 없을 때 사용 하지 마십시오. 권장할 만한 방법이 다른 방법으로 메시지를 표시 하는 것이 불가능 한 경우 모달 대화 상자를 사용 하지 마십시오.|  
|[IDE 상태 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_IDEStatusBar)|프로세스의 상태와 관련 된 텍스트 앰비언트 정보가 사용 됩니다.|단독 사용 하지 마십시오. 다른 피드백 메커니즘와 함께에서 가장 적합합니다.|  
|[포함 된 정보 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_EmbeddedInfobar)|도구 창과 문서 창에서 진행 중, 오류 상태, 결과 및/또는 동작 가능한 정보에 알리기 위해 사용 합니다.|정보 표시줄을 배치할 위치와 관련이 없는 경우 사용 하지 마십시오.<br /><br /> 문서/도구 창 밖에 사용 하지 마십시오.|  
|[마우스 커서가 변경](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_MouseCursorChanges)|프로세스가 진행 되 게 사용할 수 있습니다. 또한 마우스 커서가 그리기 모드와 같은 특정 모드에서 끌어서 놓기 또는 진행 중인 경우와 같은 마우스의 상태 변경 알림 하는 데 사용 합니다.|짧은 진행 중인 변경 내용에 대해 사용 하지 않거나 경우의 펄럭이는 커서 가능성이 높습니다 (예를 들어 경우에 전체 프로세스 대신 오래 실행 중인 프로세스의 부분에 연관 됨).|  
|[진행률 표시기](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_NotSysProgressIndicators)|(비활성화 상태 또는 결정 되지 않은) 진행률을 보고 해야 하는 경우 사용 합니다. 진행률 표시기 유형이 및 각각에 대 한 특정 사용의 여러 가지가 있습니다. 참조 [진행률 표시기](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ProgressIndicators)합니다.||  
|[Visual Studio 알림 창](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_VSNotificationsToolWindow)|알림 창을 공개적으로 확장할 수는 없습니다. 그러나 다양 한 라이선스와 Visual Studio로 또는 패키지에 업데이트의 정보 알림 중요 한 문제를 포함 하 여 Visual Studio에 대 한 메시지를 통신에 사용 됩니다.|다른 유형의 알림 사용 하지 마십시오.|  
|[오류 목록](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ErrorList)|문제와 문제가 (오류/경고/정보) 사용자의 현재 열려 있는 솔루션에 직접 관련 되어 있는 경우 코드에 대해 작업을 수행 해야 합니다.<br /><br /> 이 예를 포함 합니다.<br /><br /> -컴파일러 메시지 (오류/경고/정보)<br /><br /> 코드에 대 한 코드 분석/진단 메시지<br /><br /> -메시지를 작성 합니다.<br /><br /> 프로젝트 또는 솔루션 파일에 관련 된 문제에 대 한 적절 한 수 있지만 먼저 솔루션 탐색기 표시를 고려 합니다.|사용자의 열려 있는 솔루션 코드에는 관계를 갖지 않는 항목에 대 한 사용 하지 마십시오.|  
|편집기 알림: 전구|열려 있는 파일에 존재 하는 문제를 해결할 수 있는 문제를 해결 해야 하는 경우 사용 합니다.<br /><br /> 전구는 또한 호스팅, 리팩터링 등 필요에 따라 사용자의 코드에서 수행 되 있지만 경우 "알림 스타일입니다."를 표시 되지 것입니다 있는 빠른 작업에 대 한 사용 가능|열린 파일에 모든 관계를 갖지 않는 항목에 대 한 사용 하지 마십시오.|  
|편집기 알림: 오류 표시선|사용자가 열려 있는 코드 (예를 들어 빨간색 오류 표시선 오류에 대 한)의 범위를 특정 문제를 경고를 사용 합니다.|가 열려 있는 코드의 범위를 특정 하는 항목에 대 한 사용 하지 마십시오.|  
|[포함 된 상태 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_EmbeddedStatusBars)|사용 하 여 콘텐츠 또는 특정 도구 창, 문서 창 또는 대화 상자 창을의 컨텍스트 내에서 프로세스와 관련 된 상태를 제공 합니다.|일반적인 제품 알림, 프로세스 또는 특정 창 내에서 콘텐츠를 모든 관계를 갖지 않는 항목에 대 한 사용 하지 마십시오.|  
|[Windows 트레이 알림](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_WindowsTray)|프로세싱 아웃 프로세스에 대 한 알림 화면 또는 응용 프로그램 도우미를 사용 합니다.|IDE에 관련 된 알림을 사용 하지 마십시오.|  
|[알림 풍선](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_NotificationBubbles)|원격 프로세스의 알리거나 변경할를 사용 하 여 **외부** ide입니다.|프로세스의 사용자에 게 알리기 위해 하는 수단으로 사용 하지 않는 **내** IDE입니다.|  
  
### <a name="notification-methods"></a>알림 방법  
  
####  <a name="a-namebkmkmodalerrormessagedialogsa-modal-error-message-dialogs"></a><a name="BKMK_ModalErrorMessageDialogs"></a> 모달 오류 메시지 대화 상자  
 모달 오류 메시지 대화 상자는 사용자의 확인 또는 동작을 필요로 하는 오류 메시지를 표시 하는 데 사용 됩니다.  
  
 ![모달 오류 메시지](../../extensibility/ux-guidelines/media/0901-01_modalerrormessage.png "0901-01_ModalErrorMessage")  
  
 **데이터베이스에 잘못 된 연결 문자열의 사용자에 게 알리는 모달 오류 메시지 대화 상자**  
  
####  <a name="a-namebkmkidestatusbara-ide-status-bar"></a><a name="BKMK_IDEStatusBar"></a> IDE 상태 표시줄  
 사용자가 상태 표시줄 텍스트를 확인 하는 가능성 다방면 컴퓨터 환경 및 특정 환경과 Windows 플랫폼을 상호 연결 합니다. Visual Studio 고객 기반 경향이 두 영역에서 숙련 된 경우에 잘 알고 있는 Windows 사용자 상태 표시줄에 변경 내용을 놓칠 수입니다. 따라서 상태 표시줄은 적합 중복 큐 또는 정보 제공의 목적 정보가 다른 곳에서 소개 합니다. 알림 도구 창 또는 대화 상자에서 모든 종류의 사용자를 즉시 해결 해야 하는 중요 한 정보를 제공 합니다.  
  
 Visual Studio 상태 표시줄은 여러 유형의 정보 표시 될 수 있도록 설계 되었습니다. 피드백, 디자이너, 진행률 표시줄, 애니메이션 및 클라이언트에 대 한 영역 나뉩니다.  
  
 피드백 지역 및 디자이너 영역 항상 표시 됩니다. 진행률 표시줄 및 애니메이션 지역은 항상 동적이 고 사용자 컨텍스트를 기반으로 합니다. 디자이너 영역에 정적 폭 문자 메시지에 대 한 관련 리소스에서 가져온 문자열의 길이 의해 결정 됩니다. 따라서 지역화를 코드 변경 하지 않고도 너비를 조정할 수 있습니다. 영어의 경우이 문자열의 너비는 약 220 픽셀. 디자이너 영역 정상적으로 동작 합니다 및 피드백 지역 나머지 공간을 처리 합니다.  
  
 상태 표시줄은 또한 색으로 표시 IDE이 디버그 모드에 있을 때와 같은 다양 한 IDE 상태 변경 내용을 통신 하 여 시각적 효과 기능 값을 추가 합니다.  
  
 ![IDE 상태 표시줄 색 변경](../../extensibility/ux-guidelines/media/0901-02_idestatusbar.png "0901-02_IDEStatusBar")  
  
 **IDE 상태 표시줄 색상**  
  
####  <a name="a-namebkmkembeddedinfobara-embedded-infobar"></a><a name="BKMK_EmbeddedInfobar"></a> 포함 된 정보 표시줄  
 정보 표시줄 문서 창이 나 도구 창 맨 위에 있는 상태 또는 조건 사용자에 게 알리는 데 사용할 수 있습니다. 또한 사용자는 쉽게 작업을 수행 하는 방법을 유지할 수 있습니다. 있도록 명령을 제공할 수 있습니다. 정보 표시줄 표준 셸 컨트롤입니다. 작동 되며 IDE에서 다른 사용자와 일치 하지 않는 표시는 직접 작성 하지 마십시오. 참조 [정보 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars) 구현 세부 정보 및 사용 지침에 대 한 합니다.  
  
 ![포함된 정보 표시줄](../../extensibility/ux-guidelines/media/0901-03_embeddedinfobar.png "0901-03_EmbeddedInfobar")  
  
 **IDE 기록 디버깅 모드에 있고 표준 디버깅 모드에서와 마찬가지로 편집기는 동일한 방식으로 응답 하지 않습니다 사용자에 게 알리는 문서 창에 포함 된 정보 표시줄입니다.**  
  
####  <a name="a-namebkmkmousecursorchangesa-mouse-cursor-changes"></a><a name="BKMK_MouseCursorChanges"></a> 마우스 커서가 변경  
 마우스 커서를 변경할 때는 VSColor 서비스에 연결 되 고 이미 커서와 연결 되어 있는 색을 사용 합니다. 커서 변경 사항은 진행 중인 작업을 나타내는 데 사용할 수 뿐만 아니라 영역 수을 끌어다 놓을 끌거나 개체를 선택 하는 데 사용 하는 대상 사용자가 마우스로 적중 합니다.  
  
 더 이상 모든 입력을 표현 하기 때문에 사용자 작업에 대 한 모든 사용 가능한 CPU 시간을 예약 해야 하는 경우에 사용 중/대기 마우스 커서를 사용 합니다. 다중 스레딩을 사용 하는 잘 작성 된 응용 프로그램과 함께 대부분의 경우에서 시간 때 수 없는 사용자에서 다른 작업을 수행 하는 거의 발생 하지 않아야 합니다.  
  
 정보에 대 한 중복 큐 다른 곳에서 제공 하는 대로 커서가 변경 유용 하다는 것을 염두에 두십시오. 사용자 해결 해야 하는 중요 한 것을 전달 하려고 하는 경우에 특히 사용자와의 통신의 유일한 방법으로 커서 변경에 의존 하지 마십시오.  
  
####  <a name="a-namebkmknotsysprogressindicatorsa-progress-indicators"></a><a name="BKMK_NotSysProgressIndicators"></a> 진행률 표시기  
 진행률 표시기는 프로세스를 완료 하는 몇 초를 사용 하는 동안 사용자에 게 피드백을 제공 하는 것에 대 한 중요 합니다. 진행률 표시기를 표시 될 수 있습니다 내부 (근처의 시작 지점 진행 중인 작업의), 포함 된 상태 표시줄, 모달 대화 상자에서 또는 Visual Studio 상태 표시줄입니다. 지침에 따라 [진행률 표시기](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ProgressIndicators) 대가 사용 하 고 구현 합니다.  
  
####  <a name="a-namebkmkvsnotificationstoolwindowa-visual-studio-notifications-window"></a><a name="BKMK_VSNotificationsToolWindow"></a> Visual Studio 알림 창  
 Visual Studio 알림 창에 라이선스, 환경 (Visual Studio), 확장 및 업데이트 하는 방법에 대 한 개발자를 게 알립니다. 사용자는 개별 알림을 해제할 수 또는 특정 종류의 알림 무시 하도록 선택할 수 있습니다. 무시 알림 목록에서 관리 되는 **도구 > 옵션** 페이지입니다.  
  
 알림 창을 현재 확장할 수는 없습니다.  
  
 ![Visual Studio 알림 창](../../extensibility/ux-guidelines/media/0901-06_vsnotificationswindow.png "0901-06_VSNotificationsWindow")  
  
 **Visual Studio 알림 도구 창**  
  
####  <a name="a-namebkmkerrorlista-error-list"></a><a name="BKMK_ErrorList"></a> 오류 목록  
 오류 목록에서 알림을 컴파일하는 동안 발생 및 or 빌드 프로세스와 특정 코드 오류에 해당 하는 코드를 탐색할 수 있도록 하는 오류 및 경고를 나타냅니다.  
  
 ![오류 목록](../../extensibility/ux-guidelines/media/0901-08_errorlist.png "0901-08_ErrorList")  
  
 **Visual Studio의 오류 목록**  
  
####  <a name="a-namebkmkembeddedstatusbarsa-embedded-status-bars"></a><a name="BKMK_EmbeddedStatusBars"></a> 포함 된 상태 표시줄  
 IDE 상태 표시줄에는 현재 문서 창 및 시스템 응답 및/또는 사용자의 컨텍스트를 업데이트 하는 정보를 설정 하는 클라이언트 지역 컨텍스트와 동적, 정보의 연속 표시를 유지 관리 하거나 장기 비동기 프로세스에 상태를 제공 하려면 어렵습니다. 예를 들어, IDE 상태 표시줄에 대 한 테스트 실행 결과 여러 실행 및/또는 즉시 실행 가능한 항목이 선택 항목에 대 한 알림을 적합 하지 않습니다. 사용자가 항목을 선택 하거나 프로세스를 시작 있는 문서 또는 도구 창 컨텍스트에서 이러한 상태 정보를 유지 하는 것이 반드시 합니다.  
  
 ![포함된 상태 표시줄](../../extensibility/ux-guidelines/media/0901-09_embeddedstatusbar.png "0901-09_EmbeddedStatusBar")  
  
 **Visual Studio에 포함 된 상태 표시줄**  
  
####  <a name="a-namebkmkwindowstraya-windows-tray-notifications"></a><a name="BKMK_WindowsTray"></a> Windows 트레이 알림  
 Windows 작업 표시줄 알림 영역은 시스템 옆에 있는 Windows 클록 합니다. 대부분의 유틸리티와 소프트웨어 구성 요소 사용자 화면 해상도 변경 하거나 소프트웨어 업데이트를 가져오는 등의 시스템 수준 작업에 대 한 상황에 맞는 메뉴를 얻을 수 있도록이 영역에 있는 아이콘을 제공 합니다.  
  
 환경 수준 알림은 Visual Studio 알림 허브 Windows 알림 영역에에서 표시 해야 합니다.  
  
####  <a name="a-namebkmknotificationbubblesa-notification-bubbles"></a><a name="BKMK_NotificationBubbles"></a> 알림 풍선  
 정보는 편집기/디자이너 내에서 또는 Windows 알림 영역의 일부로 알림 풍선 나타날 수 있습니다. 사용자에 게 이러한 거품 나중에 확인할 수 있는 문제는 중요 하지 않은 알림에 유용 합니다. 거품은 사용자를 즉시 해결 해야 하는 중요 한 정보에 대 한 적합 하지 않습니다. 알림 풍선을 사용 하 여 Visual Studio에서 수행을 하는 경우에 따라는 [알림 풍선에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742472\(v=vs.85\).aspx)합니다.  
  
 ![알림 거품형](../../extensibility/ux-guidelines/media/0901-07_notificationbubbles.png "0901-07_NotificationBubbles")  
  
 **Visual Studio에 사용 되는 Windows 알림 영역에서 알림 거품형**  
  
##  <a name="a-namebkmkprogressindicatorsa-progress-indicators"></a><a name="BKMK_ProgressIndicators"></a> 진행률 표시기  
  
### <a name="overview"></a>개요  
 진행률 표시기는 사용자에 게 피드백을 제공 하는 것에 대 한 알림 시스템의 중요 한 부분입니다. 이러한 프로세스와 작업 완료 되 면 사용자에 게 알려줍니다. 친숙 한 표시기에 진행률 표시줄, 회전 커서 및 애니메이션된 아이콘입니다. 유형 및 진행률 표시기를 배치를 완료 하는 데 걸리는 보고 내용을 포함 하는 컨텍스트를 얼마나 프로세스와 작업에 따라 다릅니다.  
  
#### <a name="factors"></a>요소  
 어떤 표시기 형식이 적절 한가 확인 하기 위해서는 다음과 같은 요소를 결정 해야 합니다.  
  
1.  **타이밍:** 기간 동안 작업 걸립니다  
  
2.  **형식:** 작업 환경 (잠금 프로세스가 완료 될 때까지 UI)에 모달 인지 여부  
  
3.  **영구/일시적:** 진행률의 최종 결과 나중에 보고 된 및/또는 볼 수 있는 수 해야 하는지 여부  
  
4.  **활성화 상태의 / 미 확정:** 작업 종료 시간 및 진행률을 계산할 수 있는지 여부  
  
5.  **그래픽/Textual 위치:** 진행 상황이 나 프로세스 인지는 메시지 또는 특정 컨트롤의 트리 컨트롤 등의 본문에 캡처된 인라인  
  
6.  **근사:** 진행률 UI와는 관련이 있는 인접에서 여야 하는지 여부입니다. (예를 들어 멀리 떨어져 될 수 있는 상태 표시줄에 사용할 수 또는 프로세스를 시작 하는 단추의 근처에 있을 수도 있습니까)?  
  
#### <a name="determinate-progress"></a>활성화 상태의 진행률  
  
|진행률 유형|시기 및 사용 하는 방법|노트|  
|-------------------|-------------------------|-----------|  
|진행률 표시줄 (비활성화)|예상 기간 > 5 초입니다.<br /><br /> 프로세스 세부 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.|**하지** 애니메이션에 텍스트를 포함 합니다.|  
|정보 표시줄|상황에 맞는 UI와 연결 된 메시징입니다. 참조 [정보 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars)합니다.<br /><br /> 프로세스 세부 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.|**하지** 여러 프로세스를 표시 해야 할 때 여러 정보 표시줄을 사용 합니다. 누적된 진행률 표시줄을 대신 사용 합니다.|  
|출력 창|일시적인 알림: 해당 사용자가 해야 할 응용 프로그램 수준 프로세스 **검토** 완료 된 후의 세부 정보입니다.|**하지** 는 사용자가 나중에 데이터를 참조 해야 하는 경우 사용 합니다.|  
|로그 파일|이를 중요 한 경우에서 intransient 알림 쌍을 이루는 **저장** 완료 한 후 세부 정보입니다.||  
|상태 표시줄|일시적인 알림: 응용 프로그램 수준 프로세스는 사용자에 게 **필요는 없습니다** 완료 된 후의 세부 정보입니다.<br /><br /> 포함 된 진행률 표시줄을 포함합니다.<br /><br /> 프로세스 세부 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.||  
  
#### <a name="indeterminate-progress"></a>비활성화 상태의 진행률  
  
|진행률 유형|시기 및 사용 하는 방법|노트|  
|-------------------|-------------------------|-----------|  
|진행률 표시줄 (비활성화)|예상 기간 > 5 초입니다.<br /><br /> 프로세스 세부 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.|**하지** 애니메이션에 텍스트를 포함 합니다.|  
|Ants (가로 점에 애니메이션된)|서버에 왕복 합니다.<br /><br /> 부모 컨테이너의 위쪽 near 지점의 컨텍스트를 배치합니다.|**하지** 하지 전체 컨테이너에 의해 부모로 지정 하는 경우 사용 합니다.|  
|스핀 상자 (진행률 링)|프로세스 또는와 관련 된 상황별 UI 공간 고려 사항입니다.<br /><br /> 프로세스 세부 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.||  
|정보 표시줄|상황에 맞는 UI와 연결 된 메시징입니다. 참조 [정보 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars)합니다.|**하지** 여러 프로세스를 표시 해야 할 때 여러 정보 표시줄을 사용 합니다. 누적된 진행률 표시줄을 대신 사용 합니다.|  
|출력 창|일시적인 알림: 응용 프로그램 수준 프로세스는 사용자는 하려면 **검토** 완료 된 후의 세부 정보입니다.|**하지** 세션 간에 유지 하는 정보를 사용 합니다.|  
|로그 파일|이를 중요 한 경우에서 intransient 알림 쌍을 이루는 **저장** 완료 한 후 세부 정보입니다.||  
|상태 표시줄|일시적인 알림: 응용 프로그램 수준 프로세스는 사용자에 게 **필요는 없습니다** 완료 된 후의 세부 정보입니다.<br /><br /> 포함 된 진행률 표시줄을 포함합니다.<br /><br /> 프로세스 세부 정보에 대 한 텍스트 설명을 포함 될 수 있습니다.||  
  
### <a name="progress-indicator-types"></a>진행률 표시기 유형이  
  
#### <a name="progress-bars"></a>진행률 표시줄  
  
##### <a name="indeterminate"></a>비활성화 상태  
 ![비활성화 상태의 진행률 표시줄](../../extensibility/ux-guidelines/media/0901-04_indeterminate.png "0901-04_Indeterminate")  
  
 **비활성화 상태의 진행률 표시줄**  
  
 "비활성화"는 작업의 전반적인 진행 상황을 의미 하거나 프로세스를 확인할 수 없습니다. 바인딩되지 않은 기간을 필요로 하는 작업에 대 한 비활성화 상태의 진행률 표시줄을 사용 하 여 또는 알 수 없는 개체 수를 액세스 하는 합니다. 대 한 텍스트 설명을 사용 하 여 일어나는 함께 제공 합니다. 경계 시간 기반 작업에 부여할 시간 제한을 사용 합니다. 비활성화 상태의 진행률 표시줄 표시 진행 상황을 않지만 없는 다른 정보를 제공 하 여 애니메이션을 사용 합니다. 가능한 정확도 만으로는 부족 기반 부정형 진행률 표시줄을 선택 하지 마십시오.  
  
##### <a name="determinate"></a>비활성화 상태  
 ![활성화 상태의 진행률 표시줄](../../extensibility/ux-guidelines/media/0901-05_determinate.png "0901-05_Determinate")  
  
 **활성화 상태의 진행률 표시줄**  
  
 "비활성화" 있어도 제한 된 기간 동안에는 작업 또는 프로세스에 필요 시간을 정확 하 게 예측할 수 없습니다. 완료를 명확히 표시 합니다. 작업이 완료 된 경우가 아니면 100%로 이동 하는 동안 진행률 표시줄이 하지 말고 합니다. 활성화 상태의 진행률 표시줄 애니메이션 0에서 100% 왼쪽에서 오른쪽 이동합니다.  
  
 작업 하는 동안 이전 버전과 진행률 표시기를 이동 하지 않습니다. 막대 앞으로 이동 꾸준히는 작업이 시작 되 고 끝날 때 100%에 도달 해야 합니다. 진행률 표시줄의 핵심은 이해 전체 작업 하는 걸리는 시간, 관련 된 단계 수에 관계 없이 사용자에 게 제공 합니다.  
  
##### <a name="concurrent-reporting-stacked-progress-bars"></a>동시 (누적된 진행률 표시줄)를 보고 합니다.  
 작업에 시간이 오래 걸립니다 경우 몇 분-다음 두 가지 진행률 표시줄을 사용할 있습니다 아마도 하나 소개 하는 작업에 대 한 전반적인 진행률 및 현재 단계의 진행에 대 한 다른입니다. 예를 들어 설치 프로그램은 많은 파일을 복사 하는 경우 하나의 진행률 표시줄 걸리는 시간을 전체 프로세스는 두 번째 현재 파일의 비율을 나타낼 수 또는 디렉터리를 복사 하는 동안 동안 나타내기 위해 사용 수 있습니다. 5 개 이상의 동시 작업 또는 누적된 진행률 표시줄을 사용 하 여 프로세스를 보고 하지 않습니다. 5 개 이상의 동시 작업 또는 보고서에 대 한 프로세스를 설정한 경우 모달 대화 상자는 취소 단추 및 사용 보고서 출력 창에 진행률 세부 정보.  
  
##### <a name="textual-descriptions"></a>텍스트 설명  
 상황에 대 한 텍스트 설명을 완료 될 때까지 예상된 시간을 사용 합니다. 시간 걸릴 것을 알 수 없는 경우 진행률 표시줄 보다는 애니메이션된 아이콘 피드백 제공에 보다 적합할 수 있습니다.  
  
 Visual Studio는 Visual Studio에 통합 하는 모든 제품에서 사용할 수 있는 상태 표시줄에 표준 진행률 표시줄을 제공 합니다. 진행률 표시줄은 애니메이션이 적용 하는 동안 상황의 텍스트 설명에 대 한 상태 표시줄 텍스트를 업데이트할 수 있습니다.  
  
#### <a name="other-progress-indicators"></a>다른 진행률 표시기  
  
##### <a name="ants-animated-horizontal-dots"></a>Ants (가로 점에 애니메이션된)  
 ![진행률 ants](../../extensibility/ux-guidelines/media/0903-01_ants.png "0903-01_Ants")  
  
 "개미" 가로 점에 애니메이션된을 결정할 수 없는 왕복 서버 프로세스에 대 한는 시각적 참조 자료를 제공 합니다.  
  
##### <a name="spinner-progress-ring"></a>스핀 상자 (진행률 링)  
 ![진행률 회전자](../../extensibility/ux-guidelines/media/0903-02_spinner.png "0903-02_Spinner")  
  
 스핀 상자 ("진행률 링" 라고도 함)에 주로 사용 되는 상황에 맞는 UI와 관련 하 여 부정형 진행률 표시기입니다. 회전자 인접 텍스트 범주 헤더, 메시징, 또는 컨트롤 등의 관련된 콘텐츠를 표시 합니다.  
  
##### <a name="cursor-feedback"></a>커서 피드백  
 2 ~ 7 초 사이 하는 작업에 대 한 커서 피드백을 제공 합니다. 일반적으로이 운영 체제에서 제공 하는 대기 커서를 사용 하 여 의미 합니다. 지침에 대 한 MSDN 문서를 참조 [Cursors.Wait 속성](https://msdn.microsoft.com/en-us/library/system.windows.input.cursors.wait\(v=vs.110\).aspx)합니다.  
  
#### <a name="progress-indicator-locations"></a>진행률 표시기 위치  
  
##### <a name="status-bar"></a>상태 표시줄  
 상태 표시줄을 통해 응용 프로그램 사용자의 작업을 중단 하지 않고 사용자에 게 메시지와 유용한 정보를 표시할 수 있는 곳입니다. 진행률에 대 한 상태는 일반적으로 창 맨 아래에 표시를 진행률 표시줄 표시기와 함께에서 진행률을 측정 하는 방법에 대 한 메시지를 포함 하는 도구 팁 창 수 있습니다.  
  
 ![진행률 표시줄을 사용하는 상태 표시줄](../../extensibility/ux-guidelines/media/0903-03_statusbarprogressbar.png "0903-03_StatusBarProgressBar")  
  
 **진행률 표시줄 상태 표시줄**  
  
 ![메시징을 사용하는 상태 표시줄](../../extensibility/ux-guidelines/media/0903-04_statusbarmessage.png "0903-04_StatusBarMessage")  
  
 **상태 표시줄 텍스트 설명으로**  
  
##### <a name="infobar"></a>정보 표시줄  
 상태 표시줄 정보 표시줄와 비슷하지만 제공 하 상황에 맞는 알림 및 메시징에 진행률 표시줄이 나 스핀 상자와 같은 부정형 진행률 표시기와도 연결할 수 있습니다. 정보 표시줄 세부적인 수준의 진행률 또는 활성화 상태의 진행률 표시를 제공 하지 않아야 합니다. 참조 [정보 표시줄](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars)합니다.  
  
 ![진행률 표시줄 및 메시징을 사용하는 정보 표시줄](../../extensibility/ux-guidelines/media/0903-05_infobar.png "0903-05_InfoBar")  
  
 **진행률 표시줄 및 텍스트 설명을 포함 된 정보 표시줄**  
  
 ![창 내의 정보 표시줄](../../extensibility/ux-guidelines/media/0903-06_infobarinwindow.png "0903-06_InfoBarInWindow")  
  
 **코드 분석 창 내의 정보 표시줄**  
  
##### <a name="inline"></a>인라인  
 인라인 진행률 표시 진행률 로더 형식으로 나타낼 수 있습니다. 일반적으로 진행률 표시기는 쌍을 이루는 메시징, 있지만 반드시 그럴 필요는 없습니다.  
  
 ![인라인 진행률 회전자](../../extensibility/ux-guidelines/media/0903-07_inlinespinner.png "0903-07_InlineSpinner")  
  
 **회전자 결합 된 텍스트 설명**  
  
 ![인라인 누적 진행률 표시줄](../../extensibility/ux-guidelines/media/0903-08_inlinestackedprogress.png "0903-08_InlineStackedProgress")  
  
 **활성화 상태의 누적된 진행률 표시줄**  
  
 ![인라인 진행률 메시징](../../extensibility/ux-guidelines/media/0903-09_inlinetext.png "0903-09_InlineText")  
  
 **서버 탐색기 인라인 텍스트: 새로 고침 중...**  
  
##### <a name="tool-windows"></a>도구 창  
 전역 진행률 표시 도구 모음 바로 아래에 배치 하는 부정형 진행률 표시줄이 표시 됩니다.  
  
 ![전역 비활성화 상태의 진행률 표시줄](../../extensibility/ux-guidelines/media/0903-23_globalindeterminate.png "0903-23_GlobalIndeterminate")  
  
 **팀 탐색기 전역 비활성화 상태의 진행률 표시줄**  
  
##### <a name="dialogs"></a>대화 상자  
 대화 상자에 진행률 로더 유형이 포함 될 수 있습니다. 진행률 표시기 수 메시징 쌍을 이루는 뿐만 수 여러 수준의 세부적인 나타내며, 하위 프로세스 진행률 표시와 결합 합니다.  
  
 ![여러 진행률 표시기 유형이 있는 대화 상자](../../extensibility/ux-guidelines/media/0903-11_dialog.png "0903-11_Dialog")  
  
 **동시 프로세스 및 여러 진행률 표시기 유형이 있는 visual Studio 대화 상자**  
  
 ![진행률 로더 및 메시징이 있는 대화 상자](../../extensibility/ux-guidelines/media/0903-12_dialog2.png "0903-12_Dialog2")  
  
 **진행률 로더 및 메시징 인라인 명령으로 visual Studio 대화 상자**  
  
##### <a name="document-well"></a>잘 문서화  
 잘 문서 컨트롤과 조합 하 여 여러 진행률 로더 유형을 표시할 수 있습니다.  
  
 ![문서의 진행률 메시징](../../extensibility/ux-guidelines/media/0903-13_documentwell.png "0903-13_DocumentWell")  
  
 **도구 모음 아래 비활성화 상태의 진행률 표시줄**  
  
##### <a name="output-window"></a>출력 창  
 출력 창은 프로세스 진행 및 인라인 텍스트 메시징을 통해 진행 상태를 처리 하기 위한 적합 합니다. 모든 출력 창의 진행률 보고와 함께 상태 표시줄을 사용 해야 합니다.  
  
 ![출력 창의 진행률 메시징](../../extensibility/ux-guidelines/media/0903-14_outputwindow.png "0903-14_OutputWindow")  
  
 **지속적인 프로세스 상태와 함께 출력 창 및 메시징 대기**  
  
##  <a name="a-namebkmkinfobarsa-infobars"></a><a name="BKMK_Infobars"></a> 정보 표시줄  
  
### <a name="overview"></a>개요  
 정보 표시줄 관심 지점에 가까운 표시기 사용자를 지정 하 고 시각적 모양과 상호 작용의 일관성을 유지 공유 정보 표시줄 컨트롤을 사용 하 여 키를 누릅니다.  
  
 ![정보 표시줄](../../extensibility/ux-guidelines/media/0904-01_infobar.png "0904-01_Infobar")  
  
 **Visual Studio에서 정보 표시줄**  
  
#### <a name="appropriate-uses-for-an-infobar"></a>정보 표시줄에 대 한 적절 한 사용  
  
-   현재 컨텍스트와 관련 된 비 중단 하지만 중요 한 메시지를 사용자에 게 부여 하려면  
  
-   기록 디버깅과 같은 일부 상호 작용 의미를 전달 하는 UI 특정 상태 또는 조건 임을 나타내기 위해  
  
-   시스템이 확장은 성능 문제를 일으킬 때 같은 문제를 검색을 사용자에 게  
  
-   사용자를 쉽게 편집기 탭 및 공백이 파일에 혼합 있는지 감지 했을 때 등의 작업을 사용 하는 방법을 제공 하기  
  
##### <a name="do"></a>수행 합니다.  
  
-   간단히 말해 더 간결 하 고 정보 표시줄 메시지 텍스트를 유지 합니다.  
  
-   간결한 링크 및 단추에 텍스트를 유지 합니다.  
  
-   사용자에 게 제공 하는 "action" 옵션 최소 필수 작업에만 표시 되도록 합니다.  
  
##### <a name="dont"></a>안 함:  
  
-   도구 모음에 배치 해야 하는 표준 명령을 제공 하는 정보 표시줄을 사용 합니다.  
  
-   모달 대화 상자 대신 정보 표시줄을 사용 합니다.  
  
-   창 밖에 부동 메시지를 만듭니다.  
  
-   같은 창 내에서 여러 위치에서 여러 정보 표시줄을 사용 합니다.  
  
#### <a name="can-multiple-infobars-show-at-the-same-time"></a>여러 정보 표시줄 동시에 표시할 수 있습니다.  
 예, 여러 정보 표시줄은 동시에 표시할 수 있습니다. 첫 번째 정보 표시줄 아래 표시 된 위쪽 및 추가 정보 표시줄에 표시 된 대로, 처음 들어간 것부터 순서 대로 표시 됩니다.  
  
 사용자가 한 번에 최대 세 개의 정보 표시줄을 표시 한 후, 자세한 정보 표시줄을 사용할 수 있으므로 정보 표시줄 지역 됩니다 스크롤할 수 있는 합니다.  
  
### <a name="creating-an-infobar"></a>정보 표시줄 만들기  
 정보 표시줄에 왼쪽에서 오른쪽의 4 개의 섹션이 있습니다.  
  
-   **아이콘:** 이 모든 아이콘을 추가할 위치에 대 한 경고 아이콘 같은 정보 표시줄을 표시 하려고 합니다.  
  
-   **텍스트:** 필요한 경우 텍스트에 있는 링크와 함께,에서 시나리오/상황 사용자를 설명 하는 텍스트를 추가할 수 있습니다. 텍스트를 간결 유지 해야 합니다.  
  
-   **작업의 경우:** 링크 및 단추는 사용자 프로그램 정보 표시줄에 수행할 수 있는 작업에 대 한이 섹션을 포함 해야 합니다.  
  
-   **닫기 단추:** 오른쪽 마지막 섹션 닫기 단추를 가질 수 있습니다.  
  
#### <a name="creating-a-standard-infobar-in-managed-code"></a>관리 코드에서 표준 정보 표시줄 만들기  
 InfoBarModel 클래스는 정보 표시줄에 대 한 데이터 소스를 만드는 데 사용할 수 있습니다. 이러한 네 가지 생성자 중 하나를 사용 합니다.  
  
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
  
 하이퍼링크, 단추, 아이콘와 일부 텍스트는 InfoBarModel를 만드는 예제는 다음과 같습니다.  
  
 ![하이퍼링크가 포함된 정보 표시줄](../../extensibility/ux-guidelines/media/0904-02_infobarhyperlink.png "0904-02_InfobarHyperlink")  
  
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
  
#### <a name="creating-a-standard-infobar-in-native-code"></a>네이티브 코드의 표준 정보 표시줄 만들기  
 네이티브 코드에서 정보 표시줄을 제공 하기 위해 The IVsInfoBar 인터페이스를 구현 합니다.  
  
```  
public interface IVsInfoBar  
{  
    IVsInfoBarActionItemCollection ActionItems { get; }  
    ImageMoniker Image { get; }  
    bool IsCloseButtonVisible { get; }  
    IVsInfoBarTextSpanCollection TextSpans { get; }  
}  
  
```  
  
#### <a name="getting-an-infobar-uielement-from-an-infobar"></a>정보 표시줄에서 UIElement 정보 표시줄이 가져오기  
 InfoBarModel 또는 IVsInfoBar 구현에는 UI에 표시 하기 위해 UIElement로 설정 해야 하는 데이터 모델입니다. UIElement은 SVsInfoBarUIFactory/IVsInfoBarUIFactory 서비스를 검색할 수 있습니다.  
  
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
>  전역 컨텍스트에 대 한 메시지를 제공 하는 정보 표시줄을 배치 하는 것이 불가능 합니다. 이 도구 모음과 잘 문서 간에 나타납니다. "점프 및 jerk" 문제가 발생 하기 때문에 권장 되지 않습니다 IDE의 하지 않는 한 피해 야 절대적으로 필요 하 고 적절 한 합니다.  
  
#### <a name="placing-an-infobar-in-a-toolwindowpane"></a>ToolWindowPane에 배치 하는 정보 표시줄  
 도구 창에는 정보 표시줄을 추가 하려면 ToolWindowPane.AddInfoBar(IVsInfoBar) 메서드를 사용할 수 있습니다. 이 API는 IVsInfoBar (어떤 InfoBarModel은 기본 구현)를 추가 하거나 또는 IVsUIElement 합니다.  
  
#### <a name="placing-an-infobar-in-a-document-or-non-toolwindowpane"></a>문서 또는 비 ToolWindowPane에 배치 하는 정보 표시줄  
 정보 표시줄 모든 한 IVsWindowFrame를 배치 하려면 프레임의 IVsInfoBarHost를 가져오려면 VSFPROPID_InfoBarHost 속성을 사용 하 고 정보 표시줄 ui 요소를 추가 합니다.  
  
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
  
#### <a name="placing-an-infobar-in-the-main-window"></a>주 창에 배치 하는 정보 표시줄  
 주 창에는 정보 표시줄에 배치 하려면 VSSPROPID_MainWindowInfoBarHost IVsShell 서비스의 주 창 IVsInfoBarHost를 사용 하 고를 UIElement 정보 표시줄을 추가 합니다.  
  
### <a name="will-i-know-when-the-user-takes-action-in-my-infobar"></a>내 정보 표시줄에는 사용자가 작업 수행 하는 경우를 알 수 있습니까?  
 예,에서는 정보 표시줄 작성자에 게 이벤트 작업을 수행할 때마다 반환 합니다. 다음 정보 표시줄에 사용자 선택에 따라 IDE에서 작업을 하는 정보 표시줄 작성자는 합니다. 정보 표시줄 닫기 단추를 클릭 한 호스트에서 자동으로 제거 되지만 추가 작업은 다른 정보 표시줄 제거 해야 후 닫을 경우 필요 합니다. 또한 원격 분석 각 정보 표시줄에서 독립적으로 기록 되도록 할 수 있습니다.  
  
#### <a name="receiving-infobar-events-in-a-toolwindowpane"></a>에 ToolWindowPane 정보 표시줄 이벤트를 수신합니다.  
 ToolWindowPane 정보 표시줄에 대 한 두 개의 이벤트에 있습니다. InfoBarClosed 이벤트는 ToolWindowPane에 정보 표시줄이 닫힐 때 발생 합니다. 정보 표시줄 내 단추나 하이퍼링크를 클릭할 때 InfoBarActionItemClicked 이벤트가 발생 합니다.  
  
#### <a name="receiving-infobar-events-directly-from-the-uielement"></a>UIElement에서 직접 정보 표시줄 이벤트를 수신합니다.  
 정보 표시줄의 ui 요소에서 직접 이벤트를 구독할 수 IVsInfoBarUIElement.Advise는 사용할 수 있습니다. IVsInfoBarUIEvents 구현 하는 작성자가 close 수신 하 고 클릭 이벤트를 허용 합니다.  
  
```  
public interface IVsInfoBarUIEvents  
{  
    void OnActionItemClicked(IVsInfoBarUIElement infoBarUIElement, IVsInfoBarActionItem actionItem);  
    void OnClosed(IVsInfoBarUIElement infoBarUIElement);  
}  
  
```  
  
##  <a name="a-namebkmkerrorvalidationa-error-validation"></a><a name="BKMK_ErrorValidation"></a> 유효성 검사 오류  
 필수 필드는 생략 하는 경우와 같은 또는 잘못 된 형식의 데이터를 입력할 때에 허용 되지 않는 정보를 입력할 때 유효성 검사를 사용 하 여 제어 또는 차단 팝업 오류 대화 상자를 사용 하는 대신 컨트롤 근처 피드백 하는 것이 좋습니다.  
  
### <a name="field-validation"></a>필드 유효성 검사  
 세 가지 구성 요소로 이루어져 있습니다 양식 및 필드 유효성 검사: 컨트롤, 아이콘 및 도구 설명 합니다. 여러 유형의 컨트롤에는이 사용할 수 있습니다, 예를 들어 텍스트 상자 사용 됩니다.  
  
 ![필드 유효성 검사 &#40; 빈 &#41;](../../extensibility/ux-guidelines/media/0905-01_fieldvalidation.png "0905-01_FieldValidation")  
  
 필드가 필요한 경우 없어야 라는 텍스트를 워터 마크 **\< 필요한>** 필드 배경 빛 해야 노란색 (VSColor: `Environment.ControlEditRequiredBackground`) 전경 회색 이어야 하 고 (VSColor: `Environment.ControlEditRequiredHintText`):  
  
 !["필수" 레이블이 있는 필드 유효성 검사](../../extensibility/ux-guidelines/media/0905-02_fieldvalidationrequired.png "0905-02_FieldValidationRequired")  
  
 컨트롤의 상태 인지 결정할 수 *에 입력 된 잘못 된 콘텐츠* 다른 컨트롤로 포커스가 이동 될 때 또는 사용자 커밋 [확인] 단추를 클릭할 때 또는 사용자는 문서 또는 폼을 저장 하는 경우.  
  
 잘못 된 콘텐츠 상태를 확인 하는 경우 컨트롤 내부 또는 바로 그 옆에 아이콘이 나타납니다. 가리키면 표시 아이콘 또는 컨트롤의 오류를 설명 하는 도구 설명이 표시 됩니다. 또한 1 픽셀 테두리를 잘못 된 상태를 만드는 컨트롤 주위에 나타나야 합니다.  
  
 ![필드 유효성 검사 레이아웃 사양](../../extensibility/ux-guidelines/media/0905-03_layoutspecs.png "0905-03_LayoutSpecs")  
  
 **필드 유효성 검사 레이아웃 사양**  
  
#### <a name="acceptable-variations-for-icon-location"></a>아이콘 위치에 대 한 허용 가능한 변형  
 유효성 검사 오류에 대 한 알림을 받을 사용자가 해야 하는 수많은 고유 경우가 있습니다. 컨트롤 유형과 구성 ui를 고려 하면 상황에 맞는 아이콘 위치를 선택 합니다.  
  
 ![아이콘 위치에 적합한 위치](../../extensibility/ux-guidelines/media/0905-04_iconlocation.png "0905-04_IconLocation")  
  
 **필드 유효성 검사 아이콘 위치에 대 한 허용 가능한 변형**  
  
#### <a name="validation-requiring-a-round-trip-to-a-server-or-network-connection"></a>서버 또는 네트워크 연결에 라운드트립을 수행 하는 유효성 검사  
 경우에 따라 서버에 대 한 라운드 트립을 콘텐츠를 확인 하는 데 필요 하 고는 것이 확인 된 사용자 진행률 및 오류 상태를 표시 하는 것이 중요 합니다. 아래 그림이이 사례 및 권장 되는 UI의 예를 보여 줍니다.  
  
 ![서버에 대한 왕복과 관련된 유효성 검사](../../extensibility/ux-guidelines/media/0905-05_roundtrip.png "0905-05_RoundTrip")  
  
 **서버에 왕복과 관련 된 유효성 검사**  
  
 "확인..."를 수용 하기 위해 컨트롤의 오른쪽에 적절 한 사용 가능한 공간을 제공 해야 하는 참고 텍스트 "다시 시도" 합니다.  
  
#### <a name="in-place-warning-text"></a>내부 경고 텍스트  
 컨트롤에 가까운 오류 메시지의 오류 상태로 전환 하려면 사용 가능한 공간이 있는 경우,이 도구 설명만을 사용 하 여 보다 선호 됩니다.  
  
 ![(& a) #45; 내부 경고](../../extensibility/ux-guidelines/media/0905-06_inplacewarning.png "0905-06_InPlaceWarning")  
  
 **내부 경고 텍스트**  
  
#### <a name="watermarks"></a>워터 마크  
 때로는 전체 컨트롤이 나 창 오류 상태에서입니다. 이 상황에서 워터 마크를 사용 하 여 해당 오류를 나타냅니다.  
  
 ![워터마크](../../extensibility/ux-guidelines/media/0905-07_watermark.png "0905-07_Watermark")  
  
 **워터 마크 필드 유효성 검사**