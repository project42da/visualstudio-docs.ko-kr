---
title: "Visual Studio 2017의 새로운 기능 | Microsoft Docs"
ms.custom: 
ms.date: 04/04/2017
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
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: b19199274d116e20af4c415673ebbeded95859d9
ms.lasthandoff: 04/05/2017

---
# <a name="what39s-new-in-visual-studio-2017"></a>Visual Studio 2017의 새로운 기능
모든 개발, 앱 및 플랫폼에서 뛰어난 생산성을 제공합니다. Visual Studio 2017를 사용하여 Android, iOS, Windows, Linux, 웹 및 클라우드용 앱을 개발합니다. 빠르게 코딩하고, 간단하게 디버그 및 진단하고, 자주 테스트하며, 안심하고 릴리스하세요. 개발자 고유의 확장을 빌드하여 Visual Studio를 확장하고 사용자 지정할 수도 있습니다. 이 새로운 릴리스로 버전 제어를 사용하고, 민첩하게 대처하고, 효율적으로 공동 작업하세요.

> [!NOTE]
> Visual Studio 2017의 새로운 기능에 대한 전체 목록은 [릴리스 정보](https://www.visualstudio.com/news/vs2015-vs)를 참조하세요.

변경 내용의 대략적인 요약은 다음과 같습니다.

* **성능 및 생산성** 새롭고 최신의 모바일, 클라우드 및 데스크톱 개발 기능에 집중했을 뿐만 아니라 전반적인 취득, 성능 및 일반 개발자 생산성 환경도 향상되었습니다. Visual Studio는 더 빨리 시작하고, 더 빨리 응답하며, 이전보다 적은 메모리를 사용합니다.
* **재정의된 기본 사항**. 새로운 설치 환경을 통해 더 빠르게 설치하고, 필요할 때 원하는 항목을 설치할 수 있습니다. Visual Studio는 대규모 솔루션과 프로젝트를 로드하거나 코드 폴더 또는 단일 코드 파일에서 작업하려는 경우 더 빠르게 시작합니다. 또한 Visual Studio를 사용하는 경우 특히 DevOps를 수용하는 팀에서 큰 그림에 계속 집중할 수 있습니다.
* **Azure로 클라우드 앱 개발** 기본 제공 Azure 도구 모음을 통해 Microsoft Azure 기반의 클라우드 지원 앱을 쉽게 만들 수 있습니다. Visual Studio를 사용하면 Azure에서 직접 앱과 서비스를 쉽게 구성, 빌드, 디버그, 패키징 및 배포할 수 있습니다.
* **모바일 앱 개발** Visual Studio 2017에서는 하나의 핵심 코드베이스와 기술 집합을 사용하여 다중 플랫폼 모바일 요구 사항을 통합하는 Xamarin에서 혁신적인 결과를 빠르게 얻을 수 있습니다. 기존 팀, 기술 투자 및 C# 코드와 더불어 모바일로 이동하여 예정보다 빨리 예산 수준 이하의 소비자급 환경을 제공합니다. 사용자의 역량을 강화할 수 있도록 모바일 수명 주기의 각 단계를 모두 가속화하여 세계 최고의 소비자 환경 또는 생산성 앱 포트폴리오를 제공합니다.

가장 두드러진 변화 중 몇 가지에 대한 자세한 내용은 다음과 같습니다.

## <a name="performance-improvements"></a>성능 향상

### <a name="a-new-setup-experience"></a>새로운 설치 환경  
[Visual Studio 2017 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) 또는 [Visual Studio 시스템 요구 사항 확인](https://www.visualstudio.com/en-us/productinfo/vs2017-system-requirements-vs)

 Visual Studio를 사용하면 필요할 때 필요한 기능만 쉽고 빠르게 설치할 수 있습니다. 또한 완전히 제거됩니다.

 가장 중요한 변화는 Visual Studio를 설치할 때 볼 수 있는 새로운 설치 환경입니다. **작업** 탭에는 일반 프레임워크, 언어 및 플랫폼을 나타내도록 그룹화된 설치 옵션이 표시됩니다. .NET 데스크톱 개발에서 Windows, Linux 및 iOS의 C++ 응용 프로그램 개발에 이르기까지 모든 작업을 포함합니다.   

 ![Visual Studio 2017 설치 대화 상자](../install/media/vs2017-workloads.PNG "Visual Studio 2017 설치 화면")

필요한 작업을 선택하고, 필요할 때 변경합니다.

작업을 사용하는 대신 사용자 고유의 구성 요소를 선택하고 싶으세요? 설치 관리자에서 **개별 구성 요소** 탭을 선택하면 됩니다. 또한 Windows 언어 옵션을 변경하지 않고도 언어 팩을 설치하고 싶으세요? 설치 관리자의 **언어 팩** 탭을 선택합니다.  

단계별 지침을 포함하여 새로운 설치 환경에 대한 자세한 내용은 [Visual Studio 설치](../install/install-visual-studio.md) 페이지를 참조하세요.

### <a name="start-visual-studio-faster"></a>더 빨리 Visual Studio 시작
새로운 Visual Studio 성능 센터는 IDE 시작 시간을 최적화하는 데 유용합니다. 성능 센터에는 IDE 시작을 늦출 수 있는 모든 확장 및 도구 창이 나열됩니다. 성능 센터를 사용하여 확장 시작 시간 또는 시작 시 도구 창을 열지 여부를 결정하여 시작 성능을 개선할 수 있습니다.

### <a name="decrease-solution-load-time"></a>솔루션 로드 시간 감소
많은 수의 프로젝트가 포함된 솔루션에서 작업한다고 해서 한 번에 모든 파일이나 프로젝트로 작업해야 하는 것은 아닙니다. 이제 Visual Studio에서 모든 프로젝트가 로드되기를 기다리지 않고 편집 및 디버그할 수 있습니다. 관리되는 프로젝트에서 이 작업을 시도해보려면 도구-> 옵션-> 프로젝트 및 솔루션에서 **경량 솔루션 로드**를 켭니다.

  ![Visual Studio 2017의 옵션 대화 상자](../ide/media/vs2017ide-LightweightSolutionLoad.PNG "Visual Studio 2017 - 옵션 대화 상자 - 경량 솔루션 로드")

### <a name="faster-on-demand-loading-of-extensions"></a>요청 시 더 빠르게 확장 로드
Visual Studio는 IDE 시작이 아닌 요청 시에 로드되도록 확장을 전환하고 있습니다(타사 확장과도 작업). 어떤 확장이 시작, 솔루션 로드 및 입력 성능에 영향을 주는지 궁금하세요? 이 정보는 도움말-> Visual Studio 성능 관리에서 확인할 수 있습니다.

  ![Visual Studio 2017의 옵션 대화 상자](../ide/media/vs2017ide-manage-vs-perf.png "Visual Studio 도움말 대화 상자 - 성능 관리")

## <a name="productivity-improvements"></a>생산성 향상

### <a name="sign-in-across-multiple-accounts"></a>여러 계정에 로그인  
팀 탐색기, Azure 도구, Windows 스토어 게시 등에서 사용자 계정을 공유할 수 있는 새로운 ID 서비스를 Visual Studio에 도입했습니다.

더 오랫동안 로그인 상태를 유지할 수도 있습니다. Visual Studio에서 12시간마다 다시 로그인하라는 메시지가 표시하되 않습니다. 자세한 내용은 [Fewer Visual Studio Sign-in Prompts](https://blogs.msdn.microsoft.com/visualstudio/2016/08/15/fewer-visual-studio-sign-in-prompts/)(Visual Studio 로그인 프롬프트 횟수 감소) 블로그 게시물을 참조하세요.

### <a name="manage-your-extensions-with-roaming-extensions-manager"></a>로밍 중인 확장 관리자를 사용하여 확장 관리
Visual Studio에 로그인할 때 즐겨찾는 확장으로 각 개발 환경을 더 쉽게 설정할 수 있습니다. 새로운 [로밍 중인 확장 관리자]는 클라우드에 동기화된 목록을 만들어 즐겨찾는 확장을 모두 추적합니다.  

Visual Studio의 확장 목록을 보려면 도구 > 확장 및 업데이트를 클릭한 다음 로밍 중인 확장 관리자를 클릭합니다.

![Visual Studio 2017 - 확장 및 업데이트 대화 상자](../ide/media/vs2017ide-extensions-and-updates.png "Visual Studio 2017 - 도구 > 확장 및 업데이트 대화 상자")

로밍 중인 확장 관리자는 설치하는 모든 확장을 추적하지만 로밍 목록에 추가할 확장을 선택할 수 있습니다.

![Visual Studio 2017 - 확장 및 업데이트 대화 상자](../ide/media/vs2017ide-RoamingExtensionManager.png "Visual Studio 2017 - 로밍 중인 확장 관리자")

로밍 중인 확장 관리자를 사용하는 경우 3개의 아이콘 형식이 목록에 표시됩니다.
* ![로밍 아이콘](../ide/media/vs2017ide-roamedicon.png "로밍 아이콘") ***로밍***: 이 로밍 목록에 포함되어 있지만, 컴퓨터에 설치되지 않은 확장입니다.
  **다운로드** 단추를 사용하여 이러한 확장을 설치할 수 있습니다.
* ![로밍 및 설치 아이콘](../ide/media/vs2017ide-roamedinstalledicon.png "로밍 및 설치 아이콘") ***로밍 및 설치***: 이 로밍 목록에 포함되어 있고, 개발 환경에 설치된 모든 확장입니다.
  로밍하지 않도록 결정하는 경우 **로밍 중지** 단추를 사용하여 이러한 확장을 제거할 수 있습니다.
* ![설치 아이콘](../ide/media/vs2017ide-installedicon.png "설치 아이콘") ***설치***: 이 환경에 설치되어 있지만 로밍 목록에 포함되지 않은 모든 확장입니다.
  **로밍 시작** 단추를 사용하여 로밍 목록에 확장을 추가할 수 있습니다.

로그인한 상태에서 다운로드하는 모든 확장은 **로밍 및 설치**로 목록에 추가되며, 모든 컴퓨터에서 액세스할 수 있는 로밍 목록의 일부가 됩니다.

### <a name="experience-live-architecture-dependency-validation-and-live-unit-testing"></a>라이브 아키텍처 종속성 유효성 검사 및 Live Unit Testing 경험

이제 종속성 유효성 검사 다이어그램(레이어 다이어그램이라고도 함)을 사용하여 코드 편집기에서 코드를 입력하면 Visual Studio에서 아키텍처 종속성 규칙 위반을 실시간으로 알릴 수 있습니다.

오류 목록에 오류가 표시되고, 텍스트 편집기의 물결선은 정확한 위반 위치를 보여 줍니다. 이제 원치 않는 종속성이 늘어날 가능성이 줄었습니다.

![라이브 아키텍처 유효성 검사](../ide/media/vs2017ide-LiveArchitectureDepedendencyValidation.png "라이브 아키텍처 종속성 유효성 검사")

#### <a name="live-unit-testing"></a>Live Unit Testing:

Visual Studio Enterprise 2017에서 라이브 단위 테스트는 코딩하는 동안 편집기에 라이브 단위 테스트 결과와 코드 검사를 제공합니다. .NET Framework용 C# 및 Visual Basic 프로젝트에서 작동하고, MSTest, xUnit, NUnit의 세 가지 테스트 프레임워크를 지원합니다.

![라이브 단위 테스트](../ide/media/lut-codewindow.png "Visual Studio Enterprise 버전에 있는 새 라이브 단위 테스트 기능의 예")

자세한 내용은 [Visual Studio 2017 Enterprise의 Live Unit Testing](https://blogs.msdn.microsoft.com/visualstudio/2017/03/09/live-unit-testing-in-visual-studio-2017-enterprise/) 블로그 게시물을 참조하세요.

### <a name="devops"></a>DevOps
#### <a name="redgate-data-tools"></a>Redgate 데이터 도구:
DevOps 기능을 SQL Server 데이터베이스 개발로 확장하기 위해 Visual Studio 2017의 다음 버전에서 Redgate 데이터 도구를 사용할 수 있습니다.

Visual Studio 2017 Enterprise에는 다음이 포함되어 있습니다.
- [Redgate ReadyRoll Core](http://www.red-gate.com/products/sql-development/readyroll/entrypage/microsoft-and-readyroll?utm_source=microsoft&utm_medium=link&utm_campaign=readyroll&utm_term=relnotes0317)는 마이그레이션 스크립트를 개발하고, 소스 제어를 사용하여 데이터베이스 변경 내용을 관리하고, SQL Server 데이터베이스 변경 내용을 응용 프로그램 변경 내용과 함께 자동으로 안전하게 배포하는 데 도움이 됩니다.
- [Redgate SQL Prompt 코어](http://www.red-gate.com/products/sql-development/sql-prompt/entrypage/microsoft-and-sql-prompt?utm_source=microsoft&utm_medium=link&utm_campaign=sqlprompt&utm_term=relnotes0317)는 지능형 코드 완성 기능을 통해 SQL을 더 빠르고 정확하게 작성하는 데 도움이 됩니다. SQL 프롬프트는 데이터베이스 및 시스템 개체, 키워드를 자동으로 완성하고 입력 시 열을 제안합니다. 모든 열 이름이나 별칭을 기억할 필요가 없으므로 코드가 더 깔끔해지고 오류가 줄어듭니다.

Visual Studio 2017의 모든 버전에는 다음이 포함되어 있습니다.
- [Redgate SQL 검색](http://www.red-gate.com/products/sql-development/sql-search/?utm_source=microsoft&utm_medium=link&utm_campaign=sqlsearch&utm_term=relnotes0317)은 여러 데이터베이스에서 SQL 조각 및 개체를 빠르게 찾을 수 있도록 하여 생산성을 높입니다.

자세한 내용은 [Visual Studio 2017의 Redgate 데이터 도구](https://blogs.msdn.microsoft.com/visualstudio/2017/03/07/redgate-data-tools-in-visual-studio-2017/) 블로그 게시물을 참조하세요.

### <a name="visual-studio-ide-enhancements"></a>Visual Studio IDE 향상
#### <a name="interact-with-git"></a>Git과 상호 작용:
Visual Studio에서 프로젝트로 작업할 때 코드를 설정하고 빠르게 커밋하여 Git 서비스에 게시할 수 있습니다. 또한 IDE의 오른쪽 아래 모서리에 있는 단추의 메뉴 클릭을 사용하여 Git 리포지토리를 관리할 수도 있습니다.

![Visual Studio 2017과 Git 대화 상자의 상호 작용](../ide/media/vsIDE-GitInteraction.png "Visual Studio IDE의 Git 도구")

#### <a name="view-and-navigate-code-with-structure-visualizer"></a>구조 시각화 도우미를 사용하여 코드 보기 및 탐색:
구조 시각화 도우미는 코드에 구조 안내선(들여쓰기 안내선이라고도 함)을 그립니다. 이 안내선을 사용하면 언제든지 스크롤하지 않고도 어떤 코드 블록을 시각화하고 검색할 수 있습니다. 선 위로 마우스를 가리키면 해당 블록과 그 부모를 열어서 볼 수 있는 도구 설명이 표시됩니다. TextMate 문법 검사뿐만 아니라 C#, Visual Basic 및 XAML을 통해 지원되는 모든 언어에서 사용할 수 있습니다.

![Visual Studio 2017 구조 시각화 도우미](../ide/media/vsIDE-StructureVisualizer.png "Visual Studio의 구조 시각화 도우미")

#### <a name="experience-improved-navigation-controls"></a>향상된 컨트롤 탐색 환경:
A에서 B로 이동하는 데 도움이 되는 탐색 환경을 새로 고쳐 자신감 있게 더욱 집중할 수 있게 했습니다.

* **다음으로 이동**(Ctrl+F12) &ndash; 모든 베이스 형식 또는 멤버에서 다양한 구현으로 이동합니다.

* **모두로 이동**(Ctrl+T 또는 Ctrl+,) &ndash; 모든 파일/형식/멤버/기호 선언으로 직접 이동합니다. 결과 목록을 필터링하거나 쿼리 구문을 사용할 수 있습니다(예: 파일의 경우 "f searchTerm", 형식의 경우 "t searchTerm").

 ![향상된 모두로 이동](../ide/media/vs2017ide-navigation-go-to.png "향상된 모두로 이동 기능의 예")

* **모든 참조 찾기(Shift+F12)** &ndash; 구문 색 지정을 사용하면 프로젝트, 정의 및 경로의 조합에 따라 [모든 참조 찾기] 결과를 그룹화할 수 있습니다. 또한 결과를 "잠그면" 원래 결과를 잃지 않고 다른 참조를 계속 찾을 수 있습니다.

 ![새로운 모든 참조 찾기 도구](../ide/media/vs2017ide-find-all-references.png "새로운 모든 참조 찾기 도구의 예")

* **들여쓰기 안내선** &ndash; 회색 세로 점선은 코드에서 랜드마크로 작용하여 보기의 프레임 내에서 컨텍스트를 제공합니다. 이러한 기능은 인기 있는 생산성 파워 도구에서 인식할 수 있습니다.

새로운 생산성 기능에 대한 자세한 내용은 Mark Wilson-Thomas의 [Visual Studio 2017의 생산성](https://blogs.msdn.microsoft.com/visualstudio/2016/11/28/productivity-in-visual-studio-2017-rc/)(영문) 블로그 게시물을 참조하세요.

### <a name="visual-c"></a>Visual C++
Visual Studio에서 C++ 핵심 지침을 배포하고, C++11 및 C++ 기능에 대한 향상된 지원을 추가하여 컴파일러를 업데이트하고, C++ 라이브러리에서 기능을 추가 및 업데이트하는 등 Visual Studio에서 향상된 몇 가지 기능을 확인할 수 있습니다. C++ IDE, 설치 작업 등의 성능도 향상되었습니다.

또한 많은 고객이 [Microsoft Connect](https://connect.microsoft.com/VisualStudio "Microsoft Connect")를 통해 제출한 컴파일러와 도구에서 발생된 250개 이상의 버그와 보고된 문제를 해결했습니다.

자세한 내용은 [Visual 2017의 Visual C++에 대한 새로운 기능](/cpp/top/what-s-new-for-visual-cpp-in-visual-studio) 페이지를 참조하세요.  

### <a name="debugging-and-diagnostics"></a>디버깅 및 진단

#### <a name="run-to-click"></a>실행하려면 클릭:

이제 원하는 줄에서 중지하도록 중단점을 설정하지 않고도 디버깅 중에 더 쉽게 건너뛸 수 있습니다. 디버거에서 멈췄을 때 마우스가 있는 코드 줄 옆에 나타나는 아이콘을 클릭하면 됩니다. 코드가 실행되어 다음에 코드 경로에서 이 줄에 도달하면 해당 줄에서 중지됩니다.

![Visual Studio 2017 디버그 - 실행하려면 클릭](../ide/media/vs2017ide-RunToClick.png "Visual Studio 디버깅 및 진단의 실행하려면 클릭")

#### <a name="the-new-exception-helper"></a>새 예외 도우미:

새 예외 도우미를 사용하면 예외 정보를 한눈에 볼 수 있습니다. 정보는 내부 예외에 즉시 액세스할 수 있는 간결한 양식으로 제공됩니다. NullReferenceException을 진단할 때 예외 도우미 내부에서 null인 항목을 빠르게 확인할 수 있습니다.

![Visual Studio의 새 예외 도우미 대화 상자](../ide/media/vs2017ide-ExceptionHelper.png "새 예외 도우미 대화 상자")

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

