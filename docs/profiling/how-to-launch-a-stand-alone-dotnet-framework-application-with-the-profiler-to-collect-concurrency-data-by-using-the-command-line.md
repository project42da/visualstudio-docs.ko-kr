---
title: "방법: 명령줄을 통해 프로파일러와 함께 독립 실행형 .NET Framework 응용 프로그램을 시작하여 동시성 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 17a48848-bd3e-44ef-9971-e39836ff1df2
caps.latest.revision: 28
caps.handback.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 명령줄을 통해 프로파일러와 함께 독립 실행형 .NET Framework 응용 프로그램을 시작하여 동시성 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 명령줄 도구를 사용하여 .NET Framework 독립 실행형\(클라이언트\) 응용 프로그램을 시작하고 프로세스 및 스레드 동시성 데이터를 수집하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  프로파일링 도구의 명령줄 도구는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 설치 디렉터리의 \\Team Tools\\Performance Tools 하위 디렉터리에 있습니다.  64비트 컴퓨터에서는 64비트 및 32비트 버전의 도구를 모두 사용할 수 있습니다.  프로파일러 명령줄 도구를 사용하려면 해당 도구 경로를 명령 프롬프트 창의 PATH 환경 변수에 추가하거나 명령 자체에 추가해야 합니다.  자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하십시오.  
  
 응용 프로그램에 프로파일러가 연결된 경우 데이터 수집을 일시 중지했다가 다시 시작할 수 있습니다.  프로파일링 세션을 종료하려면 프로파일러가 응용 프로그램에 더 이상 연결되어 있지 않아야 하며 프로파일러를 명시적으로 종료해야 합니다.  
  
## 프로파일러를 사용하여 응용 프로그램 시작  
 프로파일러를 사용하여 .NET Framework 대상 응용 프로그램을 실행하려면 VSPerfClrEnv.exe를 사용하여 .NET Framework 프로파일링 변수를 설정합니다.  그런 다음 VSPerfCmd **\/start** 및 **\/launch** 옵션을 사용하여 프로파일러를 초기화하고 응용 프로그램을 시작합니다.  단일 명령줄에서 **\/start** 및 **\/launch**와 각각에 해당하는 옵션을 지정할 수 있습니다.  명령줄에 **\/globaloff** 옵션을 추가하여 대상 응용 프로그램이 시작될 때 데이터 수집을 일시 중지할 수도 있습니다.  그런 다음 별도의 명령줄에서 **\/globalon**을 사용하여 데이터 수집을 시작합니다.  
  
#### 프로파일러를 사용하여 응용 프로그램을 시작하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  프로파일러를 시작합니다.  다음을 입력합니다.  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **\/start:concurrency**\[**,**{**ResourceOnly**&#124;**ThreadOnly**}\] **\/output:**`OutputFile` \[`Options`\]  
  
    -   [\/start](../profiling/start.md) 옵션은 프로파일러를 초기화합니다.  
  
        |||  
        |-|-|  
        |**\/start:concurrency**|리소스 경합 및 스레드 실행 데이터 모두를 수집합니다.|  
        |**\/start:concurrency,resourceonly**|리소스 경합 데이터만 수집합니다.|  
        |**\/start:concurrency,threadonly**|스레드 실행 데이터만 수집합니다.|  
  
    -   **\/start**와 함께 [\/output](../profiling/output.md)**:**`OutputFile` 옵션을 사용해야 합니다.  `OutputFile`은 프로파일링 데이터 파일\(.vsp\)의 이름과 위치를 지정합니다.  
  
     다음 옵션을 **\/start:concurrency** 옵션과 함께 사용할 수 있습니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`domain\`\]`username`|프로파일러에 대한 액세스 권한을 부여할 계정의 선택적 도메인 및 사용자 이름을 지정합니다.|  
    |[\/crosssession](../profiling/crosssession.md)|다른 로그온 세션에서 프로세스를 프로파일링할 수 있도록 합니다.|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|프로파일링 중 수집할 Windows 성능 카운터를 지정합니다.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|**\/wincounter**에만 사용합니다.  Windows 성능 카운터 수집 이벤트의 시간 간격\(밀리초\)을 지정합니다.  기본값은 500밀리초입니다.|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|프로파일링 중 수집할 ETW\(Windows용 이벤트 추적\) 이벤트를 지정합니다.  ETW 이벤트는 별도의 파일\(.etl\)에 수집됩니다.|  
  
3.  대상 응용 프로그램을 시작합니다.  다음을 입력합니다.  
  
     **VSPerfCmd**  [\/launch](../profiling/launch.md) **:** `AppName` \[`Options`\] \[`Sample Event`\]  
  
     다음 옵션을 **\/launch** 옵션과 함께 사용할 수 있습니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/args](../profiling/args.md) **:** `Arguments`|대상 응용 프로그램에 전달할 명령줄 인수가 들어 있는 문자열을 지정합니다.|  
    |[\/console](../profiling/console.md)|대상 명령줄 응용 프로그램을 별도의 창에서 시작합니다.|  
    |[\/targetclr](../profiling/targetclr.md) **:** `Version`|응용 프로그램에 둘 이상의 런타임 버전이 로드될 때 프로파일링할 CLR\(공용 언어 런타임\) 버전을 지정합니다.|  
  
## 데이터 수집 제어  
 대상 응용 프로그램이 실행 중일 때는 VSPerfCmd.exe 옵션을 사용하여 파일에 데이터를 기록하는 작업을 시작하고 중지하는 방법으로 데이터 수집을 제어할 수 있습니다.  데이터 수집을 제어하면 응용 프로그램의 시작 또는 종료와 같은 프로그램 실행의 특정 부분에 대해 데이터를 수집할 수 있습니다.  
  
#### 데이터 수집을 시작 및 중지하려면  
  
1.  다음과 같은 VSPerfCmd.exe 옵션 쌍으로 데이터 수집을 시작하고 중지할 수 있습니다.  각 옵션을 별도의 명령줄에 지정합니다.  데이터 수집을 여러 번 설정하거나 해제할 수 있습니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|모든 프로세스에 대해 데이터 수집을 시작\(**\/globalon**\)하거나 중지\(**\/globaloff**\)합니다.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID` [\/processoff](../profiling/processon-and-processoff.md)**:**`PID`|프로세스 ID\(`PID`\)로 지정된 프로세스에 대해 데이터 수집을 시작\(**\/processon**\)하거나 중지\(**\/processoff**\)합니다.|  
    |[\/attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [\/detach](../profiling/detach.md)\[**:**{`PID`&#124;`ProcName`}\]|**\/attach**는 프로세스 ID\(`PID`\) 또는 프로세스 이름\(ProcName\)으로 지정된 프로세스에 대해 데이터 수집을 시작합니다.  **\/detach**는 지정된 프로세스 또는 모든 프로세스\(특정 프로세스가 지정되지 않은 경우\)에 대해 데이터 수집을 중지합니다.|  
  
## 프로파일링 세션 종료  
 프로파일링 세션을 종료하려면 프로파일러에서 데이터를 수집하고 있지 않아야 합니다.  프로파일링된 응용 프로그램을 닫거나 **VSPerfCmd \/detach** 옵션을 호출하여 데이터 수집을 중지할 수 있습니다.  그런 다음 **VSPerfCmd \/shutdown** 옵션을 호출하여 프로파일러를 해제하고 프로파일링 데이터 파일을 닫을 수 있습니다.  **VSPerfClrEnv \/off** 명령은 프로파일링 환경 변수를 지웁니다.  
  
#### 프로파일링 세션을 종료하려면  
  
1.  다음 중 하나를 수행하여 대상 응용 프로그램에서 프로파일러를 분리합니다.  
  
    -   대상 응용 프로그램을 닫습니다.  
  
         또는  
  
    -   **VSPerfCmd \/detach**를 입력합니다.  
  
2.  프로파일러를 종료합니다.  
  
     **VSPerfCmd**  [\/shutdown](../profiling/shutdown.md)  
  
## 참고 항목  
 [동시성 데이터 수집](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)