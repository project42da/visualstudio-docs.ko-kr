---
title: "Visual Studio에서 지연 UI 확장 진단 | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
author: PooyaZv
ms.author: pozandev
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 714d047cda7a167045983f5068a425d0d82823ea
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-diagnose-ui-delays-caused-by-extensions"></a>방법: 진단 UI 확장으로 지연이 발생

UI를 응답 하지 않는 경우 Visual Studio는 리프로 시작 하 고 기준에 대해 작동 UI 스레드의 호출 스택을 검사 합니다. Visual Studio 호출 스택 프레임에 설치 되어 있고 활성화 된 확장의 일부인 모듈에 속해 있는지 확인 하는 경우 알림을 보여 줍니다.

![UI 지연 (응답 중지) 알림](media/ui-delay-notification-in-vs.png)

알림을 UI 지연 (즉, UI에 응답) 되었을 수 확장 프로그램의 코드의 결과 사용자에 게 알립니다. 또한 사용자 확장 또는 해당 확장명에 대 한 향후 알림을 사용 하지 않도록 설정 하려면 옵션과 함께 제공 합니다.

이 문서는 확장 프로그램 코드에서 원인을 UI 지연 알림을 진단할 수 있는 방법을 설명 합니다. 

> [!NOTE]
> UI 지연 진단 하려면 Visual Studio 실험적 인스턴스를 사용 하지 마십시오. UI 지연 알림 하는 데 필요한 호출 스택이 분석의 일부 UI 지연 알림을 표시 하지 않을 수 있습니다 의미 실험적 인스턴스를 사용 하는 경우 비활성화 되어 있습니다.

진단 프로세스의 개요는 다음과 같습니다.
1. 트리거 시나리오를 식별 합니다.
2. VS를 다시 시작 로그온 활동을 포함 합니다.
3. ETW 추적을 시작 합니다.
4. 다시 표시 하려면 알림을 트리거하십시오.
5. ETW 추적을 중지 합니다.
6. 지연 ID를 가져옵니다. 활동 로그를 검사 합니다.
7. 6 단계에서 지연 ID를 사용 하 여 ETW 추적을 분석 합니다.

다음 섹션에서는 이러한 단계를 자세히 살펴보겠습니다.

## <a name="identifying-the-trigger-scenario"></a>트리거 시나리오를 식별합니다.

UI 지연을 진단 수행 하려면 먼저 (순서 동작의) 하면 Visual Studio에서 알림 표시를 식별 해야 합니다. 이를 나중에 로깅 기능이 설정 된 알림을 트리거할 수 있습니다에 대 한 순서로 표시 됩니다.

## <a name="restarting-vs-with-activity-logging-on"></a>활동에 대 한 로깅을 VS를 다시 시작

Visual Studio "활동 로그"를 생성할 수는 문제를 디버깅할 때 유용한 정보를 제공 하 합니다. Visual Studio에 로그인 하는 활동을 설정 하려면 시작을 사용한 Visual Studio는 `/log` 명령줄 옵션입니다. Visual Studio가 시작 되 면 작업 로그는 다음 위치에 저장 됩니다.

```DOS
%APPDATA%\Microsoft\VisualStudio\<vs_instance_id>\ActivityLog.xml
```

인스턴스 ID 프로그램 VS를 찾는 방법에 대해 자세히 알아보려면 참조 [을 검색 하 고 Visual Studio 인스턴스를 관리 도구](../install/tools-for-managing-visual-studio-instances.md)합니다. 이 활동 로그 UI 지연 및 관련된 알림에 대 한 자세한 정보를 나중에 사용 합니다.

## <a name="starting-etw-tracing"></a>ETW 추적을 시작합니다.

사용할 수 있습니다 [PerfView](https://github.com/Microsoft/perfview/) ETW 추적을 수집 하도록 합니다. ETW 추적을 수집 하기 위한와 분석을 위해 PerfView 사용 하기 쉬운 인터페이스를 제공 합니다. 다음 명령을 사용 하 여 추적을 수집 합니다.

```DOS
Perfview.exe collect C:\trace.etl /BufferSizeMB=1024 -CircularMB:2048 -Merge:true -Providers:*Microsoft-VisualStudio:@StacksEnabled=true -NoV2Rundown /kernelEvents=default+FileIOInit+ContextSwitch+Dispatcher
```

이 통해 공급자 UI 지연 알림을 관련 된 이벤트에 대 한 Visual Studio를 사용 하는 "Microsoft visual Studio" 공급자. 또한 PerfView "시간 스택 스레드" 뷰를 생성 하는 데 사용할 수 있는 커널 공급자에 대 한 키워드를 지정 합니다.

## <a name="triggering-the-notification-to-appear-again"></a>다시 표시 하려면 알림 트리거

PerfView 추적 컬렉션 시작 된 후에 다시 표시 하려면 알림에 대 한 트리거 동작 시퀀스 (1 단계)에서 사용할 수 있습니다. 알림이 표시 되 면, PerfView 처리 하 고 추적 출력 파일 생성에 대 한 추적 수집을 중지할 수 있습니다.

## <a name="stopping-etw-tracing"></a>ETW 추적 중지

추적 수집을 중지 하려면 단순히 사용는 `Stop collection` PerfView 창에서 단추입니다. 추적 수집을 중지 한 후 PerfView는 자동으로 ETW 이벤트를 처리 하 고 추적 출력 파일을 생성 합니다.

## <a name="examining-the-activity-log-to-get-the-delay-id"></a>지연 ID를 가져오는 활동 로그를 검사 합니다.

설명한 바와 같이 활동 로그에서 찾을 수 있습니다 `%APPDATA%\Microsoft\VisualStudio\<vs_instance_id>\ActivityLog.xml`합니다. 노드를 활동 로그에 기록 될 때마다 Visual Studio에서 검색 하는 UI 지연 확장 `UIDelayNotifications` 소스로 합니다. 이 노드에 다음 4 가지 UI 지연에 대 한 정보를 포함 합니다.

- VS 세션에서 UI 지연을 고유 하 게 식별 하는 일련 번호를 I 지연 ID
- 시작을 닫으려면 Visual Studio 세션을 고유 하 게 식별 하는 세션 ID
- UI 지연에 대 한 알림을 표시 된 여부
- UI 지연 흔히 발생 하는 확장 프로그램

```xml
<entry>
  <record>271</record>
  <time>2018/02/03 12:02:52.867</time>
  <type>Information</type>
  <source>UIDelayNotifications</source>
  <description>A UI delay (Delay ID = 0) has been detected. (Session ID=16e49d4b-26c2-4247-ad1c-488edeb185e0; Blamed extension="UIDelayR2"; Notification shown? Yes.)</description>
</entry>
```

> [!NOTE]
> 일부 UI 지연 알림이 발생 합니다. "알림 표시?"를 항상 확인 해야 따라서 오른쪽 UI 지연을 올바르게 식별 하려면 값입니다.

활동 로그에서 올바른 UI 지연을 찾은 후에 노드에 지정 된 UI 지연 ID를 적어 둡니다. 다음 단계에서 해당 ETW 이벤트에 대 한 조회 하는 ID를 사용 합니다.

## <a name="analyzing-the-etw-trace"></a>ETW 추적을 분석합니다.

다음으로, 추적 파일을 엽니다. PerfView 또는 새 인스턴스를 시작 하 고 왼쪽 위 창에 추적 파일의 위치에서에서 현재 폴더 경로 설정 하 여 동일한 인스턴스를 사용 하거나 수행할 수 있습니다.

![Perfview에서 폴더 경로 설정합니다.](media/perfview-set-path.png)

그런 다음 왼쪽된 창에서 추적 파일을 선택 하 고 마우스 오른쪽 단추 클릭 또는 상황에 맞는 메뉴에서 열기를 선택 하 여 엽니다.

> [!NOTE]
> 기본적으로 PerfView는 Zip 보관 파일을 출력합니다. Trace.zip을 열 때 자동으로 보관 압축을 푸는 하 고 추적을 엽니다. 추적 컬렉션 동안 "Zip" 확인란의 선택을 취소 하 여이 건너뛸 수 있습니다. 그러나 전송 하 고 여러 컴퓨터에서 추적을 사용 하려는 경우 좋습니다 "Zip" 확인란의 선택을 취소 합니다. 이 옵션이 없으면 Ngen 어셈블리에 대 한 필요한 Pdb에는 추적와 함께 제공 됩니다 및 Ngen 어셈블리의 기호를 대상 컴퓨터에서 확인 되지 않습니다 따라서 합니다. (참조 [이 블로그 게시물](https://blogs.msdn.microsoft.com/devops/2012/12/10/creating-ngen-pdbs-for-profiling-reports/) Ngen 어셈블리에 대 한 Pdb에 대 한 자세한 내용은.) 

PerfView 처리 하 고 추적 열에 대 일 분 정도 걸릴 수 있습니다. 추적을 열면 그 아래에서 다양 한 "보기"의 목록이 표시 됩니다.

![PerfView 추적에 대 한 요약 보기](media/perfview-summary-view-events-selected.png)

"이벤트" 보기 UI 지연의 시간 범위를 가져오려면 먼저 사용 합니다.

1. 추적에서 "이벤트" 노드를 선택 하 고 마우스 오른쪽 단추 클릭 또는 상황에 맞는 메뉴에서 열기를 선택 하 여 "이벤트" 보기를 엽니다.
2. 선택 "`Microsoft-VisualStudio/ExtensionUIUnresponsiveness`" 왼쪽된 창에서.
3. Enter 키를 누릅니다.

선택을 적용 되 고 모든 `ExtensionUIUnresponsiveness` 이벤트가 오른쪽 창에 표시 됩니다.

![이벤트 보기에서 이벤트를 선택합니다.](media/perfview-event-selection.png)

오른쪽 창에서 각 행 UI 지연에 해당합니다. 이벤트는 6 단계에서 활동 로그에서 지연 ID와 일치 해야 하는 "지연 ID" 값을 포함 합니다. 이후 `ExtensionUIUnresponsiveness` 은 종료 시 발생 이벤트의 타임 스탬프 UI 지연의 개략적인 표시 UI 지연의 종료 시간입니다. 이벤트에는 지연 기간을 포함 되어 있습니다. UI 지연 시작 될 때의 타임 스탬프를 가져올 수 종료 타임 스탬프에서 기간을 뺍니다 수 했습니다.

![UI 지연 시간 범위를 계산합니다.](media/ui-delay-time-range.png)

이전 스크린 샷에서 예를 들어 이벤트의 타임 스탬프 12,125.679 이며 지연 기간은 6,143.085 (밀리초)입니다. 그러므로
* 지연 시작은 12,125.679 6,143.085 5,982.594 = 합니다.
* UI 지연 시간 범위를 12,125.679 5,982.594입니다.

시간 범위를 있으면 म 이벤트 보기 닫았다가 "스레드 시간 (StartStop 활동)와 스택" 보기를 엽니다. 이 뷰는 다른 스레드 또는 I/o 바인딩된 작업에 UI 스레드를 차단 하는 확장 종종 단순히 대기 중 이어서에서 매우 편리 합니다. 따라서 대부분의 경우에 대 한 옵션으로는 "CPU 스택" 보기 스레드가 이후이 시간 동안 CPU 사용 하지 않는 차단 하는 데 걸린 시간이 캡처되지 않을 수 있습니다. "스레드 시간 스택" 적절히 보여 주는 차단 시간 함으로써이 문제를 해결합니다.

![PerfView 요약 뷰에서 스레드 시간 (StartStop 활동)와 스택 노드](media/perfview-thread-time-with-startstop-activities-stacks.png)

"시간 스택 스레드"를 여는 동안 보기 분석을 시작할 "devenv" 프로세스를 선택 합니다.

![스레드 UI 지연 분석에 대 한 시간 스택 뷰](media/ui-delay-thread-time-stacks.png)

"시간 스택 스레드" 보기에서 페이지의 왼쪽 위에서에서 시간 범위를 enter 키를 확인 하 고 이전 단계에서 계산에서는 시간 범위는 스택 조정 되어 되므로 값으로 설정할 수 있습니다.

> [!NOTE]
> UI 스레드 결정 (시작) 스레드 추적 컬렉션 Visual Studio를 이미 연 후에 시작 된 경우에 예상치 않은 될 수 있습니다. 그러나 (시작) UI 스레드의 스택에 첫 번째 요소는 가장 가능성이 높은 항상 devenv 다음 운영 체제 Dll (ntdll.dll 및 kernel32.dll)? 및 다음 msenv?입니다. 이 시퀀스 UI 스레드를 식별할 수 있습니다.

 ![시작 스레드를 식별합니다.](media/ui-delay-startup-thread.png)

또한만 패키지의 모듈을 포함 하는 스택에서 포함 하 여이 보기를 필터링 할 수 있습니다.

* 기본적으로 추가 하는 모든 그룹화 제거 하려면 빈 텍스트에 "GroupPats"를 설정 합니다.
* "IncPats" 기존 프로세스 필터 외에도 어셈블리 이름의 일부를 포함 하도록 설정 합니다. 이 경우 "devenv; 있어야 UIDelayR2 "입니다.

![시간 스택 스레드 보기에서 GroupPath 및 IncPath 설정](media/perfview-tts-group-path-inc-path.png)

PerfView에 코드에서 성능 병목 상태를 식별 하는 데 사용할 수 있는 도움말 메뉴 아래 지침을 설명 합니다. 또한 다음 링크는 Visual Studio 스레딩 코드를 최적화 하는 Api를 활용 하는 방법에 자세한 정보를 제공 합니다.

* [https://aka.ms/vsthreading](https://aka.ms/vsthreading)
* [https://aka.ms/vsthreadingcookbook](https://aka.ms/vsthreadingcookbook)

확장에 대 한 새 Visual Studio 정적 분석기를 사용할 수도 있습니다 (NuGet 패키지 [여기](https://www.nuget.org/packages/microsoft.visualstudio.sdk.analyzers))을 효율적으로 확장을 작성 하기 위한 모범 사례에 지침을 제공 하는 합니다. 목록을 보려면 [VS SDK 분석기](https://github.com/Microsoft/VSSDK-Analyzers/blob/master/doc/index.md) 및 [분석기 스레딩](https://github.com/Microsoft/vs-threading/blob/master/doc/analyzers/index.md)합니다.

> [!NOTE]
> 대해서 컨트롤을가지고 있지 않습니다 종속성으로 인해 응답 하지 않는 문제를 해결할 수 없는 경우 (예: 확장 UI 스레드에서 동기 VS 서비스를 호출 하는 경우)을 알려 주세요. 이 Visual Studio 파트너 프로그램의 구성원 인 개발자 지원 요청을 제출 하 여 문의할 수 있습니다. 그렇지 않은 경우 '문제를 보고' 도구를 사용 하 여 피드백 제출 하 여 포함할 `"Extension UI Delay Notifications"` 제목에서입니다. 분석의 자세한 설명도 포함 하십시오.
