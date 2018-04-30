---
title: '방법: 명령줄을 통해 프로파일러와 함께 독립 실행형 .NET Framework 응용 프로그램을 시작하여 메모리 데이터 수집 | Microsoft 문서'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 3bc53041-91b7-4ad0-8413-f8bf2c4b3f5e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 456e8fff1b4e484648c1e30a9b588a4f5923fc91
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-launch-a-stand-alone-net-framework-application-with-the-profiler-to-collect-memory-data-by-using-the-command-line"></a>방법: 명령줄을 통해 프로파일러와 함께 독립 실행형 .NET Framework 응용 프로그램을 시작하여 메모리 데이터 수집
이 항목은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구 명령줄 도구를 사용하여 .NET Framework 독립 실행형(클라이언트) 응용 프로그램을 시작하고 메모리 데이터를 수집하는 방법을 설명합니다.  
  
 프로파일링 세션은 다음과 같은 세 부분으로 구성됩니다.  
  
-   프로파일러를 사용하여 응용 프로그램 시작  
  
-   프로파일링 데이터 수집  
  
-   프로파일링 세션 종료  
  
> [!NOTE]
>  프로파일링 도구의 명령줄 도구는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 설치 디렉터리의 \Team Tools\Performance Tools 하위 디렉터리에 있습니다. 64비트 컴퓨터에서는 도구의 64비트 및 32비트 버전을 둘 다 사용할 수 있습니다. 프로파일러 명령줄 도구를 사용하려면 도구 경로를 명령 프롬프트 창의 PATH 환경 변수에 추가하거나 명령 자체에 추가해야 합니다. 자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하세요.  
  
## <a name="starting-the-application-with-the-profiler"></a>프로파일러를 사용하여 응용 프로그램 시작  
 프로파일러를 사용하여 대상 응용 프로그램을 시작하려면 **VSPerfCmd.exe/start** 및 **/launch** 옵션을 사용하여 프로파일러를 초기화하고 응용 프로그램을 시작합니다. **/start** 및 **/launch**와 해당 개별 옵션을 하나의 명령줄에서 지정할 수 있습니다.  
  
 **/globaloff** 옵션을 추가하여 대상 응용 프로그램 시작 시 데이터 수집을 일시 중지할 수도 있습니다. 그런 다음 **/globalon**을 사용하여 데이터 수집을 시작합니다.  
  
#### <a name="to-start-an-application-by-using-the-profiler"></a>프로파일러를 사용하여 응용 프로그램을 시작하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  프로파일러를 시작합니다. 유형:  
  
     **VSPerfCmd /start:sample /output:** `OutputFile` [`Options`]  
  
    -   [/start](../profiling/start.md)**:sample** 옵션은 프로파일러를 초기화합니다.  
  
    -   **/start**에는 [/output](../profiling/output.md)**:**`OutputFile` 옵션이 필요합니다. `OutputFile`은 프로파일링 데이터(.vsp) 파일의 이름과 위치를 지정합니다.  
  
     **/start:sample** 옵션과 다음 옵션을 함께 사용할 수 있습니다.  
  
    |옵션|설명|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|프로파일링 중에 수집할 Windows 성능 카운터를 지정합니다.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|**/wincounter**와 함께 사용해야 합니다. Windows 성능 카운터 수집 이벤트 사이에 경과하는 시간(밀리초)을 지정합니다. 기본값은 500ms입니다.|  
  
3.  대상 응용 프로그램을 시작합니다. 유형:  
  
     **VSPerfCmd**  [/launch](../profiling/launch.md) **:** `appName` **/gc:**{**allocation**&#124;**lifetime**}[`Options`]  
  
    -   .NET Framework 메모리 데이터를 수집하려면 [/gc](../profiling/gc-vsperfcmd.md)**:**`Keyword` 옵션이 필요합니다. keyword 매개 변수는 메모리 할당 데이터를 수집할지, 아니면 메모리 할당 및 개체 수명 데이터를 둘 다 수집할지 지정합니다.  
  
        |키워드|설명|  
        |-------------|-----------------|  
        |**allocation**|메모리 할당 데이터만 수집합니다.|  
        |**lifetime**|메모리 할당 및 개체 수명 데이터를 둘 다 수집합니다.|  
  
     **/launch** 옵션과 다음 옵션을 함께 사용할 수 있습니다.  
  
    |옵션|설명|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:** `Arguments`|대상 응용 프로그램에 전달할 명령줄 인수가 포함된 문자열을 지정합니다.|  
    |[/console](../profiling/console.md)|대상 명령줄 응용 프로그램을 별도의 창에서 시작합니다.|  
    |[/events](../profiling/events-vsperfcmd.md) **:** `Config`|프로파일링 중에 수집할 ETW(Windows용 이벤트 추적) 이벤트를 지정합니다. ETW 이벤트는 별도의 파일(.etl)로 수집됩니다.|  
    |[/targetclr](../profiling/targetclr.md) **:** `Version`|한 응용 프로그램에 두 개 이상의 런타임 버전이 로드된 경우 프로파일링할 CLR(공용 언어 런타임) 버전을 지정합니다.|  
  
## <a name="controlling-data-collection"></a>데이터 컬렉션 제어  
 대상 응용 프로그램이 실행 중이면 **VSPerfCmd.exe** 옵션을 사용하여 파일에 대한 데이터 쓰기를 시작하고 중지하는 방식으로 데이터 수집을 제어할 수 있습니다. 데이터 수집을 제어하면 응용 프로그램의 시작 또는 종료와 같이 프로그램 실행의 특정 부분에 대한 데이터를 수집할 수 있습니다.  
  
#### <a name="to-start-and-stop-data-collection"></a>데이터 수집을 시작 및 중지하려면  
  
-   다음 옵션 쌍을 사용하여 데이터 수집을 시작 및 중지합니다. 각 옵션을 개별 명령줄에서 지정합니다. 데이터 수집을 여러 번 켜고 끌 수 있습니다.  
  
    |옵션|설명|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|모든 프로세스에 대한 데이터 수집을 시작(**/globalon**) 또는 중지(**/globaloff**)합니다.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [processoff](../profiling/processon-and-processoff.md) **:** `PID`|프로세스 ID(`PID`)로 지정된 프로세스에 대한 데이터 수집을 시작(**/processon**) 또는 중지(**/processoff**)합니다.|  
    |[/attach](../profiling/attach.md) **:** `PID` [/detach](../profiling/detach.md)|**/attach**는 `PID`(프로세스 ID)로 지정된 프로세스에 대한 데이터 수집을 시작합니다. **/detach**는 모든 프로세스에 대한 데이터 수집을 중지합니다.|  
  
-   **VSPerfCmd.exe**[/mark](../profiling/mark.md) 옵션을 사용하여 프로파일링 표시를 데이터 파일에 삽입할 수 있습니다. **/mark** 명령은 식별자, 타임스탬프 및 선택적 사용자 정의 텍스트 문자열을 추가합니다. 데이터 필터링에 표시를 사용할 수 있습니다.  
  
## <a name="ending-the-profiling-session"></a>프로파일링 세션 종료  
 프로파일링 세션을 종료하려면 프로파일러가 모든 프로파일링된 프로세스에서 분리되어야 하고 프로파일러가 명시적으로 종료되어야 합니다. 응용 프로그램을 닫거나 **VSPerfCmd /detach** 옵션을 호출하여 샘플링 방법으로 프로파일링된 응용 프로그램에서 프로파일러를 분리할 수 있습니다. 그러고 나서 **VSPerfCmd /shutdown** 옵션을 호출하여 프로파일러를 끄고 프로파일링 데이터 파일을 닫습니다. **VSPerfClrEnv /off** 명령은 프로파일링 환경 변수를 지웁니다.  
  
#### <a name="to-end-a-profiling-session"></a>프로파일링 세션을 종료하려면  
  
1.  대상 응용 프로그램에서 프로파일러를 분리하려면 다음 단계 중 하나를 수행합니다.  
  
    -   대상 응용 프로그램을 닫습니다.  
  
         또는  
  
    -   **VSPerfCmd /detach** 입력  
  
2.  프로파일러를 종료합니다. 유형:  
  
     **VSPerfCmd**  [/shutdown](../profiling/shutdown.md)  
  
## <a name="see-also"></a>참고 항목  
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md)