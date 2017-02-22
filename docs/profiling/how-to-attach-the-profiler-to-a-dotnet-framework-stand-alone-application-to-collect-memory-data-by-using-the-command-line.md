---
title: "방법: 명령줄을 통해 .NET Framework 독립 실행형 응용 프로그램에 프로파일러를 연결하여 메모리 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a869fa4-3c98-4e08-b5d9-f43523059f0e
caps.latest.revision: 33
caps.handback.revision: 33
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 명령줄을 통해 .NET Framework 독립 실행형 응용 프로그램에 프로파일러를 연결하여 메모리 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] 프로파일링 도구의 명령줄 도구를 사용하여 실행 중인 .NET Framework 독립 실행형\(클라이언트\) 응용 프로그램에 프로파일러를 연결하고 메모리 데이터를 수집하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  프로파일링 도구의 명령줄 도구는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 설치 디렉터리의 \\Team Tools\\Performance Tools 하위 디렉터리에 있습니다.  64비트 컴퓨터에서는 64비트 및 32비트 버전의 도구를 모두 사용할 수 있습니다.  프로파일러 명령줄 도구를 사용하려면 해당 도구 경로를 명령 프롬프트 창의 PATH 환경 변수에 추가하거나 명령 자체에 추가해야 합니다.  자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하십시오.  
  
 .NET Framework 응용 프로그램에 연결하고 메모리 데이터를 수집하려면 대상 응용 프로그램이 시작되기 전에 [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) 도구를 사용하여 적절한 환경 변수를 초기화해야 합니다.  응용 프로그램에 프로파일러가 연결되어 있을 때 **VSPerfCmd.exe** 도구를 사용하여 데이터 수집을 일시 중지했다가 다시 시작할 수 있습니다.  
  
 프로파일링 세션을 종료하려면 프로파일링된 모든 프로세스에서 프로파일러를 분리해야 하며 프로파일러를 명시적으로 종료해야 합니다.  대부분의 경우 세션을 종료할 때 프로파일링 환경 변수를 지우는 것이 좋습니다.  
  
## 프로파일러 연결  
  
#### 실행 중인 .NET Framework 응용 프로그램에 프로파일러를 연결하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  프로파일링 환경 변수를 초기화합니다.  다음을 입력합니다.  
  
     **VSPerfClrEnv** {**\/samplegc** &#124; **\/samplegclife**} \[**\/samplelineoff**\]  
  
    -   **\/samplegc** 및 **\/samplegclife** 옵션은 메모리 할당 데이터만 수집할지 아니면 메모리 할당 데이터와 개체 수명 데이터를 모두 수집할지를 지정합니다.  하나의 옵션만 지정해야 합니다.  
  
        |옵션|설명|  
        |--------|--------|  
        |**\/samplegc**|메모리 할당 데이터만 수집합니다.|  
        |**\/samplegclife**|메모리 할당 데이터와 개체 수명 데이터를 모두 수집합니다.|  
  
    -   **\/samplelineoff** 옵션은 소스 코드 줄 번호 데이터를 수집하지 않도록 합니다.  
  
3.  프로파일러를 시작합니다.  다음을 입력합니다.  
  
     **VSPerfCmd \/start:sample \/output:** `OutputFile` \[`Options`\]  
  
    -   [\/start](../profiling/start.md) **:sample** 옵션은 프로파일러를 초기화합니다.  
  
    -   **\/start**와 함께 [\/output](../profiling/output.md)**:**`OutputFile` 옵션을 사용해야 합니다.  `OutputFile`은 프로파일링 데이터 파일\(.vsp\)의 이름과 위치를 지정합니다.  
  
     다음 옵션을 **\/start:sample** 옵션과 함께 사용할 수 있습니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|프로파일링되는 프로세스를 소유하는 계정의 도메인 및 사용자 이름을 지정합니다.  이 옵션은 로그온한 사용자 이외의 사용자 권한으로 프로세스가 실행되는 경우에만 필요합니다.  해당 프로세스 소유자는 Windows 작업 관리자에서 프로세스 탭의 사용자 이름 열에 표시됩니다.|  
    |[\/crosssession &#124; \/cs](../profiling/crosssession.md)|다른 세션에서 프로세스를 프로파일링할 수 있도록 합니다.  이 옵션은 응용 프로그램이 다른 세션에서 실행되고 있는 경우에 필요합니다.  세션 식별자는 Windows 작업 관리자에서 프로세스 탭의 세션 ID 열에 표시됩니다.  **\/crosssession**의 약식 표현으로 **\/CS**를 지정해도 됩니다.|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|프로파일링 중 수집할 Windows 성능 카운터를 지정합니다.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|**\/wincounter**에만 사용합니다.  Windows 성능 카운터 수집 이벤트의 시간 간격\(밀리초\)을 지정합니다.  기본값은 500밀리초입니다.|  
  
4.  필요한 경우 일반적인 방식으로 대상 응용 프로그램을 시작합니다.  
  
5.  대상 응용 프로그램에 프로파일러를 연결합니다.  다음을 입력합니다.  
  
     **VSPerfCmd**  [\/attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} \[[\/targetclr](../profiling/targetclr.md)**:**`Version`\]  
  
    -   `PID`는 대상 응용 프로그램의 프로세스 ID를 지정합니다.  `ProcessName`은 프로세스의 이름을 지정합니다.  `ProcessName`을 지정할 경우 같은 이름의 프로세스가 여러 개 있으면 결과를 예측할 수 없습니다.  Windows 작업 관리자에서 실행 중인 모든 프로세스의 프로세스 ID를 볼 수 있습니다.  
  
    -   **\/targetclr:** `Version`은 응용 프로그램에 둘 이상의 CLR\(공용 언어 런타임\) 버전이 로드될 때 프로파일링할 런타임 버전을 지정합니다.  선택적 요소로서,  
  
## 데이터 수집 제어  
 대상 응용 프로그램이 실행 중일 때는 **VSPerfCmd.exe** 옵션을 사용하여 파일에 데이터를 기록하는 작업을 시작하고 중지하는 방법으로 데이터 수집을 제어할 수 있습니다.  데이터 수집을 제어하면 응용 프로그램의 시작 또는 종료와 같은 프로그램 실행의 특정 부분에 대해 데이터를 수집할 수 있습니다.  
  
#### 데이터 수집을 시작 및 중지하려면  
  
-   다음 옵션 쌍으로 데이터 수집을 시작하고 중지할 수 있습니다.  각 옵션을 별도의 명령줄에 지정합니다.  데이터 수집을 여러 번 설정하거나 해제할 수 있습니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|모든 프로세스에 대해 데이터 수집을 시작\(**\/globalon**\)하거나 중지\(**\/globaloff**\)합니다.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID` [\/processoff](../profiling/processon-and-processoff.md)**:**`PID`|`PID`로 지정된 프로세스에 대해 데이터 수집을 시작\(**\/processon**\)하거나 중지\(**\/processoff**\)합니다.|  
    |[\/attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [\/detach](../profiling/detach.md)\[**:**{`PID`&#124;`ProcName`}\]|**\/attach**는 `PID` 또는 프로세스 이름\(ProcName\)으로 지정된 프로세스에 대해 데이터 수집을 시작합니다.  **\/detach**는 지정된 프로세스 또는 모든 프로세스\(특정 프로세스가 지정되지 않은 경우\)에 대해 데이터 수집을 중지합니다.|  
  
## 프로파일링 세션 종료  
 프로파일링 세션을 종료하려면 프로파일링된 모든 프로세스에서 프로파일러를 분리해야 하며 프로파일러를 명시적으로 종료해야 합니다.  응용 프로그램을 닫거나 **VSPerfCmd \/detach** 옵션을 호출하여 샘플링 방법으로 프로파일링된 응용 프로그램에서 프로파일러를 분리할 수 있습니다.  그런 다음 **VSPerfCmd \/shutdown** 옵션을 호출하여 프로파일러를 해제하고 프로파일링 데이터 파일을 닫을 수 있습니다.  **VSPerfClrEnv \/off** 명령은 프로파일링 환경 변수를 지웁니다.  
  
#### 프로파일링 세션을 종료하려면  
  
1.  다음 단계 중 하나를 수행하여 대상 응용 프로그램에서 프로파일러를 분리합니다.  
  
    -   **VSPerfCmd \/detach**를 입력합니다.  
  
         또는  
  
    -   대상 응용 프로그램을 닫습니다.  
  
2.  프로파일러를 종료합니다.  다음을 입력합니다.  
  
     **VSPerfCmd**  [\/shutdown](../profiling/shutdown.md)  
  
3.  \(선택 사항\) 프로파일링 환경 변수를 지웁니다.  다음을 입력합니다.  
  
     **VSPerfCmd \/off**  
  
## 참고 항목  
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md)