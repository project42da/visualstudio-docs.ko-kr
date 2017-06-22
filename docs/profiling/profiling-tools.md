---
title: "Visual Studio의 프로파일링 도구 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.diagnosticshub.overview
ms.assetid: 0fb6cd5d-e16a-4526-84a5-19e63c625bc5
caps.latest.revision: 20
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 09c33f3cc331af03659922e178e4089f177132de
ms.contentlocale: ko-kr
ms.lasthandoff: 05/13/2017

---
# <a name="profiling-tools"></a>프로파일링 도구
프로파일링 및 진단 도구는 메모리 및 CPU 사용량 진단 및 응용 프로그램 수준 문제 진단을 도와줍니다. 이러한 도구를 사용하면 디버거에서 응용 프로그램을 실행하는 동안 데이터(예: 변수 값, 함수 호출, 이벤트)를 누적할 수 있습니다. 코드를 실행하는 동안 다양한 지점에서 응용 프로그램 상태를 볼 수 있습니다.  
  
 프로젝트 형식에(예: 데스크톱, UWP, ASP.NET) 사용할 수 있는 도구를 보려면 아래쪽의 요약을 확인합니다.  
  
 **디버그/Windows/진단 도구 표시**를 사용하여 프로파일링 도구에 액세스함으로써 디버그 세션 중에 도구를 사용할 수 있고, 다른 접근 방법을 통해 사후 분석을 수행할 수도 있습니다.  다른 방법에 대한 자세한 내용을 보려면 [디버거를 사용하거나 사용하지 않고 프로파일링 도구 실행](../profiling/running-profiling-tools-with-or-without-the-debugger.md)을 참조하세요.
  
 ![DebugDiagnosticsToolsMenu](../profiling/media/debugdiagnosticstoolsmenu.png "DebugDiagnosticsToolsMenu")
  
 이 릴리스의 새 기능에 대해 자세히 알아보려면 [프로 파일링 도구의 새로운 기능](../profiling/what-s-new-in-profiling-tools.md)을 참조하세요.
  
 다음 섹션에서는 Visual Studio에서 사용할 수 있는 다양한 성능 도구를 설명합니다.
  
## <a name="memory-usage"></a>메모리 사용량  
 ![DiagMemorySmall](../profiling/media/diagmemorysmall.png "DiagMemorySmall")  
  
 **메모리 사용량** 도구를 사용하면 디버깅 중에 메모리 누수 및 비효율적인 메모리를 찾습니다. 이 도구를 통해 관리되는 메모리 및 기본 메모리 힙의 스냅숏을 만들 수 있습니다. 이 도구는 데스크톱 앱, Windows 유니버설 앱, ASP.NET 앱에서 사용할 수 있습니다. **메모리 사용량** 도구는 디버깅하는 동안 **진단 도구** 창에서 실행하거나(**디버그/Windows/진단 도구 표시**) 디버거 외부에서(**디버그/성능 프로파일러...**) 실행할 수 있습니다. 자세한 내용은 [메모리 사용량](../profiling/memory-usage.md) 및 [디버깅하지 않는 경우의 메모리 사용량](../profiling/Memory-Usage-without-Debugging2.md)을 참조하세요.  
  
## <a name="cpu-usage"></a>CPU 사용량  
 ![DiagCPUSmall](../profiling/media/diagcpusmall.png "DiagCPUSmall")  
  
 **CPU 사용량** 도구는 CPU에서 C++, C#/VB 및 JavaScript 코드 실행에 시간을 소모하는 상황을 보여 줍니다.  이 도구는 데스크톱 및 Windows 유니버설 앱은 물론 ASP.NET 및 Azure App Service 앱에서 사용할 수 있습니다. **CPU 사용량** 도구는 디버깅하는 동안 **진단 도구** 창에서 실행하거나(**디버그/Windows/진단 도구 표시**) 디버거 외부에서(**디버그/성능 프로파일러...**) 실행할 수 있습니다. 자세한 내용은 [초보자를 위한 성능 프로파일링 지침](../profiling/beginners-guide-to-performance-profiling.md) 및 [CPU 사용량](../profiling/cpu-usage.md)을 참조하세요.
  
## <a name="gpu-usage"></a>GPU 사용량  
 ![DiagGPUUsage](../profiling/media/diaggpuusage.png "DiagGPUUsage")  
  
 Direct3D 앱의 고급 하드웨어 사용률을 보다 잘 파악하려면 [GPU 사용량](../debugger/gpu-usage.md) 도구를 사용합니다. 이 도구는 데스크톱 및 Windows 유니버설 앱에서 사용할 수 있지만 ASP.NET 앱에서는 사용할 수 없습니다. **GPU 사용량** 도구는 디버거(**디버그 / 성능 프로파일러...**) 외부에서 실행될 수 있습니다.  
  
## <a name="application-timeline"></a>응용 프로그램 타임라인  
 ![DiagAppTimeline](../profiling/media/diagapptimeline.png "DiagAppTimeline")  
  
 [응용 프로그램 타임라인](../profiling/application-timeline.md) 도구를 사용하면 리소스 소비에 대해 자세한 뷰를 제공하기 때문에 XAML 응용 프로그램의 성능을 개선하는 데 도움이 됩니다. **응용 프로그램 타임라인** 은 데스크톱 및 Windows 유니버설 앱에서 사용할 수 있지만 ASP.NET 앱에서는 사용할 수 없습니다. **응용 프로그램 타임라인** 도구는 디버거(**디버그 / 성능 프로파일러...**) 외부에서 실행될 수 있습니다.
  
## <a name="perftips"></a>PerfTips  
 ![DiagPerfTips](../profiling/media/diagperftips.png "DiagPerfTips")  
  
 디버거가 중단점 또는 단계별 실행 작업에서 실행을 중지하는 경우 중단점과 이전 중단점 사이의 경과 시간이 편집기 창에 팁으로 표시됩니다. [PerfTips](../profiling/perftips.md) 는 디버깅 중에 앱의 성능을 모니터링하고 분석하도록 도와줍니다. **PerfTips** 는 데스크톱, Windows 유니버설, ASP.NET 앱에서 볼 수 있습니다.

## <a name="performance-explorer"></a>성능 탐색기  
 ![PerfTools](../profiling/media/perftools.png "PerfTools")  
  
 **성능 탐색기** (**디버그/프로파일러/성능 탐색기**)를 사용하면 **CPU 샘플링**,  **계측**, **.NET 메모리 할당**, **리소스 경합**을 비롯한 다양한 도구를 사용할 수 있습니다. 성능 탐색기 도구는 데스크톱 앱과 ASP.NET 앱에서 사용할 수 있지만 Windows 유니버설 앱에서는 사용할 수 없습니다. 자세한 내용은 [성능 탐색기](../profiling/performance-explorer.md)를 참조하세요.

 > [!NOTE]
 > 계측과 같은 특수한 작업을 수행하려는 경우가 아니면 성능 탐색기(현재 레거시 도구임) 대신 메모리 사용량 및 CPU 사용량과 같은 진단 도구를 사용하세요.
  
## <a name="javascript-memory"></a>JavaScript 메모리  
 ![DiagJSMemory](../profiling/media/diagjsmemory.png "DiagJSMemory")  
  
 [JavaScript 메모리](../profiling/javascript-memory.md) 도구를 사용하면 앱에서 메모리 누수 및 비효율적인 메모리 사용량을 찾을 수 있습니다. 이 도구를 사용하면 JavaScript 힙의 스냅숏을 만들 수 있습니다. 이 도구는 Windows 유니버설 HTML 앱에서 사용할 수 있습니다. **JavaScript 메모리** 도구는 디버거(**디버그 / 성능 프로파일러...**) 외부에서 실행될 수 있습니다.  
  
## <a name="html-ui-responsiveness"></a>HTML UI 응답성  
 ![DiagHTMLResp](../profiling/media/diaghtmlresp.png "DiagHTMLResp")  
  
 [HTML UI 응답성](../profiling/html-ui-responsiveness.md) 도구는 앱에서 응답성 부족, 느린 로딩 시간, 예상보다 빈도가 낮은 시각적 업데이트를 비롯한 성능 문제를 격리하도록 도와줍니다. 이 도구는 Windows 유니버설 HTML 앱에서 사용할 수 있습니다. **HTML UI 응답성** 도구는 디버거(**디버그 / 성능 프로파일러...**) 외부에서 실행될 수 있습니다.  
  
## <a name="intellitrace"></a>IntelliTrace  
 ![DiagIntelliTrace](../profiling/media/diagintellitrace.png "DiagIntelliTrace")  
  
 [IntelliTrace](../debugger/intellitrace.md)를 사용하면 재현하기 힘든 디버그 오류와 함수 호출 및 디버거 이벤트 중 **로컬** 창의 데이터를 검토하고, 특정 이벤트를 기록할 수 있습니다.  IntelliTrace는 본래 디버깅 도구이지만, 성능 조사에 사용할 수 있는 정보도 제공합니다. 이 도구는 데스크톱, Windows 유니버설, ASP.NET C# 앱의 Visual Studio Enterprise에서만 사용할 수 있습니다. IntelliTrace는 디버깅 중에 **진단 도구** 창에서(**디버그/Windows/진단 도구 표시**) 찾을 수 있습니다.  
  
## <a name="profiling-in-production"></a>프로덕션에서 프로파일링  
 프로덕션에서 프로파일링에 권장되는 방법은 [vsperf.exe를 사용하여 명령줄](../profiling/using-the-profiling-tools-from-the-command-line.md) 에서 프로파일링하여 CPU 프로필을 수집하는 것입니다. Azure 앱 서비스의 원격 프로파일링 지원의 경우, [서버 탐색기 또는 Kudu 포털](https://azure.microsoft.com/en-us/blog/remote-profiling-support-in-azure-app-service/)을 통해 프로파일링할 수 있습니다.  
  
## <a name="which-tool-should-i-use"></a>사용해야 하는 도구  
 다음 테이블에는 Visual Studio가 제안하는 다양한 도구 및 그와 함께 사용할 수 있는 다양한 프로젝트 형식이 나열되어 있습니다.  
  
|성능 도구|Windows 바탕 화면|Windows 유니버설/스토어|ASP.NET/ASP.NET Core|  
|----------------------|---------------------|------------------------------|-------------|  
|[메모리 사용](../profiling/memory-usage.md)|예|예|예|  
|[CPU 사용량](../profiling/cpu-usage.md)|예|예|예|  
|[GPU 사용량](../debugger/gpu-usage.md)|예|예|no|  
|[응용 프로그램 타임라인](../profiling/application-timeline.md)|예|예|no|  
|[PerfTips](../profiling/perftips.md)|예|XAML은 예, HTML은 no|예|  
|[성능 탐색기](../profiling/performance-explorer.md)|예|no|예(ASP.NET Core의 경우 아니요)|  
|[IntelliTrace](../debugger/intellitrace.md)|.NET Enterprise만 해당|.NET Enterprise만 해당|.NET Enterprise만 해당|
|[네트워크 사용량](../profiling/network-usage.md)|no|예|no| 
|[HTML UI responsiveness](../profiling/html-ui-responsiveness.md)|no|HTML은 예, XAML은 no|no|  
|[JavaScript 메모리](../profiling/javascript-memory.md)|no|HTML은 예, XAML은 no|no|  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio IDE](../ide/visual-studio-ide.md)
