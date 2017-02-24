---
title: "Visual Studio 2017 RC의 새로운 기능 | Microsoft 문서"
ms.custom: 
ms.date: 12/13/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.StartPage.WhatsNew
helpviewer_keywords:
- Visual Studio, what's new
- what's new [Visual Studio]
ms.assetid: 7307e180-ba28-4774-8a43-cbb980085a71
author: TerryGLee
ms.author: tglee
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 4fb097ab0ee0d45fd5727e3170db3393392abf23
ms.openlocfilehash: dc1941fd755c28039560b608733067b1da365c3a

---
# <a name="what39s-new-in-visual-studio-2017"></a>Visual Studio 2017의 새로운 기능
웹, Windows 스토어, 데스크톱, Android 및 iOS를 위한 최고의 앱과 게임을 만들 수 있는 개발자 생산성 도구, 클라우드 서비스 및 확장의 통합 모음인 Visual Studio 2017 RC를 시작합니다.  

최신 Visual Studio 버전의 이번 RC(릴리스 후보)에서는 성능과 생산성 향상에 집중했습니다. 성능 측면에서는 Visual Studio 시작 시간이 단축되고, 응답성이 향상되고, 이전보다 메모리 사용량이 줄었습니다. 생산성 측면에서는 Visual Studio를 사용하는 동안 효율성을 높이는 데 도움이 되는 새로운 기능이나 업데이트된 기능이 추가되었습니다.

> [!TIP]
> 새로운 RC의 실행 과정을 보려면 Channel 9에서 [Visual Studio의 새로운 기능](https://channel9.msdn.com/events/connect/2016/159) 비디오를 시청하세요.   

변경 내용의 대략적인 요약은 다음과 같습니다.

* **향상된 생산성**. 코드 탐색, IntelliSense, 리팩터링, 코드 수정, 디버깅이 향상되어 언어와 플랫폼에 상관없이 빠르고 간편하게 일상 작업을 할 수 있습니다. 또한 DevOps를 적용하는 팀에서 Visual Studio 2017을 사용하면 Live Unit Testing, 실시간 아키텍처 종속성 유효성 검사와 같은 새로운 개념의 실시간 기능으로 코드 흐름을 빨리 전개하고 개발자 내부 루프를 간소화할 수 있습니다.
* **재정의된 기본 사항**.  초점을 재정비하여 개발자가 일상적인 기본 작업을 더 효율적으로 할 수 있도록 했습니다. 그 일환으로, 개발자의 요구에 맞게 경량으로 설치하거나 모듈형으로 설치할 수 있는 새로운 개념의 설치 방식부터, 시작에서 종료까지 속도가 더 빨라진 IDE, 프로젝트나 솔루션 없이 모든 코드를 보고 편집하고 디버그할 수 있는 새로운 방법까지 Visual Studio 2017은 개발자가 큰 그림에 집중할 수 있도록 돕습니다.
* **간소화된 Azure 개발**. 기본 제공 Azure 도구 모음을 통해 개발자가 Microsoft Azure 기반의 클라우드 우선 응용 프로그램을 손쉽게 만들 수 있습니다. Visual Studio를 사용하면 IDE에서 직접 Microsoft Azure의 응용 프로그램과 서비스를 구성, 빌드, 디버그, 패키징 및 배포할 수 있습니다.
* **별&5;개 모바일 개발**. Visual Studio 2017은 고급 디버깅 도구와 프로파일링 도구, 단위 테스트 생성 기능이 있는 것은 물론 Xamarin도 갖추고 있기 때문에 개발자가 Android, iOS, Windows용 모바일 앱을 그 어느 때보다 빠르고 쉽게 빌드하고 연결하고 세부 조정할 수 있습니다. 그뿐만 아니라 개발자는 Visual Studio에서 Apache Cordova 또는 Visual C++ 플랫폼 간 라이브러리 개발로 모바일 앱을 개발할 수도 있습니다.  

가장 두드러진 변경 내용에 대한 자세한 내용은 다음과 같습니다.

> [!NOTE]
> Visual Studio 2017 RC 및 후속 RC 새로 고침에서 추가된 새로운 기능의 전체 목록은 [릴리스 정보](https://www.visualstudio.com/news/vs2015-vs)를 참조하세요. 문제 및 해결 방법 목록은 릴리스 정보의 [알려진 문제](https://www.visualstudio.com/news/vs2015-vs#knownissues) 섹션을 참조하세요.   

## <a name="performance-improvements"></a>성능 향상

### <a name="a-new-setup-experience"></a>새로운 설치 환경  
[Visual Studio Enterprise 2017 RC 다운로드](https://aka.ms/vs/15/preview/vs_enterprise) 또는 [Visual Studio 시스템 요구 사항 확인](https://www.visualstudio.com/en-us/productinfo/vs2017-system-requirements-vs)

 필요할 때 필요한 기능만 설치하기 쉽도록 Visual Studio 설치 환경이 새롭게 디자인되었습니다. 시스템에 미치는 영향을 최소화하여 Visual Studio가 더 빨리 설치되도록 최소 사용 공간도 줄었습니다. 또한 완전히 제거됩니다.

 Visual Studio를 설치할 때 나타나는 가장 중요한 변화는 새로운 설치 환경입니다. **작업** 탭에는 .NET 데스크톱 개발에서 R, Python 및 F#을 사용한 데이터 과학에 이르기까지 모든 것을 아우르는 공통 프레임워크, 언어 및 플랫폼을 나타내도록 그룹화된 설치 옵션이 표시됩니다.  

 ![Visual Studio 2017 RC 설정 대화 상자](../ide/media/willow1.png "VS2017RC_Setup_screen")

필요한 작업을 선택하고, 필요한 경우 변경합니다. 최소 설치는 크기가 몇백 MB에 불과하지만 여전히 소스 코드 제어와 함께&20;개가 넘는 언어에 대한 기본 코드 편집 지원 기능이 포함되어 있습니다.

Visual Studio를 설치하는 다양한 방법도 추가되었습니다. 작업을 사용하는 대신 사용자 고유의 구성 요소를 선택하고 싶으세요? 설치 관리자에서 **개별 구성 요소** 탭을 선택하면 됩니다. 또한 Windows 언어 옵션을 변경하지 않고도 언어 팩을 설치하고 싶으세요? 설치 관리자의 **언어 팩** 탭을 선택합니다.  

안내하는 단계별 지침을 포함하여 새로운 설치 환경에 대한 자세한 내용은 [Visual Studio 설치](../install/install-visual-studio.md) 페이지를 참조하세요.


### <a name="start-visual-studio-faster"></a>더 빨리 Visual Studio 시작
Visual Studio에서 IDE 시작 시간이 느린 것을 감지하면 가속화하는 데 도움이 되는 새로운 Visual Studio 성능 센터가 제공됩니다. 성능 센터에는 IDE 시작을 지연시키는 모든 확장 및 도구 창이 표시됩니다. 성능 센터를 사용하여 확장 시작 시간 또는 시작 시 도구 창을 열지 여부를 결정하여 시작 성능을 개선할 수 있습니다.

### <a name="decrease-solution-load-time"></a>솔루션 로드 시간 감소
100개 이상의 프로젝트가 포함된 솔루션에서 작업한다고 해서 동시에 모든 파일이나 프로젝트에서 작업해야 하는 것은 아닙니다. 이제 Visual Studio에서 모든 프로젝트가 로드되기를 기다리지 않고 편집 및 디버그할 수 있습니다. 관리되는 프로젝트에서 이 작업을 시도해보려면 도구-> 옵션-> 프로젝트 및 솔루션에서 **경량 솔루션 로드**를 켭니다.

  ![Visual Studio 2017 RC의 옵션 대화 상자](../ide/media/vs2017ide-LightweightSolutionLoad.PNG "VS2017RC 옵션 대화 상자 - 경량 솔루션 로드")

### <a name="faster-on-demand-loading-of-extensions"></a>요청 시 더 빠르게 확장 로드
아이디어는 간단합니다. Visual Studio를 시작할 때가 아니라 필요할 때 확장을 로드합니다. 먼저, Python 및 Xamarin 확장이 요청 시 로드되도록 이동되었으며, Visual Studio와 함께 제공되는 모든 확장 및 타사 공급업체에서 제공하는 확장도 이 모델로 이동하고 있습니다. 어떤 확장이 시작, 솔루션 로드 및 입력 성능에 영향을 주는지 궁금하세요? 이 정보는 도움말-> Visual Studio 성능 관리에서 확인할 수 있습니다.

  ![Visual Studio 2017 RC의 옵션 대화 상자](../ide/media/vs2017ide-ManageVSperf.png "VS2017RC 도움말 대화 상자 - 성능 관리")

## <a name="productivity-improvements"></a>생산성 향상

### <a name="sign-in-across-multiple-accounts"></a>여러 계정에 로그인  
팀 탐색기, Azure 도구, Windows 스토어 게시 등의 Microsoft 개발자 도구에서 사용자 계정을 공유할 수 있도록 하는 새로운 ID 서비스가 Visual Studio 2017 RC에 도입되었습니다.

또한 로그인 상태를 더 오래 유지할 수 있습니다. 12시간마다 다시 로그인하지 않아도 됩니다. 자세한 내용은 [Fewer Visual Studio Sign-in Prompts](https://blogs.msdn.microsoft.com/visualstudio/2016/08/15/fewer-visual-studio-sign-in-prompts/)(Visual Studio 로그인 프롬프트 횟수 감소) 블로그 게시물을 참조하세요.

### <a name="manage-your-extensions-with-roaming-extensions-manager"></a>로밍 중인 확장 관리자를 사용하여 확장 관리
이제 Visual Studio에 로그인할 때 즐겨 찾는 확장으로 각 개발 환경을 더 쉽게 설정할 수 있습니다. 새로운 로밍 중인 확장 관리자는 클라우드에 동기화된 목록을 만들어 즐겨 찾는 모든 확장을 추적합니다.  

Visual Studio의 확장 목록을 보려면 도구 > 확장 및 업데이트를 클릭한 다음 로밍 중인 확장 관리자를 클릭합니다.

![Visual Studio 2017 - 확장 및 업데이트 대화 상자](../ide/media/vs2017ide-ExtensionsAndUpdates.png "Visual Studio 2017 - 도구 > 확장 및 업데이트 대화 상자")

로밍 중인 확장 관리자는 설치하는 모든 확장을 추적하지만 로밍 목록에 추가할 확장을 선택할 수 있습니다.

![Visual Studio 2017 - 확장 및 업데이트 대화 상자](../ide/media/vs2017ide-RoamingExtensionManager.png "Visual Studio 2017 - 로밍 중인 확장 관리자")

로밍 중인 확장 관리자를 사용하는 경우 3개의 아이콘 형식이 목록에 표시됩니다.
* ![로밍 아이콘](../ide/media/vs2017ide-roamedicon.png "로밍 아이콘") ***로밍 아이콘***: 이 로밍 목록에 포함되어 있지만 컴퓨터에 설치되지 않은 확장입니다.
  **다운로드** 단추를 사용하여 이러한 확장을 설치할 수 있습니다.
* ![로밍 및 설치 아이콘](../ide/media/vs2017ide-roamedinstalledicon.png "로밍 및 설치 아이콘") ***로밍 및 설치 아이콘***: 이 로밍 목록에 포함되어 있고 개발 환경에 설치된 모든 확장입니다.
  로밍하지 않도록 결정하는 경우 **로밍 중지** 단추를 사용하여 이러한 확장을 제거할 수 있습니다.
* ![설치 아이콘](../ide/media/vs2017ide-installedicon.png "설치 아이콘") ***설치 아이콘***: 이 환경에 설치되어 있지만 로밍 목록에 포함되지 않은 모든 확장입니다.
  **로밍 시작** 단추를 사용하여 로밍 목록에 확장을 추가할 수 있습니다.

이러한 아이콘은 목록의 현재 상태를 보여 줍니다. 어떠한 확장이든 원하는 상태로 사용할 수 있으므로 필요에 따라 직접 사용자 지정할 수 있으며 자동으로 사용자 지정되게 할 수도 있습니다. 로그인한 동안 다운로드하는 모든 확장은 **로밍 및 설치**로 목록에 추가되며 로밍 목록에 포함되어 모든 컴퓨터에서 액세스할 수 있게 됩니다.

### <a name="experience-live-architecture-dependency-validation-and-live-unit-testing"></a>라이브 아키텍처 종속성 유효성 검사 및 Live Unit Testing 경험

Visual Studio Enterprise 2017 RC에서 종속성 유효성 검사 다이어그램( 레이어 다이어그램이라고도 함)을 설정한 경우 이제 코드 편집기에서 코드를 입력할 때 아키텍처 종속성 규칙 위반의 실시간 알림을 받을 수 있습니다.

오류 목록에 오류가 표시되고, 텍스트 편집기의 물결선은 정확한 위반 위치를 보여 줍니다. 이제 원치 않는 종속성이 도입될 가능성이 줄었습니다.

![라이브 아키텍처 유효성 검사](../ide/media/vs2017ide-LiveArchitectureDepedendencyValidation.png "라이브 아키텍처 종속성 유효성 검사")

#### <a name="live-unit-testing"></a>Live Unit Testing

Live Unit Testing은 Visual Studio Enterprise Edition에만 새로 도입된 기능입니다. 이 기능은 코딩하는 동안 단위 테스트 결과와 코드 검사를 편집기에서 시각화합니다. .NET Framework용 C#/VB 프로젝트에 사용할 수 있고 MSTest, xUnit, NUnit의 세 가지 테스트 프레임워크를 지원합니다.

### <a name="visual-studio-ide-enhancements"></a>Visual Studio IDE 향상
#### <a name="interact-with-git"></a>Git과 상호 작용:
Visual Studio IDE의 아래쪽 모서리에 있는 컨트롤을 사용하여 프로젝트를 Git에 빠르게 커밋 및 게시하고 Git 리포지토리를 관리할 수 있습니다.

![Visual Studio 2017 RC 설정 대화 상자](../ide/media/vsIDE-GitInteraction.png "Git-tools-in-the-VS2017RC-IDE")

#### <a name="view-and-navigate-code-with-structure-visualizer"></a>구조 시각화 도우미를 사용하여 코드 보기 및 탐색:
Visual Studio 코드 편집기에서 구조 시각화 도우미라는 새로운 기능을 사용할 수 있습니다. 이 기능은 중첩된 코드 영역 사이에 세로 안내선을 표시하여 쉽게 코드를 보고 탐색할 수 있도록 합니다. 이 기능은 모든 TextMate 지원 언어와 Visual C#, Visual Basic 및 XAML에 사용할 수 있습니다.

![Visual Studio 2017 RC 설정 대화 상자](../ide/media/vsIDE-StructureVisualizer.png "Structure-Visualizer-in-VS2017RC")

#### <a name="experience-an-improved-navigate-to"></a>향상된 탐색 경험:
탐색 기능이 향상되었습니다. 탐색 창이 간단해졌고, 코드 검색 범위를 좁힐 수 있는 추가 필터 문자 지원이 추가되었습니다.

#### <a name="create-apps-in-even-more-programming-languages"></a>더 많은 프로그래밍 언어로 앱 만들기:
이전 버전보다 많은 프로그래밍 언어를 사용하여 Visual Studio에서 앱을 만들 수 있으며, 솔루션과 프로젝트는 더 이상 필요하지 않습니다. 사용자 코드에 구문 색 지정, 기본 문 완성, 경우에 따라 탐색 및 기타 지원이 제공됩니다. 원하는 언어가 지원되지 않는 경우 TextMate 문법을 사용하여 지원을 만들 수 있습니다.

### <a name="visual-c"></a>Visual C++
Visual Studio 2017 RC에는 Visual C++ 환경에 대한 많은 업데이트와 수정이 포함되었습니다. 컴파일러 및 도구에서 250개 이상의 버그와 보고된 문제가 해결되었으며, 그 중 상당수는 고객이 [Microsoft Connect](https://connect.microsoft.com/VisualStudio "Microsoft Connect")를 통해 제출한 것들입니다.

또한 Visual Studio와 함께 C++ 핵심 지침 배포, C++11 및 C++ 기능에 대한 향상된 지원을 추가하여 컴파일러 업데이트, C++ 라이브러리에서 기능 추가 및 업데이트, C++ IDE, 설치 작업 등의 성능 향상을 포함하여 여러 기능이 향상되었습니다.

자세한 내용은 [Visual 2017 RC의 Visual C++용 새로운 기능](/cpp/top/what-s-new-for-visual-cpp-in-visual-studio) 페이지를 참조하세요.  


### <a name="debugging-and-diagnostics"></a>디버깅 및 진단
디버깅이 이제 더 빨라지고 편집할 때 지연이 발생하지 않습니다.

예: 이전 버전의 Visual Studio에서는 다음 디버그 세션에서 사용할 프로세스를 백그라운드에서 준비하여 더 빠르게 디버그할 수 있도록 WPF, Windows Forms 및 관리되는 콘솔 프로젝트에 대한 호스팅 프로세스가 도입되었습니다. 좋은 의도로 도입된 이 기능으로 인해 디버깅을 중지하거나 디버그 세션이 종료된 후 Visual Studio를 사용할 때 Visual Studio가 몇 초 동안 일시적으로 응답하지 않는 문제가 발생했습니다.

Visual Studio 2017에서는 호스팅 프로세스를 해제하고 디버깅을 최적화하여, 호스팅 프로세스 없이도 똑같이 빠르게 디버그할 수 있고 호스팅 프로세스를 사용한 적이 없는 프로젝트(예: ASP.NET, 유니버설 Windows 및 C++ 프로젝트)의 경우에는 더 빨리 디버그됩니다.

#### <a name="run-to-click"></a>실행하려면 클릭:
이제 디버그하는 동안 코드 줄 옆에 있는 아이콘을 클릭하여 해당 줄을 실행할 수 있습니다. 더 이상 코드를 실행하고 원하는 줄에서 중지하기 위해 임시 중단점을 설정하여 여러 단계를 수행할 필요가 없습니다.

![Visual Studio 2017 RC 디버그 - 실행하려면 클릭](../ide/media/vs2017ide-RunToClick.png "Visual Studio 2017 디버그 및 진단의 실행하려면 클릭")

#### <a name="the-new-exception-helper"></a>새 예외 도우미:

새 예외 도우미를 사용하여 비모달의 소형 대화 상자에서 예외 정보를 한눈에 볼 수 있으며 내부 예외에 바로 액세스할 수도 있습니다.

NullReferenceException을 진단할 때 예외 도우미 내부에서 바로 null인 항목을 신속하게 확인할 수 있습니다.

또한 throw된 예외에서 중지된 동안 조건 추가 확인란을 클릭하여 특정 모듈에서 throw된 예외 유형의 중단을 제외할 수 있습니다.

![새 예외 도우미 대화 상자](../ide/media/vs2017ide-ExceptionHelper.png "새 예외 도우미 대화 상자")

자세한 내용은 [Using the New Exception Helper in Visual Studio](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/31/using-the-new-exception-helper-in-visual-studio-15-preview/)(Visual Studio에서 새 예외 도우미 사용) 블로그 게시물을 참조하세요.

## <a name="talk-to-us"></a>의견 보내기  
 피드백을 보낼 때는 Visual Studio 팀에 피드백을 보내는 이유도 함께 알려 주세요. Microsoft는 고객 여러분의 피드백을 소중하게 생각하며, Microsoft에서 추진하는 업무에 큰 역할을 합니다.  

Visual Studio를 개선하는 방법을 제안하거나 문제를 보고하려는 경우 자세한 내용은 [의견 보내기](../ide/talk-to-us.md) 페이지를 참조하세요.  

### <a name="report-a-problem"></a>문제 보고  
 발생한 문제의 전반적인 영향을 메시지만으로 전달할 수 없는 경우도 있습니다. 시스템 중단, 충돌 또는 기타 성능 문제가 발생하는 경우 **문제 보고** 도구를 사용하여 쉽게 재현 단계 및 지원 파일(예: 스크린샷, 추적 및 힙 덤프 파일)을 공유할 수 있습니다. 이 도구를 사용하는 방법에 대한 자세한 내용은 [문제를 보고하는 방법](how-to-report-a-problem-with-visual-studio-2017.md) 페이지를 참조하세요.  

### <a name="track-your-issue-in-connect"></a>Connect에서 문제 추적  
 Visual Studio 피드백의 상태를 추적하려는 경우 [Connect](http://connect.microsoft.com/)로 이동하여 버그를 신고하세요. 버그를 신고한 후에는 Connect로 돌아와 상태를 추적할 수 있습니다.  

## <a name="see-also"></a>참고 항목  
* [Visual C++의 새로운 기능](/cpp/top/what-s-new-for-visual-cpp-in-visual-studio)
* [C#의 새로운 기능](https://docs.microsoft.com/en-us/dotnet/articles/csharp/csharp-7)  
* [Team Foundation Server의 새로운 기능](https://www.visualstudio.com/en-us/docs/whats-new)
* [Visual Studio 릴리스 정보](https://www.visualstudio.com/news/vs2015-vs)



<!--HONumber=Feb17_HO4-->


