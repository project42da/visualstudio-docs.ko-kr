---
title: "방법: 확장 성능 진단 | Microsoft Docs"
ms.custom: 
ms.date: 11/08/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46b0a1e3-7e69-47c9-9d8d-a1815d6c3896
caps.latest.revision: "1"
author: BertanAygun
ms.author: bertaygu
manager: ghogen
ms.workload: bertaygu
ms.openlocfilehash: 1d1034cce8b2fced5af48a0a4bfa8620b56994e4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="measuring-extension-impact-in-startup"></a>시작에 확장 영향을 측정합니다.

## <a name="focus-on-extension-performance-in-visual-studio-2017"></a>Visual Studio 2017에서 확장 성능을에 집중

고객의 의견에 따라 Visual Studio 2017 릴리스에 대 한 주요 영역 중 하나는 되었습니다 시작 및 솔루션 로드 성능. Visual Studio 플랫폼 팀으로 다루었습니다 일반적 시작과 솔루션 로드 성능 향상에, 하는 동안 설치 된 확장 한 시나리오에 상당한 영향을 줄 있을 수도 우리의 원격 분석 제안 합니다.

사용자가이 영향을 이해 하려면 느린 확장의 사용자에 게 Visual Studio의 새로운 기능을 추가 했습니다. Visual Studio 솔루션 부하 또는 시작 저하 하는 새 확장을 감지 하면 사용자가 새 "Visual Studio 성능 관리" 대화 상자에이 가리키는 IDE에 알림이 표시 됩니다. 이 대화 상자는 항상 이전에 검색 된 확장을 탐색 하려면 도움말 메뉴에서 액세스할 수 있습니다.

![Visual Studio 성능 관리](media/manage-performance.png)

이 문서는 확장 영향은 어떻게 계산 및 어떻게를 분석할 수 있습니다 로컬로 확장 확장에 영향을 주지 성능으로 표시 될 수 있는 경우에 테스트를 설명 하는 확장 개발자 통한 효율적인 방식 합니다.

## <a name="how-extensions-can-impact-startup"></a>확장이 시작에 미치는 영향

시작 성능에 영향을 줄에 대 한 확장에 대 한 가장 일반적인 방법 중 하나에서 NoSolutionExists 또는 ShellInitialized 같은 알려진된 시작 UI 컨텍스트 중 하나가 자동 부하를 선택 하 여입니다. 이러한 UI 컨텍스트가 시작 하는 동안 활성화 될 및 이러한 컨텍스트를 해당 정의에 "ProvideAutoLoad" 특성을 포함 하는 모든 패키지를 로드 하 고 해당 시점에 초기화 됩니다.

확장의 영향을 측정 하는 경우 주로 집중 위의 컨텍스트에서 자동 부하를 위해 선택 하는 확장에서 소요 된 시간입니다. 측정 시간 포함 것에 제한 되지 않습니다.

* 동기 패키지에 대 한 확장 프로그램 어셈블리 로드
* 동기 패키지에 대 한 패키지 클래스 생성자에 소요 된 시간
* Initialize (또는 SetSite) 메서드를 동기 패키지에 대 한 패키지에 소요 된 시간
* 비동기 패키지에 대 한 위의 작업 백그라운드 스레드에서 실행 하 고 모니터링에서 제외 됩니다.
* 패키지 초기화 하는 동안 주 스레드에서 실행 되도록 예약 하는 비동기 작업에 소요 된 시간
* 이벤트 처리기를 초기화 하는 셸 컨텍스트 활성화 특히 또는 셸 좀비 상태 변경에 소요 된 시간
* Visual Studio 2017 업데이트 3에서 부터는 먼저 셸 초기화 되기 전에 유휴 호출에 걸린 시간을 모니터링 합니다. 또한 유휴 처리기에서 장기 작업 인해 응답 하지 않는 IDE 하 고 사용자가 체감된 시작 시간에 영향을 합니다.

패키지 자동 부하에 대 한 필요성을 제거 하는 정보를 보려면 사용자 수 없는 초과를 로드할 때 확장을 사용 하거나 확장 영향을 더 특정 보다 구체적인 사례에는 부하를 연기 하는 Visual Studio 2015에서 시작 하는 여러 기능을 추가 했습니다. 자동으로 합니다.

이러한 기능에 대 한 자세한 내용은 다음 문서에서 찾을 수 있습니다.

[규칙 기반 UI 컨텍스트](how-to-use-rule-based-ui-context-for-visual-studio-extensions.md): UI 컨텍스트 기반을 두고 다양 한 규칙 기반 엔진을 사용 하면 프로젝트 형식, 버전 및 기능에 따라 사용자 지정 컨텍스트를 만들 수 있도록 합니다. 패키지 시작; 대신 특정 기능을 사용 하 여 프로젝트의 존재 여부와 같은 보다 구체적인 시나리오 중 로드 하려면 이러한 사용자 지정 컨텍스트를 사용할 수 있습니다. 허용 또는 [와 사용자 지정 컨텍스트 연결에 대 한 가시성 명령](visibilityconstraints-element.md) 명령 상태 쿼리 처리기를 등록 하려면 프로젝트 기능 또는 패키지를 로드 하려면 필요가 없도록 표시 되어 있는 다른 용어 기반 합니다.

[비동기 패키지 지원](how-to-use-asyncpackage-to-load-vspackages-in-the-background.md): Visual Studio 2015의 새로운 AsyncPackage 기본 클래스가 로드 되도록 백그라운드에서 비동기적으로 자동 부하 특성 또는 비동기 서비스 쿼리에서 패키지 로드를 요청한 경우 Visual Studio 패키지를 수 있습니다. . 이 백그라운드 로드를 사용 하면 IDE에서이 확장은 백그라운드에서 초기화 되 고 시작 하 고 솔루션 로드 같은 중요 시나리오에 영향을 미칠 수 없게 하는 동안 응답성이 계속 합니다.

[비동기 서비스](how-to-provide-an-asynchronous-visual-studio-service.md): 비동기 패키지 지원도 지원이 추가 되었습니다 서비스를 비동기적으로 쿼리 및 비동기 서비스를 등록할 수 있습니다. 더욱 중요 한 제작 하는 대부분 비동기 쿼리를 통해 작업의 백그라운드 스레드에서 발생 되도록 비동기 쿼리를 지원 하기 위한 핵심 Visual Studio 서비스를 변환 합니다. SComponentModel (Visual Studio MEF 호스트)는 이제 완전히 비동기 로드를 지원 하도록 확장을 허용 하려면 비동기 쿼리를 지원 되는 주요 서비스 중 하나입니다.

## <a name="reducing-impact-of-auto-loaded-extensions"></a>확장을 로드 자동의 영향을 줄이기

패키지를 자동 시작 시 로드 해야 하는 경우에 시작에 영향을 주지 확장의 가능성을 줄이려면 패키지 초기화 하는 동안 수행 되는 작업을 최소화 해야 합니다.

패키지 초기화 비용이 많이 들 수를 일으킬 수 있는 몇 가지 예제입니다.

### <a name="use-of-synchronous-package-load-instead-of-asynchronous-package-load"></a>비동기 패키지 로드 하는 대신 동기 패키지 로드 사용

기본적으로 주 스레드에서 동기 패키지가 로드 되 면 때문에 앞에서 설명한 대로 대신 비동기 패키지 기본 클래스를 사용 하 여 자동 로드 패키지가 확장 소유자를 좋습니다. 비동기 로딩을 지원 하도록 자동 로드 된 패키지는 변경는 또한 쉽게 아래의 다른 문제를 해결 하려면.

### <a name="synchronous-filenetwork-io-requests"></a>동기 파일/네트워크 IO 요청

이상적으로 동기 파일 또는 네트워크 IO 요청 피해 야 주 스레드에서 영향력 컴퓨터 상태에 따라 달라 집니다 및 경우에 따라 시간이 오래 동안 차단할 수 있습니다.

비동기 패키지 로드 및 비동기 IO Api를 사용 하 여 패키지 초기화는 이러한 경우 주 스레드를 차단 하지 않습니다 및 사용자가 계속 입/출력 요청 백그라운드에서 발생 하는 동안 Visual Studio와 상호 작용할 수 있는지 확인 해야 합니다.

### <a name="early-initialization-of-services-components"></a>초기 서비스, 구성 요소 초기화

패키지 초기화의 일반적인 패턴 중 하나에서 사용 하는 또는 패키지 생성자 또는 초기화 메서드에서 해당 패키지에서 제공 서비스를 초기화 하는 것입니다. 이렇게 하면 서비스를 사용 하도록 준비를 하는 동안 불필요 한 비용이를 로드 하는 해당 서비스 즉시 사용 되지 않는 경우 패키지를 추가할 수도 있습니다. 대신 패키지 초기화에서 수행 된 작업을 최소화 하기 위해 필요에 따라 이러한 서비스를 초기화 합니다.

패키지에서 제공 하는 글로벌 서비스에 대 한 지연 구성 요소에 의해 요청 된 경우에 서비스를 초기화 하는 함수를 사용 하는 AddService 메서드를 사용할 수 있습니다. 패키지 내에서 사용 되는 서비스에 대 한 Lazy를 사용할 수 있습니다<T> 또는 AsyncLazy<T> 서비스는 처음 사용할 때 초기화 하거나 쿼리할 수 있도록 합니다.

## <a name="measuring-impact-of-auto-loaded-extensions-using-activity-log"></a>활동 로그를 사용 하 여 확장을 로드 자동의 영향을 측정 합니다.

Visual Studio 2017 업데이트 3부터, Visual Studio 작업 로그는 시작 및 솔루션 로드 하는 동안 패키지의 성능 영향에 대 한 항목을 이제 포함 됩니다. 이러한 측정값을 보려면 /log 스위치와 함께 Visual Studio를 시작 하 고 ActivityLog.xml 파일을 열려면 해야 합니다.

활동 로그에서 항목 "Visual Studio 성능 관리" 소스 아래에 배치 하 고 다음과 같습니다.

```Component: 3cd7f5bf-6662-4ff0-ade8-97b5ff12f39c, Inclusive Cost: 2008.9381, Exclusive Cost: 2008.9381, Top Level Inclusive Cost: 2008.9381```

이 GUID "3cd7f5bf-6662-4ff0-ade8-97b5ff12f39c" Visual Studio의 시작에 2008 밀리초가 소요 된 해당 패키지를 의미 합니다. 참고 savigs 사용자 그렇게 할 패키지의 영향을 계산할 때 Visual Studio의 주 수와 상위 수준 비용과 고려 하는 해당 패키지에 대 한 확장을 비활성화 하 참조 하십시오.

## <a name="measuring-impact-of-auto-loaded-extensions-using-perfview"></a>PerfView를 사용 하 여 확장을 로드 자동의 영향을 측정 합니다.

코드 분석 패키지 초기화 속도가 느려질 수 있는 코드 경로가 식별 시킬 수 있지만, PerfView와 같은 응용 프로그램을 사용 하 여 Visual Studio 시작 시에 패키지 로드의 영향을 파악 하 여 추적을 사용할 수 있습니다.

PerfView는 CPU 사용량 또는 시스템 호출 실행을 차단으로 인해 응용 프로그램에서 실행 부하 과다 경로 이해 하는 데 도움이 되는 시스템 넓은 추적 도구. 다음은 분석에서 사용할 수 있는 PerfView를 사용 하 여 예제 확장 프로그램에는 빠른 예제는 [Microsoft 다운로드 센터](https://www.microsoft.com/en-us/download/details.aspx?id=28567)합니다.

**예제 코드:**

이 샘플을 기반으로이 예제는 아래 코드에서 표시 하도록 설계 된 몇 가지 일반적인 지연 원인을 대/소문자:

```csharp
protected override void Initialize()
{
    // Initialize a class from another assembly as an example
    MakeVsSlowServiceImpl service = new MakeVsSlowServiceImpl();

    // Costly work in main thread involving file IO
    string systemPath = Environment.GetFolderPath(Environment.SpecialFolder.Windows);
    foreach (string file in Directory.GetFiles(systemPath))
    {
        DateTime creationDate = File.GetCreationTime(file);
    }

    // Costly work after shell is initialized. This callback executes on main thread
    KnownUIContexts.ShellInitializedContext.WhenActivated(() =>
    {
        DoMoreWork();
    });

    // Start async work on background thread
    DoAsyncWork().Forget();
}

private async Task DoAsyncWork()
{
    // Switch to background thread to do expensive work
    await TaskScheduler.Default;
    System.Threading.Thread.Sleep(500);
}

private void DoMoreWork()
{
    // Costly work
    System.Threading.Thread.Sleep(500);
    // Blocking call to an asynchronous work.
    ThreadHelper.JoinableTaskFactory.Run(async () => { await DoAsyncWork(); });
}
```

**PerfView 사용 하 여 추적을 기록 합니다.**

Visual Studio 환경 확장 설치 프로그램을 설정 하면 일단 PerfView를 열고 "수집" 메뉴에서 수집 대화 상자를 열어 시작의 추적을 기록할 수 있습니다.

![perfview 수집 메뉴](media/perfview-collect-menu.png)

기본 옵션 CPU 사용에 대 한 호출 스택을 제공 하 되지만 차단 시간 역시 연습, 이후도 활성화 해야 "스레드 시간" 스택. 설정을 준비가 되 면 "컬렉션 시작"을 클릭 하 고 기록 시작 되 면 Visual Studio를 시작할 수 있습니다.

컬렉션을 중지 하기 전에 Visual Studio 완전히 초기화 된, 주 창이 모두 표시 하며 확장 프로그램에 자동으로 표시 하는 UI 부분이 있으면 표시도 됩니다 되었는지 확인 하려고 합니다. Visual Studio가 완전히 로드 하 고 초기화 될 확장 프로그램을 기록 분석 추적을 중지할 수 있습니다.

**PerfView 사용 하 여 추적을 분석 합니다.**

기록이 완료 되 면 PerfView는 자동으로 추적을 열고 옵션을 확장 합니다.

이 예제에서는 우리는 "고급 그룹" 아래에서 찾을 수 있는 "시간 스택 스레드" 보기에서 주로 수집 합니다. 이 보기는 CPU 시간 및 디스크 IO 또는 대기 핸들에 같은 차단 된 시간을 포함 하는 메서드에서 스레드에 소요 된 총 시간을 표시 됩니다.

 ![스레드 시간 스택](media/perfview-thread-time-stacks.png)

 "시간 스택 스레드" 보기를 여는 동안 "devenv" 프로세스 분석을 시작 하도록 선택 해야 합니다.

PerfView에 읽을 스레드를 자세히 분석에 대 한 자체 도움말 메뉴에서 시간 스택 하는 방법에 대 한 지침을 설명 합니다. 이 예제에서는 우리의 패키지 모듈 이름 및 시작 스레드가 스택을 포함 하 여이 보기를 추가로 필터링 하려고 합니다.

1. 기본적으로 추가 하는 모든 그룹화 제거 하려면 빈 텍스트에 "GroupPats"를 설정 합니다.
2. 집합 "IncPats" 어셈블리 이름의 일부를 포함 하 고 스레드 시작 외에도 기존 프로세스 필터입니다. 이 경우 "devenv; 있어야 시작 스레드입니다. MakeVsSlowExtension "입니다.

이제는 뷰 확장와 관련 된 어셈블리와 관련 된 비용을만 표시 됩니다. 이 보기에서 언제 든 지 시작 스레드의 "Inc" (포괄 비용) 열 아래에 필터링 된 확장 관련 되어 있고 시작에 미치는 영향 됩니다.

몇 가지 흥미로운 호출 위의 예제에 대 한 스택 것입니다.

1. System.IO 클래스를 사용 하는 IO: 프레임 포괄 비용 추적에서 비용이 매우 많이 들 수 있지만, 이러한 되므로 문제의 잠재적인 원인을 파일 IO 속도 시스템 마다 달라 집니다.

  ![시스템 io 프레임](media/perfview-system-io-frames.png)

2. 다른 비동기 작업에서 대기 하는 호출 차단:이 경우 포괄 시간은 비동기 작업의 완료 되 면 주 스레드는 차단 하는 시간을 나타냅니다.

  ![차단 호출 프레임](media/perfview-blocking-call-frames.png)

영향을 확인 하려면 유용한 여러 가지 추적에 다른 뷰 중 하나는 "이미지 부하 스택" 됩니다. "시간 스택 스레드" 보기에 적용 될 때 동일한 필터를 적용 하 고 자동 로드 된 패키지에서 실행 한 코드 때문에 로드 된 모든 어셈블리를 찾을 수 있습니다.

각 추가 어셈블리를 상당히 느린 컴퓨터 다시 시작 속도가 느려질 수 있는 추가적인 디스크 I/O를 해야 하는 대로 패키지 초기화 루틴 내 로드 된 어셈블리의 수를 최소화 하는 것이 유용 합니다.

## <a name="summary"></a>요약

Visual Studio의 시작에 지속적으로 피드백을 구했습니다 영역 중 하나 되었습니다. 앞서 설명한 것 처럼 이러한 목표 모든 사용자가 구성 요소 및 확장과 설치한에 관계 없이 발생 하 여 일관 된 시작 되며 그 목표를 달성 하는 데 도움이 되는 데 확장 소유자와 작동 하도록 하려는. 위 지침 시작 시에는 확장 영향을 이해 하 고 자동으로 로드 하거나 사용자 생산성에 미치는 영향을 최소화 하기 위해 비동기적으로 로드할 필요가 방지 하거나 유용 합니다.
