---
title: 라이브 Azure ASP.NET 응용 프로그램을 디버깅
ms.description: Learn how to set snappoints and view snapshots with the Snapshot Debugger.
ms.custom: mvc
ms.date: 03/16/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
helpviewer_keywords:
- debugger
ms.assetid: adb22512-4d4d-40e5-9564-1af421b7087e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
- azure
ms.openlocfilehash: 415e2ee4da01affd2d34b2bbb1aafb5de697767e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="debug-live-aspnet-azure-apps-using-the-snapshot-debugger"></a>스냅숏 디버거를 사용 하 여 라이브 Azure ASP.NET 응용 프로그램을 디버깅

스냅숏 디버거는 관심이 코드가 실행 되 면 프로덕션에서 응용 프로그램의 스냅숏을 만듭니다. 디버거가 스냅숏을 생성하도록 명령하려면 코드에서 snappoint와 logpoint를 설정합니다. 디버거를 통해 프로덕션 응용 프로그램의 트래픽에 영향을 미치지 않으면서 정확히 무엇이 잘못되었는지를 볼 수 있습니다. 스냅샷 디버거를 사용하면 프로덕션 환경에서 발생하는 문제를 해결하는 데 걸리는 시간을 상당히 줄일 수 있습니다.

Snappoints 및 logpoints 중단점, 유사 하지만 snappoints 중단점, 달리 응용 프로그램을 중지 하지 않는 적중 될 때입니다. 일반적으로 snappoint에서 스냅숏을 캡처하 게 10-20 밀리초를 사용 합니다. 

스냅숏 컬렉션은 Azure App Service에서 실행되는 다음 웹앱에서 사용할 수 있습니다.

- .NET Framework 4.6.1 이상에서 실행되는 ASP.NET 응용 프로그램
- Windows의 .NET Core 2.0 이상에서 실행되는 ASP.NET Core 응용 프로그램

또한 스냅숏 디버거는 Visual Studio 2017 Enterprise 버전 15.5 이상이 및 기본 이상의 앱 서비스 계획에 사용할 수만 있습니다. 

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 스냅숏 디버거 시작
> * snappoint를 설정 하 고 스냅숏을 보려면
> * logpoint 설정

## <a name="start-the-snapshot-debugger"></a>스냅숏 디버거 시작

1. 설치 [Visual Studio 2017 Enterprise 버전 15.5](https://www.visualstudio.com/downloads/) 이상. 이전 Visual Studio 2017 설치에서 업데이트 하는 경우 Visual Studio 설치 관리자를 실행 하 고 ASP.NET 및 웹 개발 작업에서 스냅숏 디버거 구성 요소를 확인 합니다.

2. 스냅숏 디버그 하려면 프로젝트를 엽니다. 

    > [!IMPORTANT] 
    > 스냅숏 디버그 하려면 열려는 **동일한 버전의 소스 코드** Azure 앱 서비스에 게시 하는 합니다. 

3. 클라우드 탐색기에서 (**보기 > 클라우드 탐색기**) 프로젝트를 배포 하는 Azure 앱 서비스를 마우스 오른쪽 단추로 클릭 하 고 선택 **스냅숏 디버거 연결**합니다.

   ![스냅숏 디버거 시작](../debugger/media/snapshot-launch.png)

    선택 하면 처음으로 **스냅숏 디버거 연결**, Azure 앱 서비스에서 스냅숏 디버거 사이트 확장을 설치 하 라는 메시지가 있습니다. 이 Azure 앱 서비스를 다시 시작을 해야 합니다. 

   Visual Studio 디버깅 모드 스냅숏에 포함 되었습니다.

    > [!NOTE]
    > Application Insights 사이트 확장 스냅숏 디버깅도 지원합니다. "사이트 확장 만료" 오류 메시지가 발생 하면 참조 [문제 해결 팁 및 스냅숏 디버깅에 대 한 알려진된 문제](../debugger/debug-live-azure-apps-troubleshooting.md) 세부 정보를 업그레이드 합니다.

   ![스냅숏 디버깅 모드](../debugger/media/snapshot-message.png)

   **모듈** 창에 표시 되는 Azure 앱 서비스에 대 한 모든 모듈 로드 한 경우 (선택 **디버그 / Windows / 모듈** 이 창을 열려면).

   ![모듈 창을 확인 하십시오.](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>snappoint 설정

1. 코드 편집기 왼쪽된 여백에 관심이 있는 snappoint 설정 하려면 코드 줄 옆을 클릭 합니다. 실행될지 알고 있는 코드 인지 확인 합니다.

   ![snappoint 설정](../debugger/media/snapshot-set-snappoint.png)

2. 클릭 **컬렉션 시작** 는 snappoint 켜려면 합니다.  

   ![snappoint 설정](../debugger/media/snapshot-start-collection.png)

    > [!TIP]
    > 스냅숏, 볼 때 이동할 수 없습니다 되지만 여러 snappoints 코드의 서로 다른 줄에서 실행을 수행 하기 위해 코드에 배치할 수 있습니다. 코드에서 여러 snappoints 있으면 스냅숏 디버거 하면 해당 스냅숏을 같은 최종 사용자 세션에서 지 있습니다. 스냅숏 디버거는 응용 프로그램에 도달 하는 많은 사용자가 있는 경우에 합니다.

## <a name="take-a-snapshot"></a>스냅숏 만들기

snappoint를 설정 하는 경우에 snappoint 위치 코드 줄이 실행 될 때마다 스냅숏을 캡처하려면 됩니다. 이 실행 서버에서 실제 요청에 의해 발생할 수 있습니다. 적중, 웹 사이트의 브라우저 보기로 이동 하 고, 추가 작업을 실행 하 여 snappoint 강제로 적중 될 프로그램 snappoint를 발생 시키는 데 필요 합니다.

## <a name="inspect-snapshot-data"></a>스냅숏 데이터를 검사 합니다.

1. snappoint 적중 될 때 스냅숏 진단 도구 창에 나타납니다. 이 창을 열려면 선택 **디버그 / Windows / 진단 도구 표시**합니다.

   ![snappoint 열기](../debugger/media/snapshot-diagsession-window.png)

1. 코드 편집기에서 스냅숏을 열려면 snappoint 두 번 클릭 합니다.

   ![스냅숏 데이터를 검사 합니다.](../debugger/media/snapshot-inspect-data.png)

   DataTips를 보려면 사용 하 여 변수를 가리키면 수이 뷰에서 **지역**, **감시**, 및 **호출 스택** 창, 식을 평가 합니다.

    웹 사이트로 아직까지 이며 최종 사용자가 영향을 받음 되지 않습니다. 기본적으로 snappoint 당 하나의 스냅숏을 캡처하도록:는 snappoint 해제 후 스냅숏이 캡처됩니다. snappoint에서 다른 스냅숏을 캡처하려면 하려면 켤 수 있습니다는 snappoint 다시 클릭 하 여 **컬렉션 업데이트**합니다.

앱에 더 많은 snappoints를 추가 하 고와 매크로 설정할 수도 있습니다는 **컬렉션 업데이트** 단추입니다.

**도움이 필요 하십니까?** 참조는 [문제 해결 및 알려진된 문제](../debugger/debug-live-azure-apps-troubleshooting.md) 및 [스냅숏 디버깅에 대 한 FAQ](../debugger/debug-live-azure-apps-faq.md) 페이지입니다.

## <a name="set-a-conditional-snappoint"></a>조건부 snappoint 설정

응용 프로그램에서 특정 상태를 다시 만드는 어려운 경우 조건부 snappoint의 사용 여부를 활용 하는 것이 좋습니다. 조건부 snappoints 도움말 응용 프로그램 변수를 검사 하 고 원하는 특정 값 범위는 때와 같은 원하는 상태가 될 때까지 스냅숏을 만드는 것을 방지 합니다. 적중 횟수 또는 필터 식을 사용 하는 조건을 설정할 수 있습니다.

#### <a name="to-create-a-conditional-snappoint"></a>조건부 snappoint를 만들려면

1. Snappoint 아이콘 (빈 볼)를 마우스 오른쪽 단추로 클릭 하 고 선택 **설정을**합니다.

   ![설정 선택](../debugger/media/snapshot-snappoint-settings.png)

1. Snappoint 설정 창에서 식을 입력 합니다.

   ![식을 입력 합니다.](../debugger/media/snapshot-snappoint-conditions.png)

   앞의 그림에만 스냅숏이 만들어질는 snappoint에 대 한 때 `visitor.FirstName == "Dan"`합니다.

## <a name="set-a-logpoint"></a>logpoint 설정

메시지를 기록 하도록 snappoint 구성할 수도 한 snappoint 적중 될 때 스냅숏 만들기, 외에도 (즉, 한 logpoint 만들기). 응용 프로그램을 다시 배포할 필요 없이 logpoints를 설정할 수 있습니다. Logpoints 실제로 실행 되는 및를 실행 중인 응용 프로그램에 파생 작업이 없거나 영향 발생 합니다.

#### <a name="to-create-a-logpoint"></a>logpoint를 만들려면

1. Snappoint 아이콘 (파란색 양쪽 대괄호)를 마우스 오른쪽 단추로 클릭 하 고 선택 **설정을**합니다.

1. Snappoint 설정 창에서 선택 **동작**합니다.

    ![logpoint 만들기](../debugger/media/snapshot-logpoint.png)

1. 메시지 필드에 기록 하려면 새 로그 메시지를 입력할 수 있습니다. 또한 로그 메시지에서 중괄호 내에 배치 하 여 변수를 평가할 수 있습니다.

    선택 하면 **출력 창에 보내기**는 logpoint 도달 메시지가 진단 도구 창에 나타납니다.

    ![Logpoint diagsession 창에는 데이터](../debugger/media/snapshot-logpoint-output.png)

    선택 하는 경우 **응용 프로그램 로그에 보낼**는 logpoint 적중 될 때, 메시지가 메시지를 볼 수 아무 곳 이나 표시 `System.Diagnostics.Trace` (또는 `ILogger` .NET Core에서는), 같은 [App Insights](/azure/application-insights/app-insights-asp-net-trace-logs)합니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 스냅숏 디버거를 사용 하는 방법을 배웠습니다. 이 기능에 대 한 자세한 내용을 보려면 수도 있습니다.

> [!div class="nextstepaction"]
> [스냅숏 디버깅 FAQ](../debugger/debug-live-azure-apps-faq.md)
