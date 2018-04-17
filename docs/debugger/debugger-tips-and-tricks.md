---
title: 팁과 힌트는 Visual Studio 디버거에서 | Microsoft Docs
ms.custom: ''
ms.date: 06/15/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- stepping
- debugging [Visual Studio], execution control
- execution, controlling in debugger
ms.assetid: 5262d8b1-2648-429e-85d5-90fcaadfb362
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3d5a748541aa9c50b698eda441f38c88f1e791c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="learn-productivity-tips-and-tricks-for-the-debugger-in-visual-studio"></a>Visual Studio의 디버거 용 생산성 팁과 요령에 알아보기

Visual Studio 디버거에 대 한 몇 가지 생산성 팁과 요령을 알아보려면이 항목을 읽습니다. 참조를 살펴보려면 디버거의 기본 기능 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)합니다. 이 항목에서는 기능 둘러보기에 포함 되지 않은 일부 영역을 다룹니다.

## <a name="pin-data-tips"></a>Pin 데이터 팁

자주 가리키면 데이터 팁 디버깅 하는 동안, 데이터 팁으로 빠르게 액세스 제공 변수에 대 한 고정 하는 것이 좋습니다. 변수를 다시 시작 후에 고정 된 상태로 유지 됩니다. 데이터 팁을 고정 하려면 고정 아이콘을 가리키면 하는 동안 클릭 합니다. 여러 변수를 고정할 수 있습니다.

![데이터 팁 고정](../debugger/media/dbg-tips-data-tips-pinned.png "PinningDataTip")

## <a name="edit-your-code-and-continue-debugging-c-vb-c"></a>코드를 편집 하 고 디버깅 (C#, VB, + +)

Visual Studio에서 지 원하는 대부분의 언어에서 디버깅 세션 중에 코드 편집한 디버깅을 계속 합니다. 디버거, 확인 편집 및 키를 눌러에서 일시 중지 된 동안 커서를 사용 하 여 코드에이 기능을 사용 하려면를 클릭 **F5**, **F10**, 또는 **F11** 디버깅을 계속 하려면.

![편집 하 고 디버깅을 계속](../debugger/media/dbg-tips-edit-and-continue.gif "EditAndContinue")

기능 제한 사항 및 기능을 사용 하 여에 자세한 내용은 참조 [편집 하며 계속 하기](../debugger/edit-and-continue.md)합니다.

## <a name="debug-issues-that-are-hard-to-reproduce"></a>재현 하기 어려운 문제 디버그

어려운 또는 응용 프로그램에서 특정 상태를 다시 만드는 데 많은 시간이 소요 인 경우에 조건부 중단점을 사용 하면 도움이 수 있는지 여부를 하는 것이 좋습니다. 사용할 수 있습니다 [조건부 중단점](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) 및 응용 프로그램 (예: 변수에서 잘못 된 데이터를 저장 하는 상태) 원하는 상태가 될 때까지 응용 프로그램 코드에 손상을 방지 하기 위해 중단점을 필터링 합니다. 식, 필터, 적중된 횟수 및 등을 사용 하 여 조건을 설정할 수 있습니다.

#### <a name="to-create-a-conditional-breakpoint"></a>조건부 중단점을 만들려면

1. 중단점 아이콘 (빨간 공이)를 마우스 오른쪽 단추로 클릭 하 고 선택 **조건**합니다.

2. 에 **중단점 설정** 창에서 식 입력 합니다.

    ![조건부 중단점](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

3. 에 더 관심이 선택 **필터** 대신 **조건식** 에 **중단점 설정** 대화 상자를 닫은 후 다음의 필터 팁입니다.

## <a name="change-the-execution-flow"></a>실행 흐름 변경

디버거는 마우스를 사용 하 여 왼쪽에 노란색 화살표 포인터를 가져올 코드 줄에서 일시 중지 합니다. 노란색 화살표 포인터 코드 실행 경로에서 다른 지점으로 이동 합니다. 다음 f5 키 또는 단계 명령을 사용 하 여 응용 프로그램 실행을 계속 합니다.

![실행 포인터 이동](../debugger/media/dbg-tour-move-the-execution-pointer.gif "실행 포인터를 이동 합니다.")

실행 흐름을 변경 하 여 서로 다른 코드 실행 경로 테스트 하거나 디버거를 다시 시작 하지 않고 코드를 다시 실행 하는 등의 작업을 수행할 수 있습니다.

> [!WARNING]
> 종종이 기능에 주의 해야 하 고 도구 설명에 경고를 표시 합니다. 너무 다른 경고를 볼 수 있습니다. 포인터를 이동 하면 이전 응용 프로그램 상태로 앱이 되돌릴 수 없습니다.

## <a name="track-an-out-of-scope-object-c-visual-basic"></a>추적 범위를 벗어난 개체 (C#, Visual Basic)

쉽게 같은 디버거 창을 사용 하 여 변수를 볼 수는 **조사식** 창. 그러나 변수 될 때에 범위에 속하지는 **조사식** 창은 회색으로 표시을 확인할 수 있습니다. 일부 앱 시나리오에서는 변수의 값도 변수가 범위를 벗어난 시점과 밀접 하 게 조사할 수도 변경 될 수 있습니다 (예를 들어 변수 발생할 수 가비지 수집). 개체 ID를 만들어 변수를 추적할 수 있습니다는 **조사식** 창.

#### <a name="to-create-an-object-id"></a>개체 ID를 만들려면

1.  추적 하려는 변수에 중단점을 설정 합니다.

2.  디버거를 시작 (**F5**) 중단점에서 중지 합니다.

3. 변수를 찾을 **지역** 창 (**디버그 > Windows > 지역**) 변수를 마우스 오른쪽 단추로 클릭 하 고 선택 **개체 ID 만들기**합니다.

    ![개체 ID 만들기](../debugger/media/dbg-tips-watch-create-object-id.png "CreateObjectID")
  
4.  **$** 창에 **지역** 창을 닫습니다. 이 변수는 개체 id입니다.
  
5.  개체 ID 변수를 마우스 오른쪽 단추로 클릭 하 고 선택 **조사식 추가**합니다.

자세한 내용은 참조 [개체 ID 만들기](../debugger/watch-and-quickwatch-windows.md#bkmk_objectIds)합니다.

## <a name="view-return-values-for-functions"></a>함수에 대 한 반환 값 보기

함수에 대 한 반환 값을 보려면에 표시 된 함수를 조사는 **자동** 코드를 단계별로 동안 창. 함수에 대 한 반환 값을 보려면에 관심이 함수가 이미 실행 된 있는지 확인 (키를 눌러 **F10** 함수 호출에는 현재 중지 되어 있는 경우 한 번). 창이 닫혀 있는 사용 하 여 **디버그 > Windows > 자동** 열려는 **자동** 창.

![창 자동](../debugger/media/dbg-tips-autos-window.png "AutosWindow")

또한의 함수를 입력할 수 있습니다는 **직접 실행** 반환 값 보기 창입니다. (사용 하 여 열고 **디버그 > Windows > 직접 실행**.)

![직접 실행 창](../debugger/media/dbg-tips-immediate-window.png "ImmediateWindow")

사용할 수도 있습니다 [의사 변수](../debugger/pseudovariables.md) 에 **조사식** 및 **직접 실행** 창 같은 `$ReturnValue`합니다.

## <a name="string_visualizer"></a>시각화 도우미에 문자열을 검사 합니다.

문자열에서 작업할 때는 형식화 된 전체 문자열을 볼 수 있습니다. 일반 텍스트, XML, HTML 또는 JSON 문자열을 보려면 돋보기 아이콘을 클릭 ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "시각화 도우미 아이콘") 는 문자열 값을 포함 하는 변수를 가리키면 됩니다.

![문자열 시각화 도우미를 열고](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

문자열 시각화 도우미 문자열 유형에 따라 잘못 된 형식의 문자열 인지 확인 하면 도움이 될 수 있습니다. 예를 들어 빈 **값** 필드 문자열 시각화 도우미 형식을에서 인식 되지 않습니다 나타냅니다. 자세한 내용은 참조 [문자열 시각화 도우미 대화 상자](../debugger/string-visualizer-dialog-box.md)합니다.

![JSON 문자열 시각화 도우미](../debugger/media/dbg-tips-string-visualizer-json.png "JSONStringVisualizer")

디버거 창에 표시 되는 WPF 개체 등 몇 가지 다른 형식에 대 한 시각화 도우미를 열 수 있습니다.

## <a name="break-into-code-on-handled-exceptions"></a>처리 된 예외에 대 한 코드 중단

디버거는 처리 되지 않은 예외에서 코드에 중단 합니다. 그러나 예외를 처리 (내에서 발생 하는 예외와 같은 `try/catch` 블록) 버그의 원인이 수 있으며 발생할 때 조사 하는 것이 좋습니다. 옵션을 구성 하 여 뿐만 아니라 처리 된 예외에 대 한 코드를 중단 하도록 디버거를 구성할 수는 **예외 설정** 대화 상자. 선택 하 여이 대화 상자를 열려면 **디버그 > Windows > 예외 설정**합니다.

**예외 설정** 대화 상자를 사용 하면 특정 예외에 대해 코드를 중단 하도록 디버거에 지시할 수 있습니다. 다음 그림에서는 디버거가 코드로 중단 될 때마다 한 `System.NullReferenceException` 발생 합니다. 자세한 내용은 참조 [예외 관리](../debugger/managing-exceptions-with-the-debugger.md)합니다.

![예외 설정 대화 상자](../debugger/media/dbg-tips-exception-settings.png "ExceptionSettingsDialogBox")

## <a name="debug-deadlocks-and-race-conditions"></a>교착 상태 및 경합 상태를 디버그 합니다.

종류의 다중 스레드 응용 프로그램에 공통 된 문제를 디버깅 해야 하는 경우 종종 디버깅 하는 동안 스레드 위치를 볼 수 있습니다. 사용 하 여 쉽게 수행할 수 있습니다는 **소스의 스레드 표시** 단추입니다.

#### <a name="to-show-threads-in-your-source-code"></a>소스 코드에서 스레드를 표시 하려면

1.  디버깅 하는 동안 클릭는 **소스의 스레드 표시** 단추 ![소스의 스레드 표시](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker") 에 **디버그** 도구 모음입니다.
  
2.  창 왼쪽의 여백을 확인합니다. 이 줄에 표시 된 *스레드 마커* 아이콘 ![스레드 마커](../debugger/media/dbg-thread-marker.png "ThreadMarker") 두 가닥의 실 유사한 합니다. 스레드 마커는 이 위치에서 스레드가 중지되었음을 나타냅니다.

    스레드 마커 중단점에서 부분적으로 숨겨진 수를 확인 합니다.
  
3.  스레드 마커에 포인터를 올려 놓습니다. DataTips가 나타납니다. DataTip을 통해 중지된 각 스레드의 이름과 스레드 ID 번호를 알 수 있습니다.

    스레드 위치를 볼 수도 있습니다는 [병렬 스택 창의](../debugger/get-started-debugging-multithreaded-apps.md)합니다.

## <a name="examine-payloads-for-web-services-and-network-resources-uwp"></a>웹 서비스 및 네트워크 리소스 (UWP)에 대 한 페이로드를 검사 합니다.

UWP 앱에서 사용 하 여 수행 하는 네트워크 작업을 분석할 수 있습니다는 `Windows.Web.Http` API입니다. 이 도구는 웹 서비스 및 네트워크 리소스를 디버깅 하는 데 사용할 수 있습니다. 이 도구를 사용 하려면 선택 **디버그 > 성능 프로파일러**합니다. 선택 **네트워크**를 선택한 후 **시작**합니다. 앱에서 `Windows.Web.Http`를 사용하는 시나리오를 확인한 다음 **컬렉션 중지**를 선택하여 보고서를 생성합니다.

![네트워크 사용량을 프로 파일링 도구의](../profiling/media/prof-tour-network-usage.png "NetworkUsageProfTool")

요약 뷰에서 작업을 선택하여 세부 정보를 확인할 수 있습니다.

![자세한 정보는 네트워크 사용량 도구에서](../profiling/media/prof-tour-network-usage-details.png "DetailedViewNetworkUsage")

자세한 내용은 [네트워크 사용량](../profiling/network-usage.md)을 참조하세요.

## <a name="get-more-familiar-with-how-the-debugger-attaches-to-your-app"></a>앱에 디버거 연결 하는 방법에 대해 get

실행 중인 앱에 연결할 디버거는 디버깅 하려는 응용 프로그램의 정확한 같은 빌드에 대해 생성 되는 기호 (.pdb) 파일을 로드 합니다. 일부 시나리오에서 기호 파일의 작은 기술 유용할 수 있습니다. Visual Studio를 사용 하 여 기호 파일을 로드 하는 방법을 검사할 수 있습니다는 **모듈** 창.

열기는 **모듈** 창을 선택 하 여 디버깅 하는 동안 **디버그 > Windows > 모듈**합니다. **모듈** 창 디버거가 사용자 코드로 처리 되며 모듈 알 수 또는 [ *내 코드*](../debugger/just-my-code.md), 및 기호 모듈에 대 한 상태를 로드 합니다. 대부분의 시나리오에서 디버거가 사용자 코드에 대 한 기호 파일을 자동으로 검색 하지만 추가 단계가 올바른 기호 파일을 가져오는 데 필요한 한 단계씩 코드 실행 (또는 디버그).NET framework 코드, 시스템 코드 또는 타사 라이브러리 코드 하려는 경우.

![모듈 창에서 기호 정보를 보려면](../debugger/media/dbg-tips-modules-window.png "ViewSymbolInformation")

직접 기호 정보를 로드할 수는 **모듈** 창을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 **기호 로드**합니다.

경우에 따라 응용 프로그램 개발자는 일치 하는 기호 파일 (공간을 줄이고), 나중에 릴리스 버전을 디버깅할 수 있습니다는 빌드에 대 한 파일 일치 하는 기호의 복사본을 유지 하지만 없이 앱을 배송 됩니다.

디버거가 사용자 코드와 코드를 분류 하는 방법을 알아보려면, 참조 [내 코드만](../debugger/just-my-code.md)합니다. 기호 파일에 대 한 자세한 참조 [Visual Studio 디버거에서 기호 (.pdb) 및 소스 파일 지정](specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)합니다.

## <a name="learn-more"></a>자세한 정보

추가 팁 및 요령 및 자세한 내용은 다음 블로그 게시물을 참조 하십시오.

- [Visual Studio의 디버깅에 대 한 7 미만 알려진된 해킹](https://blogs.msdn.microsoft.com/visualstudio/2017/06/26/7-lesser-known-hacks-for-debugging-in-visual-studio/)
- [Visual Studio에서 숨겨진된 gems 7](https://blogs.msdn.microsoft.com/visualstudio/2017/10/05/7-hidden-gems-in-visual-studio-2017/)

## <a name="see-also"></a>참고 항목
[바로 가기 키](../ide/tips-and-tricks-for-visual-studio.md)
