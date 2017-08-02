---
title: "방법: 확장 성능 진단 | Microsoft 문서"
ms.custom: 
ms.date: 11/08/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46b0a1e3-7e69-47c9-9d8d-a1815d6c3896
caps.latest.revision: 1
author: BertanAygun
ms.author: bertaygu
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: f1226c9bd42476acc9fb57be0a6df8058174fd4d
ms.lasthandoff: 02/22/2017

---
# <a name="measuring-extension-impact-in-startup"></a>시작에서 확장 영향 측정

## <a name="focus-on-extension-performance-in-visual-studio-2017"></a>Visual Studio 2017에서 확장 성능을에 집중

고객의 의견에 따라 Visual Studio 2017 릴리스에 대 한 주요 영역 중 하나가 되었습니다 시작 및 솔루션 로드 성능. Visual Studio 플랫폼 팀으로 작업 했으므로 일반적 시작 및 솔루션 로드 성능 향상에, 하는 동안 설치 된 확장 이러한 시나리오에도 상당한 영향을 줄 수는 원격 분석 제안 합니다.

이 영향을 이해 하는 사용자를 위해 느린 확장의 사용자에 게 Visual Studio의 새로운 기능을 추가 했습니다. Visual Studio 솔루션 부하 또는 시작 저하 하는 새 확장을 감지 하면 사용자가 새 "Visual Studio 성능 관리" 대화 상자를 가리키는 IDE에 알림이 표시 됩니다. 이 대화 상자를 이전에 검색 된 확장을 찾아보려면 도움말 메뉴에서 항상 액세스할 수 있습니다.

![Visual Studio 성능 관리](~/extensibility/media/manage-performance.png)

이 문서는 확장 영향을 계산 하는 방식을 어떻게 분석할 수 있습니다 로컬로 확장 확장에 영향을 미치는 성능으로 표시 될 수 있는지 테스트를 설명 하 여 확장을 쉽게를 목표로 합니다.

## <a name="how-extensions-can-impact-startup"></a>확장 시작 영향을 줄 수는 방법

시작 성능에 영향을 줄에 대 한 확장에 대 한 가장 일반적인 방법 중 하나는 NoSolutionExists 또는 ShellInitialized 같은 알려진된 시작 UI 컨텍스트 중 하나에 자동 로드를 선택 하 여입니다. 이러한 UI 컨텍스트에 시작 하는 동안 활성화 될 및 이러한 컨텍스트를 해당 정의에 "ProvideAutoLoad" 특성을 포함 하는 모든 패키지를 로드 하 고 해당 시점에 초기화 됩니다.

확장의 영향을 측정 하는 경우 주로 중점적으로 위의 컨텍스트에서 자동 로드를 선택 하는 해당 확장에 의해 소요 된 시간입니다. 측정 한 번은 포함 되지만에 제한 되지 않습니다.

* 동기 패키지에 대 한 확장 프로그램 어셈블리 로드
* 동기 패키지에 대 한 패키지 클래스 생성자에 소요 된 시간
* 동기 패키지에 대 한 패키지 초기화 (또는 SetSite) 방법에서 소요 된 시간
* 비동기 패키지에 대 한 위의 연산이 백그라운드 스레드에서 실행 및 모니터링에서 제외 됩니다.
* 패키지 초기화 하는 동안 주 스레드에서 실행 되도록 예약 하는 모든 비동기 작업에 소요 된 시간
* 특히 초기화 셸 상황에 맞는 정품 인증 또는 셸 좀비 상태 변경 이벤트 처리기에 소요 된 시간

자동 로드 하는 패키지에 대 한 필요성을 제거 하는 데 도움이, 사용자 수 없는 확장을 사용 하거나 자동으로 로드 하는 경우에 확장 영향을 줄일 추는 보다 특정 한 경우에는 부하를 연기 하는 Visual Studio 2015에서 시작 하는 여러 기능을 추가 했습니다.

이러한 기능에 대 한 자세한 내용은 다음 문서에서 찾을 수 있습니다.

[규칙 기반 UI 컨텍스트](how-to-use-rule-based-ui-context-for-visual-studio-extensions.md): UI 컨텍스트 기반으로 구축 하는 다양 한 기반으로 하는 규칙 엔진을 사용 하면 프로젝트 형식, 버전 및 기능에 따라 사용자 지정 컨텍스트를 만들 수 있습니다. 패키지 시작; 대신 특정 기능을 사용 하 여 프로젝트의 존재와 같은 보다 구체적인 시나리오 중 로드 하려면 이러한 사용자 지정 컨텍스트를 사용할 수 있습니다. 허용 또는 [명령에 사용자 지정 컨텍스트 연결에 대 한 가시성](https://msdn.microsoft.com/en-us/library/bb166512.aspx) 프로젝트 기능 또는 사용 가능한 다음 용어는 패키지를 로드할 필요가 없도록 명령 상태 쿼리 처리기를 등록 하려면 기반 합니다.

[비동기 패키지 지원](how-to-use-asyncpackage-to-load-vspackages-in-the-background.md): Visual Studio 2015의 새로운 AsyncPackage 기본 클래스 로드 되도록 백그라운드에서 비동기적으로 패키지 로드 자동 부하 특성 또는 비동기 서비스 쿼리에 의해 요청 된 경우 Visual Studio 패키지를 사용 합니다. 이 백그라운드 로드가 확장은 백그라운드에서 초기화 되 고 시작 하 고 솔루션 로드와 같은 중요 한 시나리오에 영향을 미칠 수 없습니다 하는 동안 응답을 계속 하도록 IDE를 수 있습니다.

[비동기 서비스](how-to-provide-an-asynchronous-visual-studio-service.md): 비동기 패키지 지원으로 추가 했습니다 지원 서비스를 비동기적으로 쿼리 및 비동기 서비스를 등록할 수 있습니다. 무엇 보다도 제작 하는 대부분 비동기 쿼리에서 작업의 백그라운드 스레드에서 발생 되도록 비동기 쿼리를 지원 하기 위한 핵심 Visual Studio 서비스를 변환 합니다. SComponentModel (Visual Studio MEF 호스트)는 이제 완전히 비동기 로드를 지원 하도록 확장을 허용 하는 비동기 쿼리를 지원 되는 주요 서비스 중 하나입니다.

## <a name="reducing-impact-of-auto-loaded-extensions"></a>확장을 로드의 auto 미치는 영향을 줄이기

패키지를 자동 시작 시 로드 해야 하는 경우에 시작에 영향을 미치는 확장의 가능성을 줄이려면 패키지 초기화 하는 동안 수행 된 작업을 최소화 하는 것이 중요 합니다.

패키지 초기화를 저렴 하 게 할 수 있는 몇 가지 예제입니다.

### <a name="use-of-synchronous-package-load-instead-of-asynchronous-package-load"></a>비동기 패키지 로드 하는 대신 동기 패키지 로드 사용

동기 패키지는 기본적으로 주 스레드에서 로드 되므로, 앞에서 설명한 대로 대신 비동기 패키지 기본 클래스를 사용 하 여 자동으로 로드 패키지에 있는 확장 소유자를 좋습니다. 비동기 로드를 지원 하기 위해 프로그램 자동 로드 된 패키지를 변경 합니다도 쉽게 아래의 다른 문제를 해결 하려면.

### <a name="synchronous-filenetwork-io-requests"></a>동기 파일/네트워크 IO 요청

이상적으로 동기 파일 또는 네트워크 IO 요청 피해 야 주 스레드에서 영향력 컴퓨터 상태에 따라 달라 집니다 및 일부 경우에는 장기간에 대 한 차단할 수 있습니다.

비동기 패키지 로드 및 비동기 IO Api를 사용 하 여 이러한 경우 주 스레드를 차단 하지 않습니다 패키지 초기화 하 고 사용자가 계속 입/출력 요청 백그라운드에서 발생 하는 동안 Visual Studio와 상호 작용할 수를 확인 해야 합니다.

### <a name="early-initialization-of-services-components"></a>구성 요소 서비스의 초기 초기화

패키지 초기화에서 일반적인 패턴 중 하나에서 사용 되거나 패키지 생성자 또는 initialize 메서드에서 해당 패키지에서 제공 되는 서비스를 초기화 하입니다. 이렇게 하면 서비스를 사용 하도록 준비를 하는 동안 로드 하 고 이러한 서비스가 즉시 사용 하지 않는 경우 패키지에 불필요 한 비용을 추가할 수도 있습니다. 대신 패키지 초기화에서 수행 된 작업을 최소화 하기 위해 필요에 따라 이러한 서비스를 초기화 합니다.

패키지에서 제공 하는 글로벌 서비스에 대 한 구성 요소에 의해 요청 된 경우에 지연 서비스를 초기화 하는 함수를 사용 하는 AddService 메서드를 사용할 수 있습니다. 패키지 내에서 사용 되는 서비스에 대 한 지연을 활용할 수 있습니다<T> 또는 AsyncLazy<T> 서비스는 처음 사용할 때 초기화/쿼리할 수 있도록 합니다.

## <a name="measuring-impact-of-auto-loaded-extensions-using-perfview"></a>PerfView를 사용 하 여 확장을 로드 자동의 영향을 측정 합니다.

코드 분석 패키지 초기화를 저하 시킬 수 있는 코드 경로 식별 시킬 수 있지만, Visual Studio 시작에서 패키지 로드의 영향을 이해 하기 PerfView와 같은 응용 프로그램을 사용 하 여 추적을 활용할 수도 있습니다.

PerfView는 CPU 사용량 또는 시스템 호출 차단으로 인해 응용 프로그램에서 실행 부하 과다 경로 이해 하는 데 도움이 되는 시스템 넓은 추적 도구입니다. 다음은 간단한 예는 예제 확장 프로그램에서 사용할 수 있는 PerfView를 사용 하 여 분석에 [Microsoft 다운로드 센터](https://www.microsoft.com/en-us/download/details.aspx?id=28567)합니다.

**예제 코드:**

샘플을 기반으로이 예제는 표시 하도록 설계 되었습니다는 아래 코드에는 몇 가지 일반적인 지연 원인을 경우:

```c#
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

Visual Studio 환경에 설치 된 확장으로 설정한 후 PerfView를 열고 "수집" 메뉴에서 수집 대화 상자를 열고 시작 추적을 기록할 수 있습니다.

![perfview 수집 메뉴](~/extensibility/media/perfview-collect-menu.png)

기본 옵션 CPU 사용에 대 한 호출 스택을 제공 하 되지만 차단 시간에도 관심이 있기 때문에 활성화 해야 "스레드 시간" 스택. 설정을 준비가 되 면 "컬렉션 시작"을 클릭할 수 있으며 녹음/녹화 시작 되 면 Visual Studio를 시작 수 있습니다.

수집을 중지 전에 Visual Studio는 완전히 초기화, 주 창이 완전히 표시 되 고 볼 수 있다는 확장이 자동으로 표시 하는 UI 부분이 있으면 있는지 확인 하는 것이 좋습니다. Visual Studio는 완전히 로드 되 고 확장 프로그램은 초기화 되 면 기록 분석 추적을 중지할 수 있습니다.

**PerfView 사용 하 여 추적을 분석 합니다.**

기록이 완료 되 면 PerfView는 자동으로 추적을 열고 옵션을 확장 합니다.

이 예제의 목적에 관심이 있습니다 주로 "스레드 시간 스택" 보기 "[고급] 그룹" 아래에서 찾을 수 있습니다. 이 보기에는 CPU 시간 및 디스크 IO 또는 핸들 대기와 같은 차단 된 시간을 포함 하는 메서드에서 스레드에서 소요 된 총 시간을 표시 됩니다.

 ![스레드 시간 스택](~/extensibility/media/perfview-thread-time-stacks.png)

 "시간 스택 스레드" 보기를 여는 동안 분석을 시작 하는 "devenv" 프로세스를 선택 해야 합니다.

PerfView를 자세히 분석에 대 한 자체 도움말 메뉴에서 시간 스택 스레드를 읽는 방법에 대 한 지침에 자세히 설명 합니다. 이 예제의 목적에 대 한만 우리의 패키지 모듈 이름 및 시작 스레드 스택을 포함 하 여이 뷰를 추가로 필터링 하려고 합니다.

1. 기본적으로 추가 하는 모든 그룹화를 제거 하려면 빈 텍스트에 "GroupPats"를 설정 합니다.
2. 집합의 어셈블리 이름 일부를 포함 하는 "IncPats" 및 스레드 시작 기존 프로세스 필터 외에도입니다. 이 경우 "devenv; 있어야 시작 스레드입니다. MakeVsSlowExtension "로 설정 합니다.

이제 보기와 관련 된 확장 프로그램 어셈블리와 연결 된 비용만 표시 됩니다. 이 보기에서 언제 든 지 시작 스레드의 "Inc" (포괄 비용) 열 아래에 나열 된 필터링 된 확장에 관련 되어 있으며 시작에 미치는 영향 됩니다.

예를 들어 위의 몇 가지 흥미로운 호출 스택 것입니다.

1. System.IO 클래스를 사용 하는 IO: 이러한 프레임의 포괄적 비용 추적에 매우 많은 비용이 소요 아닐 수 있습니다는 문제의 잠재적인 원인을 이후 파일 IO 속도 차이 시스템 마다 다릅니다.

  ![시스템 io 프레임](~/extensibility/media/perfview-system-io-frames.png)

2. 다른 비동기 작업에서 대기 하는 호출 차단:이 경우 포괄 시간은 비동기 작업의 완료에 주 스레드가 차단 되는 시간을 나타냅니다.

  ![차단 호출 프레임](~/extensibility/media/perfview-blocking-call-frames.png)

영향을 확인 하는 데 유용 합니다 추적에는 다른 보기 중 하나는 "이미지 부하 스택" 됩니다. "시간 스택 스레드" 보기에 적용 될 때 동일한 필터를 적용할 수 있으며 자동 로드 패키지에서 실행 되는 코드 때문에 로드 된 모든 어셈블리를 찾을 수 있습니다.

것 처럼 각 추가 어셈블리 상당히 느린 컴퓨터 다시 시작이 느려질 수 있는 추가 디스크 I/O가 관련 패키지 초기화 루틴 내의 로드 된 어셈블리의 수를 최소화 하기 위해 중요 합니다.

## <a name="summary"></a>요약

Visual Studio의 시작에서 지속적으로 피드백을 얻게 영역 중 하나가 되었습니다. 앞서 설명한 것 처럼 이러한 목표 달성 모든 사용자가 구성 요소 및 확장을 설치 해야 하는 것에 관계 없이 발생 하는 일관 된 시작 되며 목표를 달성 하는 데 도움이 되는 데 확장 소유자를 사용 하려고 합니다. 위 지침 시작 시에는 확장 영향을 이해 하 고 자동으로 로드 하거나 사용자 생산성에 미치는 영향을 최소화 하기 위해 비동기적으로 로드할 필요가 방지 하거나 유용 합니다.
