---
title: Visual Studio 기능 둘러보기-디버거 | Microsoft Docs
description: Visual Studio 디버거 둘러보기
ms.custom: mvc
ms.date: 03/27/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: c763d706-3213-494f-b4d2-990b6e1ec456
caps.latest.revision: 1
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2e031716c68d44a9d08a4b074c5dcb58d5553041
ms.sourcegitcommit: 064f8678f4a918e1dce60285090a9803d37dc34b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2018
---
# <a name="quickstart-first-look-at-the-visual-studio-debugger"></a>빠른 시작: Visual Studio 디버거 조사

이 항목에서는 Visual Studio 디버거 기능을 소개 합니다. Visual Studio에서 직접 앱을 열어 진행 하 시겠습니까, 그럴 수 또는 사용 하 여 샘플 앱도 함께 수행할 수는 [초보자 가이드](../debugger/getting-started-with-the-debugger.md)합니다.

여기서 설명 하는 기능은 C#, c + +, Visual Basic, JavaScript 및 명시 된 경우) (제외 Visual Studio에서 지 원하는 다른 언어에 적용 됩니다.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>중단점을 설정 하 고 디버거를 시작

를 디버깅 하려면 디버거가 응용 프로그램 프로세스에 연결 된 앱을 시작 해야 합니다. F5 키 (**디버그 > 디버깅 시작**) 작업을 수행 하는 가장 일반적인 방법입니다. 그러나 지금은 중단점 검사할 앱 수를 설정 하지 코딩, 하므로 작업을 먼저 수행 하 고 디버깅을 시작 합니다.

파일이 코드 편집기에 열려 있는 경우에 코드 줄의 왼쪽 여백을 클릭 하 여 중단점을 설정할 수 있습니다.

![중단점을 설정](../debugger/media/dbg-tour-set-a-breakpoint.gif "중단점 설정")

F5 키를 누릅니다 (**디버그 > 디버깅 시작**) 하 고 발견 되는 첫 번째 중단점으로 디버거를 실행 합니다. 응용 프로그램이 아직 실행 되지 않는 경우 f 5를 눌러 디버거를 시작 하 고 첫 번째 중단점에서 중지 합니다.

자세히 검사 하려는 코드 섹션 또는 코드 줄을 알고 있는 경우 중단점은 유용한 기능으로 지정 합니다.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>단계 명령을 사용 하 여 디버거에서 코드를 탐색

하기 때문에 응용 프로그램 코드의 탐색 빠른 대부분 명령에 대 한 바로 가기 키 제공 합니다. (해당 하는 명령 예: 메뉴 명령을 괄호 안에 표시 됩니다.)

F11 키를 눌러 디버거를 연결 및 응용 프로그램을 시작 하려면 (**디버그 > 한 단계씩 코드 실행**). F11는는 **한 단계씩 코드 실행** 명령을 클릭 한 번에 응용 프로그램 실행 한 문 앞으로 이동 합니다. F11로 앱을 시작할 때 디버거는 실행 되는 첫 번째 문에서 중단 합니다.

![F11 키를 한 단계씩](../debugger/media/dbg-tour-f11.png "F11 한 단계씩 코드 실행")

노란색 화살표는 또한 (이 문은 실행 되지 않았으면 아직) 같은 지점에서 응용 프로그램 실행을 일시 중단 하는 문을입니다 디버거가 일시 중지를 나타냅니다.

F11이 세부 정보에서 실행 흐름을 검사 하는 것이 좋습니다. (코드를 통해 더 빠르게 이동할 보여줍니다 다른 옵션 또한.) 기본적으로 디버거 사용자 코드가 아닌으로 건너뜁니다 (자세한 내용은 참조 [내 코드만](../debugger/just-my-code.md)).

>[!NOTE]
> 관리 코드에서 속성 및 연산자 건너뛰기 (기본 동작) 자동으로 단계별로 실행할 때 알림을 받을 것인지를 묻는 대화 상자가 표시 됩니다. 설정을 변경 하려는 경우 나중에 사용 하지 않도록 설정 **속성 및 연산자 건너뛰기** 에서 설정는 **도구 > 옵션** 메뉴 아래 **디버깅**합니다.

## <a name="step-over-code-to-skip-functions"></a>코드를 건너뛰려면 함수

함수 또는 메서드 호출 되는 코드의 줄에 있는 경우 f 10을 눌러 수 있습니다 (**디버그 > 프로시저 단위 실행**) F11 대신 합니다.

F10 함수나 (코드를 실행 여전히) 앱 코드에서 메서드를 한 단계씩 실행 하지 않고 디버거를 이동 합니다. F10 키를 눌러 사용자가 관심이 있는 코드에 대해 건너뛸 수 있습니다. 이러한 방식으로 얻을 수 있습니다 신속 하 게에 더 관심이 있는 코드.

## <a name="step-into-a-property"></a>속성을 한 단계씩

디버거 관리 되는 속성 및 필드를 건너뜁니다 기본적으로 앞에서 설명한 것 처럼 하지만 **한 단계씩 코드** 명령을이 동작을 재정의할 수 있습니다.

속성 또는 필드를 마우스 오른쪽 단추로 클릭 하 고 선택 **한 단계씩 코드**, 사용 가능한 옵션 중 하나를 선택 합니다.

![특정 한 단계씩](../debugger/media/dbg-tour-step-into-specific.png "단계씩 코드 실행")

이 예제에서는 **한 단계씩 코드** us에 대 한 코드를 가져옵니다 `Path.set`합니다.

![특정 한 단계씩](../debugger/media/dbg-tour-step-into-specific-2.png "단계씩 코드 실행")

## <a name="run-to-a-point-in-your-code-quickly-using-the-mouse"></a>마우스를 신속 하 게 사용 하 여 코드의 지점에 실행

디버거에 있는 동안 위로 마우스를 가져가고 될 때까지 코드 줄의 **클릭에 실행** (여기서 실행 실행) 단추 ![클릭에 실행](../debugger/media/dbg-tour-run-to-click.png "RunToClick") 왼쪽에 나타납니다.

![실행을 클릭 하 여](../debugger/media/dbg-tour-run-to-click-2.png "클릭에 실행")

>  [!NOTE] 
> **클릭에 실행** (여기서 실행 실행) 단추는의 새로운 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다.

클릭는 **클릭에 실행** (여기서 실행 실행) 단추입니다. 디버거를 클릭 한 코드의 줄으로 이동 합니다.

이 단추를 사용 하 여 임시 중단점을 설정 하는 것과 비슷합니다. 이 명령은 응용 프로그램 코드의 표시 영역 내에서 신속 하 게 살펴보기도 유용 합니다. 사용할 수 있습니다 **클릭에 실행** 열려 있는 특정 파일에 있습니다.

## <a name="advance-the-debugger-out-of-the-current-function"></a>디버거는 현재 함수 외부로 이동

디버깅 세션을 계속 있지만, 현재 함수의 끝까지 디버거를 진행 하는 경우가 있습니다.

Shift + F11 키를 누릅니다 (또는 **디버그 > 프로시저 나가기**).

응용 프로그램 실행을 다시 시작 (및 디버거를 앞으로 이동)이이 명령은 현재 함수에서 반환 될 때까지 합니다.

## <a name="run-to-cursor"></a>커서까지 실행

키를 눌러 디버거를 중지는 **디버깅 중지** 빨간색 단추 ![디버깅 중지](../debugger/media/dbg-tour-stop-debugging.png "디버깅 중지") 또는 Shift + f 5를 눌러 합니다.

응용 프로그램에서 코드의 줄을 마우스 오른쪽 단추로 클릭 하 고 선택 **커서까지 실행**합니다. 이 명령은 디버깅을 시작 하 고 코드의 현재 줄에 임시 중단점을 설정 합니다.

![커서까지 실행](../debugger/media/dbg-tour-run-to-cursor.png "커서까지 실행")

중단점을 설정 하면 디버거가 페이로드만 첫 번째 중단점에서 일시 중지 됩니다.

F5 키를 누른 채 선택한 코드 줄에 도달할 때까지 **커서까지 실행**합니다.

이 명령은 코드를 편집 하 고 신속 하 게 임시 중단점을 설정 하 고 디버거를 시작 하려고 할 때 유용 합니다.


> [!NOTE]
> 사용할 수 있습니다 **커서까지 실행** 에 **호출 스택** 디버깅 하는 동안 창.

## <a name="restart-your-app-quickly"></a>응용 프로그램을 신속 하 게 다시 시작

클릭는 **다시 시작** ![응용 프로그램 다시 시작](../debugger/media/dbg-tour-restart.png "응용 프로그램 다시 시작") 디버그 도구 모음에서 단추 (**Ctrl + Shift + f 5를 눌러**).

누를 때 **다시 시작**와 비교 하는 앱을 중지 하 고 디버거를 다시 시작 시간을 절약 합니다. 디버거는 코드를 실행 하 여 적중 하는 첫 번째 중단점에서 일시 중지 합니다.

디버거를 중지 하 여 코드 편집기에 다시 액세스할 않으려면 누르면 빨간색 중지 ![디버깅 중지](../debugger/media/dbg-tour-stop-debugging.png "디버깅 중지") 단추 대신 **다시 시작**합니다.

## <a name="inspect-variables-with-data-tips"></a>데이터 팁을 사용 하 여 변수를 검사 합니다.

이제 조금 사용 방법을 알고 있는 디버거를 사용 하면 응용 프로그램 상태가 (변수) 검사를 시작할 수 있는 좋은 기회가 있는지 합니다. 디버거의 가장 유용한 기능 중 일부 기능을 사용 하는 변수를 검사 하는 하 고 여러 가지 방법으로 작업을 수행할을 합니다. 종종 문제를 디버깅 하려고 할 때 변수는 특정 응용 프로그램 상태에 있어야 하는 값을 저장 하는 여부를 알아보려면 하려고 합니다.

디버거에서 일시 중지 된 동안 위로 마우스를 가져가고 마우스로 개체의 기본 속성 값을 표시 하 고 (이 예제에서는 파일 이름 `market 031.jpg` 속성 값은 기본값).

![데이터 팁 보기](../debugger/media/dbg-tour-data-tips.gif "데이터 팁을 보려면")

모든 속성을 보려면 개체에 확장 하 고 (같은 `FullPath` 이 예에서 속성).

종종를 디버깅할 때 신속 하 게 개체에 속성 값을 확인 하 고 데이터 팁 설정을 수행 하는 좋은 방법입니다.

> [!TIP]
> 가장 지원 되는 언어에서 디버깅 세션 중에 코드를 편집할 수 있습니다. 자세한 내용은 참조 하십시오. [편집 하며 계속 하기](../debugger/edit-and-continue.md)합니다.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>자동 및 지역 창을 사용 하 여 변수를 검사 합니다.

디버깅 하는 동안 확인 된 **자동** 코드 편집기의 아래쪽 창에 있습니다.

![창 자동](../debugger/media/dbg-tour-autos-window.png "자동 창")

에 **자동** 변수와 함께 가져가서 현재 값 및 해당 형식을 참조 창. **자동** 창에 현재 줄 이나 이전 줄에 사용 되는 모든 변수 표시 (c + +, 창에서는 변수 코드의 이전 세 줄. 언어별 동작에 대 한 설명서를 참조).

> [!NOTE]
> JavaScript에서는 **지역** 창이 있지 않고 지원 되는 **자동** 창.

다음으로 확인 된 **지역** 창. **지역** 현재 범위에는 변수 창에 표시 합니다.

![지역 창](../debugger/media/dbg-tour-locals-window.png "지역 창")

이 예제는 `this` 개체와 개체 `f` 범위에 있습니다. 자세한 내용은 참조 하십시오. [자동 및 지역 창에서 변수를 검사](../debugger/autos-and-locals-windows.md)합니다.

## <a name="set-a-watch"></a>조사식 설정

사용할 수는 **조사식** 창에 변수 (또는 식) 관심을 기울 원하는 지정 합니다.

디버깅 하는 동안 개체를 마우스 오른쪽 단추로 클릭 하 고 선택 **조사식 추가**합니다.

![조사식 창](../debugger/media/dbg-tour-watch-window.png "조사식 창")

에 설정 조사식이 예에서 한는 `File` 개체 디버거를 통해 이동 변경 값을 볼 수 있습니다. 다른 변수 창과 달리는 **조사식** windows 항상 표시 변수 조사 중인 있습니다 하는 회색 때 범위를 벗어났습니다.

자세한 내용은 참조 하세요. [조사식 및 간략 한 조사식 창 사용 하 여 감시를 설정 합니다.](../debugger/watch-and-quickwatch-windows.md)

## <a name="examine-the-call-stack"></a>호출 스택을 검사합니다

클릭는 **호출 스택** 은 기본적으로 오른쪽 아래 창에서 열려 있는 창을 디버깅 하는 동안 합니다.

![호출 스택을 검사](../debugger/media/dbg-tour-call-stack.png "호출 스택을 검사")

**호출 스택** 창에 있는 메서드 및 함수 호출 되는 순서를 가져오는 표시 합니다. 맨 윗줄로 현재 함수를 보여 줍니다 (의 `Update` 이 예제의 메서드). 두 번째 줄을 보여 줍니다 `Update` 에서 호출한는 `Path.set` 속성 및 기타 등등. 호출 스택은 검토 하 고 응용 프로그램의 실행 흐름을 이해 하는 좋은 방법입니다.

> [!NOTE]
> **호출 스택** 창은 Eclipse와 같은 일부 Ide에서 디버그 관점 비슷합니다.

해당 소스 코드를 이동 하는 코드 줄을 두 번 클릭 수 및도 디버거를 통해 검사 중인 현재 범위를 변경 하는 합니다. 이 디버거를 진행 하지 않습니다.

오른쪽 클릭 메뉴에서 사용할 수도 있습니다는 **호출 스택** 창의 다른 작업을 수행 합니다. 특정 함수에 중단점을 삽입, 사용 하 여 응용 프로그램을 다시 시작 수는 예를 들어 **커서까지 실행**를 이동할 소스 코드를 검사 합니다. 참조 [하는 방법: 호출 스택을 검사](../debugger/how-to-use-the-call-stack-window.md)합니다.

## <a name="examine-an-exception"></a>예외를 검사 합니다.

응용 프로그램에서 예외를 throw 하는 경우 디버거가 예외를 발생 시킨 코드 줄으로 이동 합니다.
     
![예외 도우미](../debugger/media/dbg-tour-exception-helper.png "예외 도우미")

이 예제에서는 **예외 도우미** 표시는 `System.Argument` 예외와 경로가 올바른 형식이 않은 없다는 오류 메시지가 있습니다. 따라서 메서드 또는 함수 인수에 오류가 발생 한 알고 있습니다.

이 예제는 `DirectoryInfo` 에 저장 된 빈 문자열에는 오류를 지정 하는 호출의 `value` 변수입니다.

예외 도우미는 오류를 디버그 하는 데 도움이 되는 유용한 기능입니다. 오류 세부 정보 보기와 같은 작업을 수행 하 고 예외 도우미에서 한 조사식을 추가할 수도 있습니다. 또는 필요에 따라 특정 예외를 throw 하는 조건을 변경할 수 있습니다.

>  [!NOTE] 
> 예외 도우미 대체 예외 도우미 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다.

확장 된 **예외 설정** 수 있지만이 예외 형식을 처리 하는 방법에 대 한 다른 옵션을 보려면 노드를이 둘러보기는에 아무 것도 변경할 필요가 없습니다!

## <a name="debug-live-aspnet-apps-in-azure-app-service"></a>Azure 앱 서비스에서 라이브 ASP.NET 앱 디버깅

**스냅숏 디버거** 에 관심이 있는 코드가 실행 되 면 프로덕션에서 응용 프로그램의 스냅숏을 수행 합니다. 디버거가 스냅숏을 생성하도록 명령하려면 코드에서 snappoint와 logpoint를 설정합니다. 디버거를 통해 프로덕션 응용 프로그램의 트래픽에 영향을 미치지 않으면서 정확히 무엇이 잘못되었는지를 볼 수 있습니다. 스냅샷 디버거를 사용하면 프로덕션 환경에서 발생하는 문제를 해결하는 데 걸리는 시간을 상당히 줄일 수 있습니다.

![스냅숏 디버거를 시작할](../debugger/media/snapshot-launch.png "스냅숏 디버거 시작")

Azure 앱 서비스에서 실행 되는 ASP.NET 응용 프로그램에 대 한 스냅숏 컬렉션 ´ ù. .NET Framework 4.6.1에서 ASP.NET 응용 프로그램을 실행 해야 이상에서 ASP.NET Core 응용 프로그램을.NET Core 2.0 또는 나중에 Windows에서 실행 해야 합니다.

자세한 내용은 참조 [스냅숏 디버거를 사용 하 여 라이브 ASP.NET 응용 프로그램을 디버깅](../debugger/debug-live-azure-applications.md)합니다.

## <a name="view-snapshots-with-intellitrace-step-back-visual-studio-enterprise"></a>IntelliTrace 단계 저장 (Visual Studio Enterprise)를 사용 하 여 보기 스냅숏

**IntelliTrace 단계 다시** 자동으로 단계 이벤트는 모든 중단점 및 디버거에서의 응용 프로그램의 스냅숏을 만듭니다. 기록된 스냅숏을 통해 이전 중단점 또는 단계로 돌아가서 응용 프로그램의 과거 상태를 볼 수 있습니다. IntelliTrace 뒤로 이동을 사용하면 이전 응용 프로그램 상태를 보고 싶지만 디버깅을 다시 시작하거나 원하는 앱 상태를 다시 만들지 않으려는 경우에 시간을 절약할 수 있습니다.

디버그 도구 모음의 **뒤로 가기**와 **앞으로 가기** 단추를 사용하여 이동하고 스냅숏을 볼 수 있습니다. 이 단추를 사용하여 **진단 도구** 창의 **이벤트** 탭에 나타나는 이벤트를 탐색할 수 있습니다.

![뒤로 및 앞으로 단추 단계](../debugger/media/intellitrace-step-back-icons-description.png  "단계 뒤로 및 앞으로 단추")  

자세한 내용은 [IntelliTrace 뒤로 이동을 사용하여 스냅숏 보기](../debugger/how-to-use-intellitrace-step-back.md) 페이지를 참조하세요.

## <a name="more-features-to-look-at"></a>더 많은 기능을 확인

-   [팁과 요령 디버거](../debugger/debugger-tips-and-tricks.md) 디버거에서 사용 하 여 생산성을 높이 방법에 알아봅니다.

-   [편집 하며 계속 하기](../debugger/edit-and-continue.md) (C#, c + +, Visual Basic) 언어의 하위 집합에 대 한는 편집 하며 계속 하기 기능을 사용 하면 디버깅 세션 중에 코드를 편집할 수 있습니다.

-   [다중 스레드 응용 프로그램을 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md) 다중 스레드 응용 프로그램을 디버깅 하는 방법에 설명 합니다. 

-   [원격 디버깅](../debugger/remote-debugging.md) 다른 컴퓨터 또는 장치에서 실행 되는 응용 프로그램을 디버깅 하는 방법을 설명 합니다. 
  
-   [IntelliTrace](../debugger/intellitrace.md) Visual Studio Enterprise에서 IntelliTrace 기능에 설명 합니다. 사용할 수 있습니다 레코드 및 추적 코드의 실행 내역입니다.

-   [네트워크 사용량](../profiling/network-usage.md) 웹 서비스 및 기타 네트워크 리소스에 앱 UWP (유니버설 Windows)를 디버깅 하는 데 사용할 수 있는 프로 파일링 도구에 설명 합니다. 페이로드를 검사 하는 도구를 사용 합니다.

-   [디버그 인터페이스 액세스 SDK](../debugger/debug-interface-access/debug-interface-access-sdk.md) Microsoft 디버그 인터페이스 액세스 소프트웨어 개발 키트 (DIA SDK)에 대해 설명 합니다. DIA SDK는 Microsoft 사후 컴파일러 도구에서 생성한 프로그램 데이터베이스(.pdb) 파일에 저장된 디버그 정보에 액세스할 수 있도록 합니다.  

## <a name="see-also"></a>참고 항목  
 [Visual Studio의 디버깅](../debugger/index.md)
