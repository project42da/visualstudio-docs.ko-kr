---
title: '방법: 명령줄을 통해 .NET Framework 독립 실행형 응용 프로그램에 프로파일러를 연결하여 동시성 데이터 수집 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: fdd41576-797e-4312-8520-fee7bb767e4a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 710c0a8bbfacc0e1edca3a1852cd8b51218a5ce3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-attach-the-profiler-to-a-net-framework-stand-alone-application-to-collect-concurrency-data-by-using-the-command-line"></a>방법: 명령줄을 통해 .NET Framework 독립 실행형 응용 프로그램에 프로파일러를 연결하여 동시성 데이터 수집
이 항목은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구 명령줄 도구를 사용하여 프로파일러를 실행 중인 .NET Framework 독립 실행형(클라이언트) 응용 프로그램에 연결하고 프로세스 및 스레드 동시성 데이터를 수집하는 방법을 설명합니다.  
  
> [!NOTE]
>  프로파일링 도구의 명령줄 도구는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 설치 디렉터리의 \Team Tools\Performance Tools 하위 디렉터리에 있습니다. 64비트 컴퓨터에서는 도구의 64비트 및 32비트 버전을 둘 다 사용할 수 있습니다. 프로파일러 명령줄 도구를 사용하려면 도구 경로를 명령 프롬프트 창의 PATH 환경 변수에 추가하거나 명령 자체에 추가해야 합니다. 자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하세요.  
  
 프로파일러가 응용 프로그램에 연결되면 데이터 수집을 일시 중지하고 다시 시작할 수 있습니다. 프로파일링 세션을 종료하려면 프로파일러가 응용 프로그램에 연결되어 있으면 안 되고 프로파일러가 명시적으로 종료되어야 합니다.  
  
## <a name="attaching-the-profiler"></a>프로파일러 연결  
  
#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>실행 중인 .NET Framework 응용 프로그램에 프로파일러를 연결하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  프로파일러를 시작합니다. 유형:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency  /output:** `OutputFile` [`Options`]  
  
     **/start**에는 [/output](../profiling/output.md)**:**`OutputFile` 옵션이 필요합니다. `OutputFile`은 프로파일링 데이터(.vsp) 파일의 이름과 위치를 지정합니다.  
  
     **/start:concurrency** 옵션과 다음 옵션을 함께 사용할 수 있습니다.  
  
    |옵션|설명|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|프로파일링 중에 수집할 Windows 성능 카운터를 지정합니다.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|**/wincounter**와 함께 사용해야 합니다. Windows 성능 카운터 수집 이벤트 사이에 경과하는 시간(밀리초)을 지정합니다. 기본값은 500ms입니다.|  
    |[/events](../profiling/events-vsperfcmd.md) **:** `Config`|프로파일링 중에 수집할 ETW(Windows용 이벤트 추적) 이벤트를 지정합니다. ETW 이벤트는 별도의 파일(.etl)로 수집됩니다.|  
  
3.  일반적인 방법으로 대상 프로그램을 시작합니다.  
  
4.  대상 응용 프로그램에 프로파일러를 연결합니다. 유형:  
  
     **VSPerfCmd /attach:** `PID` [**/lineoff**] [**/targetclr:**`Version`]  
  
    -   `PID`는 대상 응용 프로그램의 프로세스 ID를 지정합니다. [Windows 작업 관리자]에서 모든 실행 중인 프로세스의 프로세스 ID를 볼 수 있습니다.  
  
    -   [/lineoff](../profiling/lineoff.md)는 줄 번호 데이터의 컬렉션을 사용하지 않도록 설정합니다.  
  
    -   [/targetclr](../profiling/targetclr.md) **:** `Version`은 한 응용 프로그램에 두 개 이상의 런타임 버전이 로드된 경우 프로파일링할 CLR(공용 언어 런타임) 버전을 지정합니다. 선택 사항입니다.  
  
## <a name="controlling-data-collection"></a>데이터 컬렉션 제어  
 대상 응용 프로그램이 실행 중이면 VSPerfCmd.exe 옵션을 사용하여 파일에 대한 데이터 쓰기를 시작하고 중지하는 방식으로 데이터 수집을 제어할 수 있습니다. 데이터 수집을 제어하면 응용 프로그램의 시작 또는 종료와 같이 프로그램 실행의 특정 부분에 대한 데이터를 수집할 수 있습니다.  
  
#### <a name="to-start-and-stop-data-collection"></a>데이터 수집을 시작 및 중지하려면  
  
-   VSPerfCmd.exe 옵션의 다음 쌍을 사용하여 데이터 수집을 시작 및 중지합니다. 각 옵션을 개별 명령줄에서 지정합니다. 데이터 수집을 여러 번 켜고 끌 수 있습니다.  
  
    |옵션|설명|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|모든 프로세스에 대한 데이터 수집을 시작(**/globalon**) 또는 중지(**/globaloff**)합니다.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|프로세스 ID(`PID`)로 지정된 프로세스에 대한 데이터 수집을 시작(**/processon**) 또는 중지(**/processoff**)합니다.|  
    |[/attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/attach**는 프로세스 ID(`PID`) 또는 프로세스 이름(ProcName)으로 지정된 프로세스에 대한 데이터 수집을 시작합니다. **/detach**는 지정된 프로세스 또는 모든 프로세스(특정 프로세스가 지정되지 않은 경우)에 대한 데이터 수집을 중지합니다.|  
  
## <a name="ending-the-profiling-session"></a>프로파일링 세션 종료  
 프로파일링 세션을 종료하려면 프로파일러가 데이터를 수집하고 있지 않아야 합니다. 응용 프로그램을 닫거나 **VSPerfCmd /detach** 옵션을 호출하여 동시성 방법으로 프로파일링된 응용 프로그램에서 데이터를 수집하는 작업을 중지할 수 있습니다. 그러고 나서 **VSPerfCmd /shutdown** 옵션을 호출하여 프로파일러를 끄고 프로파일링 데이터 파일을 닫습니다. **VSPerfClrEnv /off** 명령은 프로파일링 환경 변수를 지웁니다.  
  
#### <a name="to-end-a-profiling-session"></a>프로파일링 세션을 종료하려면  
  
1.  대상 응용 프로그램에서 프로파일러를 분리하려면 다음 중 하나를 수행합니다.  
  
    -   **VSPerfCmd /detach** 입력  
  
         또는  
  
    -   대상 응용 프로그램을 닫습니다.  
  
2.  프로파일러를 종료합니다. 유형:  
  
     VSPerfCmd[/shutdown](../profiling/shutdown.md)