---
title: "Visual Studio 성능 팁과 요령 | Microsoft Docs"
ms.date: 08/07/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugger
ms.assetid: 2fbcb59e-e981-4b40-8b7a-c1140d31ec4b
caps.latest.revision: 1
author: mikejo5000
ms.author: mikejo
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
ms.translationtype: HT
ms.sourcegitcommit: fe6d864baf518cba882cea8e985fdacbfdf5b8b2
ms.openlocfilehash: 53c31da02b643114d9b152a0cde180ff5f6a5b7e
ms.contentlocale: ko-kr
ms.lasthandoff: 08/09/2017

---
# <a name="visual-studio-performance-tips-and-tricks"></a>Visual Studio 성능 팁과 요령

Visual Studio 성능 권장 사항은 드물게 발생할 수 있는 메모리 부족 상황에 대처하기 위해 제공됩니다. 이러한 상황에서는 사용하지 않는 특정 Visual Studio 기능을 최적화할 수 있습니다. 아래에서 제시하는 팁은 일반적인 권장 사항이 아닙니다.

> [!NOTE]
> 메모리 문제로 인해 제품을 사용하는 데 어려움이 있는 경우 피드백 도구를 통해 알려 주세요.

## <a name="optimize-your-environment"></a>환경 최적화

- **64비트 OS 사용**

    Windows 32비트 버전에서 64비트 버전으로 시스템을 업그레이드하면 Visual Studio에서 사용 가능한 가상 메모리가 2GB에서 4GB로 확장됩니다. Visual Studio는 32비트 프로세스이지만, 이렇게 하면 훨씬 더 큰 작업 부하에 대응할 수 ​​있습니다.

    자세한 내용은 [Memory limits](https://msdn.microsoft.com/en-us/library/windows/desktop/aa366778(v=vs.85).aspx#memory_limits)(메모리 한도) 및 [Using /LARGEADDRESSAWARE on 64-bit Windows](https://blogs.msdn.microsoft.com/oldnewthing/20050601-24/?p=35483/)(64비트 Windows에서 /LARGEADDRESSAWARE 사용)를 참조하세요.

## <a name="configure-solution-and-projects"></a>솔루션 및 프로젝트 구성

여러 프로젝트를 포함하는 대규모 솔루션에서는 다음과 같은 최적화를 통해 이점을 얻을 수 있습니다.

- **경량 솔루션 로드 사용**

    **경량 솔루션 로드**를 사용하면 솔루션에 포함된 일부 프로젝트를 지연 로드하여 메모리 및 CPU 성능을 높일 수 있습니다. 이 기능을 솔루션별로 사용할 수도 있습니다. 이 옵션은 기본적으로 해제되어 있습니다.

    **경량 솔루션 로드**를 사용하려면 **도구 > 옵션 > 프로젝트 및 솔루션 > 경량 솔루션 로드**를 선택합니다.

    이 모드에서는 일부 IDE 기능을 사용할 수 없습니다. 이 선택이 도움이 되는지 판단하려면 [Shorter solution load time](https://blogs.msdn.microsoft.com/visualstudio/2016/10/11/shorter-solution-load-time-in-visual-studio-15/)(솔루션 로드 시간 단축) 및 [Visual Studio 시작 시간 최적화](https://docs.microsoft.com/en-us/visualstudio/ide/optimize-visual-studio-startup-time#speed-up-solution-load)를 참조하세요.

- **프로젝트 언로드**

    솔루션 탐색기에서 마우스 오른쪽 단추를 클릭할 때 나타나는 상황에 맞는 메뉴에서 사용 빈도가 낮은 프로젝트를 개별적으로 직접 언로드할 수 있습니다.

- **솔루션 리팩터링**

    공통으로 사용하는 프로젝트를 포함하는 솔루션을 여러 개의 작은 솔루션 파일로 나눌 수 있습니다. 이러한 리팩터링은 워크플로의 메모리 사용량을 크게 줄여줍니다. 또한 솔루션이 작을수록 로드 속도가 빨라집니다.

## <a name="configure-debugging-options"></a>디버깅 옵션 구성
디버깅 세션 중에 메모리가 부족한 상황이 반복되면 하나 이상의 구성을 변경하여 성능을 최적화할 수 있습니다.

- **[내 코드만] 기능 사용**

    가장 간단한 최적화는 **내 코드만** 기능을 사용하여 내 프로젝트의 기호만 로드하는 것입니다. 이 기능을 사용하면 관리되는 응용 프로그램(.NET)을 디버그할 때 상당한 메모리가 절약될 수 있습니다. 일부 프로젝트 형식에서는 이 옵션이 기본적으로 사용됩니다.

    **내 코드만** 기능을 사용하려면 **도구 > 옵션 > 디버깅 > 일반**을 선택한 다음 **내 코드만 사용**을 선택합니다.

- **로드할 기호 지정**

    네이티브 디버깅의 경우 기호 파일(.pdb)을 로드하면 메모리 리소스가 많이 소비됩니다. 디버거 기호 설정을 구성하면 메모리를 절약할 수 있습니다. 일반적으로는 내 프로젝트의 모듈만 로드하도록 솔루션을 구성합니다.

    기호 로딩을 지정하려면 **도구 > 옵션 > 디버깅 > 기호**를 선택합니다.

    옵션을 **모든 모듈** 대신 **지정된 모듈만**으로 설정하고 로드할 모듈을 지정합니다. 디버깅 중에 **모듈** 창의 특정 모듈을 마우스 오른쪽 단추로 클릭하여 기호 로드에 모듈을 명시적으로 포함할 수도 있습니다. 디버깅 중에 이 창을 열려면 **디버그 > 창 > 모듈**을 선택합니다.

    자세한 내용은 [Understanding symbol files](https://blogs.msdn.microsoft.com/visualstudioalm/2015/01/05/understanding-symbol-files-and-visual-studios-symbol-settings/)(기호 파일 이해)를 참조하세요.

- **진단 도구 사용 안 함**

    CPU 프로파일링은 사용 후 해제하는 것이 좋습니다. 이 기능은 많은 리소스를 소비할 수 있습니다. CPU 프로파일링을 한 번 사용하면 이후 디버그 세션에서도 계속 사용되므로 작업을 마쳤으면 명시적으로 해제하는 것이 좋습니다. 진단 도구가 제공하는 기능이 필요하지 않은 경우 디버깅 중에 진단 도구를 해제하여 일부 리소스를 절약할 수 있습니다.

    진단 도구를 해제하려면 디버그 세션을 시작하고 **도구 > 옵션 > 디버그하는 동안 진단 도구 사용**을 선택한 후 옵션을 선택 취소합니다.

    자세한 내용은 [프로파일링 도구](https://docs.microsoft.com/en-us/visualstudio/profiling/profiling-tools)를 참조하세요.

## <a name="disable-tools-and-extensions"></a>도구 및 확장 기능 사용 안 함
일부 도구 또는 확장 기능을 해제하여 성능을 높일 수 있습니다.

> [!TIP]
> 확장 기능을 하나씩 끄면서 성능을 재확인하여 성능 문제의 원인을 파악할 수 있는 경우가 많습니다.

### <a name="managed-language-services-roslyn"></a>관리 언어 서비스(Roslyn)

Roslyn 성능 고려 사항에 대한 자세한 내용은 [Performance considerations for large solutions](대규모 솔루션에 대한 성능 고려 사항)(https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions)를 참조하세요.

- **전체 솔루션 분석 사용 안 함**

    Visual Studio는 오류와 관련하여 편리한 환경을 제공하고자 빌드를 호출하기 전에 전체 솔루션에 대한 분석을 수행합니다. 이 기능은 오류를 최대한 빠르게 식별하는 데 유용합니다. 그러나 대규모 솔루션에서는 이 기능에 상당한 메모리 리소스가 소비될 수 있습니다. 메모리 부족 또는 유사한 문제가 발생하는 경우 이 기능을 해제하여 리소스를 확보할 수 있습니다. 기본적으로 이 옵션은 Visual Basic에서는 사용되고 C#에서는 사용되지 않습니다.

    **전체 솔루션 분석**을 해제하려면 **도구 > 옵션 > 텍스트 편집기 > <Visual Basic 또는 C#>**을 선택합니다. 그런 다음 **고급**를 선택하고 **전체 솔루션 분석 사용**을 선택 취소합니다.

- **CodeLens 사용 안 함**

    Visual Studio는 각 메서드가 표시될 때 **모든 참조 찾기** 작업을 수행합니다. CodeLens는 참조 횟수를 인라인으로 표시하는 등의 기능을 제공합니다. 이때 별도의 프로세스(예: ServiceHub.RoslynCodeAnalysisService32)로 작업이 수행됩니다. 이 기능은 낮은 우선 순위로 실행되지만, 대규모 솔루션이나 리소스가 제한된 시스템에서는 성능에 상당한 영향을 줄 수 있습니다. 이 프로세스의 CPU 사용량이 많거나 메모리 문제가 발생하는 경우(예: 4GB 컴퓨터에서 대규모 솔루션을 로드할 때) 이 기능을 해제하여 리소스를 확보할 수 있습니다.

    CodeLens를 해제하려면 **도구 > 옵션 > 텍스트 편집기 > 모든 언어 > CodeLens**를 선택하고 기능을 선택 취소합니다.

    이 기능은 Visual Studio Professional 및 Visual Studio Enterprise에서 제공됩니다.

### <a name="other-tools-and-extensions"></a>기타 도구 및 확장 기능

- **확장 기능 사용 안 함**

    확장 기능은 Visual Studio에 추가된 부가적인 소프트웨어 구성 요소로서 새로운 기능을 제공하거나 기존 기능을 확장합니다. 확장 기능은 메모리 리소스 문제의 원인이 될 수도 있습니다. 메모리 리소스 문제가 발생하는 경우 확장 기능을 하나씩 해제하면서 시나리오나 워크플로에 어떠한 영향이 있는지 확인해 보세요.

    확장 기능을 해제하려면 **도구 | 확장 및 업데이트**로 이동하고 특정 확장 기능을 해제합니다.

- **XAML 디자이너 사용 안 함**

    XAML 디자이너는 기본적으로 사용되지만 .XAML 파일을 열 때만 리소스를 소비합니다. XAML 파일로 작업하지만 디자이너 기능은 사용하지 않으려는 경우 이 기능을 해제하여 일부 메모리를 확보할 수 있습니다.

    XAML 디자이너를 해제하려면 **도구 > 옵션 > XAML 디자이너 > XAML 디자이너 사용**으로 이동하고 옵션을 선택 취소합니다.

- **워크로드 제거**

    Visual Studio 설치 관리자를 사용하여 더 이상 사용되지 않는 워크로드를 제거할 수 있습니다. 이렇게 하면 더 이상 필요하지 않은 패키지 및 어셈블리를 건너뜀으로써 시작 및 런타임 비용을 줄일 수 있습니다.

## <a name="force-a-garbage-collection"></a>가비지 수집 강제 실행

CLR은 가비지 수집 메모리 관리 시스템을 사용합니다. 이 시스템에서는 더 이상 필요하지 않은 개체에 메모리가 사용될 수도 있습니다. 이 상태는 일시적이며, 가비지 수집기에서 성능 및 리소스 사용량을 추론하여 메모리를 해제합니다. Visual Studio에서 바로 가기 키를 사용하여 CLR이 미사용 메모리를 모두 수집하도록 강제할 수 있습니다. 수집 대기 중인 가비지가 상당히 많을 때 가비지 수집을 강제 실행하면 작업 관리자에서 devenv.exe 프로세스의 메모리 사용량이 감소하는 것을 확인할 수 있습니다. 이 방법을 사용해야 하는 경우는 거의 없습니다. 그러나 전체 빌드, 디버그 세션 또는 솔루션 열기 이벤트와 같이 부담이 큰 작업이 완료된 후 프로세스에서 실제로 사용 중인 메모리의 양을 확인하는 데 도움이 됩니다. Visual Studio는 관리 방식과 네이티브가 혼합된 환경이므로 경우에 따라서는 네이티브 할당자와 가비지 수집기가 제한된 메모리 리소스를 두고 경쟁할 수 있습니다. 메모리 사용량이 많은 상황에서는 가비지 수집기를 강제 실행하는 방법이 유용할 수 있습니다.

가비지 수집을 강제 실행하려면 **Ctrl+Alt+Shift+F12**, **Ctrl+Alt+Shift+F12** 단축키를 사용합니다(두 번 누름).

가비지 수집을 강제 실행해야 시나리오가 안정적으로 작동한다면, 이 동작은 버그일 가능성이 크므로 Visual Studio 피드백 도구를 통해 보고해 주시기 바랍니다.

CLR 가비지 수집기에 대한 자세한 내용은 [Fundamental of Garbage Collection](https://msdn.microsoft.com/en-us/library/ee787088(v=vs.110).aspx)(가비지 수집 기본 사항)을 참조하세요.

## <a name="see-also"></a>참고 항목  
 [Visual Studio IDE](../ide/index.md)

