---
title: "방법: 명령줄을 통해 ASP.NET 웹 응용 프로그램에 프로파일러를 연결하여 동시성 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e215fdd-55f8-43ef-9534-06542eefe223
caps.latest.revision: 29
caps.handback.revision: 29
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 명령줄을 통해 ASP.NET 웹 응용 프로그램에 프로파일러를 연결하여 동시성 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 명령줄 도구를 사용하여 ASP.NET 응용 프로그램에 프로파일러를 연결하고 프로세스 및 스레드 동시성 데이터를 수집하는 방법에 대해 설명합니다.  
  
 프로파일링 도구의 명령줄 도구는 Visual Studio 설치 디렉터리의 \\Team Tools\\Performance Tools 하위 디렉터리에 있습니다.  64비트 컴퓨터에서는 64비트 및 32비트 버전의 도구를 모두 사용할 수 있습니다.  명령 프롬프트에서 프로파일러를 사용하려면 해당 도구 경로를 **명령 프롬프트** 창의 PATH 환경 변수에 추가하거나 명령 자체에 추가해야 합니다.  자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하십시오.  
  
 동시성 데이터를 수집하려면 웹 사이트를 호스팅하는 ASP.NET 작업자 프로세스에 프로파일러를 연결합니다.  응용 프로그램에 프로파일러가 연결된 경우 데이터 수집을 일시 중지했다가 다시 시작할 수 있습니다.  프로파일링 세션을 종료하려면 프로파일러가 응용 프로그램에 더 이상 연결되어 있지 않아야 하며 프로파일러를 명시적으로 종료해야 합니다.  대부분의 경우 세션을 종료할 때 프로파일링 환경 변수를 지워야 합니다.  
  
## 프로파일러 연결  
  
#### ASP.NET 응용 프로그램에 프로파일러를 연결하려면  
  
1.  다음 명령을 입력하여 프로파일러를 시작합니다.  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **\/start:concurrency \/output:**`OutputFile` \[`Options`\]  
  
    -   [\/start](../profiling/start.md) 옵션은 리소스 경합 데이터를 수집하도록 프로파일러를 초기화합니다.  
  
    -   **\/start**와 함께 [\/output](../profiling/output.md)**:**`OutputFile` 옵션을 사용해야 합니다.  `OutputFile`은 프로파일링 데이터 파일\(.vsp\)의 이름과 위치를 지정합니다.  
  
     다음 표의 옵션을 **\/start** 옵션과 함께 사용할 수 있습니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain\`\]`UserName`|프로파일러에 대한 액세스 권한을 부여할 계정의 선택적 도메인 및 사용자 이름을 지정합니다.|  
    |[\/crosssession](../profiling/crosssession.md)|다른 로그온 세션에서 프로세스를 프로파일링할 수 있도록 합니다.|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|프로파일링 중 수집할 Windows 성능 카운터를 지정합니다.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|**\/wincounter**에만 사용합니다.  Windows 성능 카운터 수집 이벤트의 시간 간격\(밀리초\)을 지정합니다.  기본값은 500입니다.|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|프로파일링 중 수집할 ETW\(Windows용 이벤트 추적\) 이벤트를 지정합니다.  ETW 이벤트는 별도의 파일\(.etl\)에 수집됩니다.|  
  
2.  일반적인 방식으로 ASP.NET 응용 프로그램을 시작합니다.  
  
3.  **VSPerfCmd \/attach:** `PID` \[**\/targetclr:**`Version`\] 명령을 입력하여 ASP.NET 작업자 프로세스에 프로파일러를 연결합니다.  
  
    -   `PID`는 ASP.NET 작업자 프로세스의 ID 또는 이름을 지정합니다.  Windows 작업 관리자에서 실행 중인 모든 프로세스의 프로세스 ID를 볼 수 있습니다.  
  
    -   [\/targetclr](../profiling/targetclr.md) **:** `Version`은 응용 프로그램에 둘 이상의 런타임 버전이 로드될 때 프로파일링할 CLR\(공용 언어 런타임\) 버전을 지정합니다.  이 매개 변수는 선택적 요소입니다.  
  
## 데이터 수집 제어  
 응용 프로그램이 실행 중일 때는 VSPerfCmd.exe 옵션을 사용하여 파일에 데이터를 기록하는 작업을 시작하고 중지하는 방법으로 데이터 수집을 제어할 수 있습니다.  데이터 수집을 제어하면 응용 프로그램의 시작 또는 종료와 같은 프로그램 실행의 특정 부분에 대해 데이터를 수집할 수 있습니다.  
  
#### 데이터 수집을 시작 및 중지하려면  
  
-   다음 표에 나오는 VSPerfCmd 옵션 쌍으로 데이터 수집을 시작하고 중지할 수 있습니다.  각 옵션을 별도의 명령줄에 지정합니다.  데이터 수집을 여러 번 설정하거나 해제할 수 있습니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|모든 프로세스에 대해 데이터 수집을 시작\(**\/globalon**\)하거나 중지\(**\/globaloff**\)합니다.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID`  [processoff](../profiling/processon-and-processoff.md) **:** `PID`|프로세스 ID\(`PID`\)로 지정된 프로세스에 대해 데이터 수집을 시작\(**\/processon**\)하거나 중지\(**\/processoff**\)합니다.|  
    |[\/attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [\/detach](../profiling/detach.md)\[**:**{`PID`&#124;`ProcName`}\]|**\/attach**는 프로세스 ID\(`PID`\) 또는 프로세스 이름\(*ProcName*\)으로 지정된 프로세스에 대해 데이터 수집을 시작합니다.  **\/detach**는 지정된 프로세스 또는 모든 프로세스\(프로세스가 지정되지 않은 경우\)에 대해 데이터 수집을 중지합니다.|  
  
## 프로파일링 세션 종료  
 프로파일링 세션을 종료하려면 프로파일러에서 데이터를 수집하고 있지 않아야 합니다.  ASP.NET 작업자 프로세스를 다시 시작하거나 **VSPerfCmd \/detach** 옵션을 호출하여 동시성 방법으로 프로파일링되는 응용 프로그램에서 데이터 수집을 중지할 수 있습니다.  그런 다음 **VSPerfCmd \/shutdown** 옵션을 호출하여 프로파일러를 해제하고 프로파일링 데이터 파일을 닫을 수 있습니다.  **VSPerfClrEnv \/globaloff** 명령은 프로파일링 환경 변수를 지우지만 컴퓨터가 다시 시작되기 전까지 시스템 구성은 다시 설정되지 않습니다.  
  
#### 프로파일링 세션을 종료하려면  
  
1.  프로파일러를 닫거나 명령 프롬프트에서 다음 명령을 입력하여 대상 응용 프로그램에서 프로파일러를 분리합니다.  
  
     **VSPerfCmd \/detach**  
  
2.  명령 프롬프트에서 다음 명령을 입력하여 프로파일러를 종료합니다.  
  
     **VSPerfCmd**  [\/shutdown](../profiling/shutdown.md)  
  
## 참고 항목  
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [VSPerfASPNETCmd를 사용한 빠른 웹 사이트 프로파일링](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)