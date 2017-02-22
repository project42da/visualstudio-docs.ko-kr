---
title: "VSPerfCmd | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령줄, 도구"
  - "명령줄 도구, VSPerfCmd 도구"
  - "성능 도구, VSPerfCmd 도구"
  - "프로파일링 도구, VSPerfCmd"
  - "VSPerfCmd 도구"
ms.assetid: 778bc105-7643-46c4-a338-f3620e31125a
caps.latest.revision: 49
caps.handback.revision: 49
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# VSPerfCmd
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**VSPerfCmd.exe** 도구는 성능 데이터 수집을 시작하고 중지하는 데 사용합니다.  다음 구문이 사용됩니다.  
  
```  
VSPerfCmd [/U] [/options]  
```  
  
 다음 표에서는 **VSPerfCmd.exe** 도구 옵션에 대해 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|**U**|리디렉션된 콘솔 출력은 유니코드로 기록됩니다.  이 옵션을 가장 먼저 지정해야 합니다.|  
|[시작](../profiling/start.md) **:** `mode`|지정된 모드로 프로파일링 서비스를 시작합니다.|  
|[출력](../profiling/output.md) **:** `filename`|출력 파일 이름을 지정합니다.  **Start**에만 사용합니다.|  
|[CrossSession&#124;CS](../profiling/crosssession.md)|Windows 세션 간에 프로파일링을 허용합니다.  **Start**, **Attach** 또는 **Launch**에만 사용합니다.|  
|[사용자](../profiling/user-vsperfcmd.md) **:**\[`domain\`\]`username`|지정된 계정에 프로파일러 서비스에 대한 액세스를 허용합니다.  **Start**에만 사용합니다.|  
|[WaitStart](../profiling/waitstart.md)\[**:**`n`\]|데이터 수집 로거의 초기화를 기다립니다.  `n`을 지정하면 **VSPerfCmd**는 최대 `n`초 동안만 기다립니다.  `n`을 지정하지 않으면 **VSPerfCmd**는 무기한 기다립니다.  따라서 **VSPerfCmd**를 일괄 프로세스의 일부로 쉽게 사용할 수 있습니다.|  
|[카운터](../profiling/counter.md) **:** `cfg`|샘플 프로파일링 방법을 사용하는 경우에는 샘플링 간격으로 사용할 이벤트 수 및 CPU 카운터를 지정합니다.  카운터 값은 하나만 샘플링할 수 있습니다.<br /><br /> 계측 프로파일링 방법을 사용하는 경우에는 계측 지점마다 수집할 CPU 카운터를 지정합니다.  **Start:**`Trace`, **Attach**, 또는 **Launch**에만 사용합니다.|  
|[QueryCounters](../profiling/querycounters.md)|현재 컴퓨터에 적합한 CPU 카운터 목록을 표시합니다.|  
|[WinCounter](../profiling/wincounter.md) **:** *path*|프로필 표시 데이터와 함께 포함할 Windows 성능 카운터 이벤트를 지정합니다.  **Start**에만 사용합니다.|  
|[AutoMark](../profiling/automark.md) **:** *n*|Windows 성능 카운터 데이터 수집 이벤트의 간격\(밀리초\)을 지정합니다.  **WinCounter**과 함께 사용합니다.|  
|[이벤트](../profiling/events-vsperfcmd.md) **:** `option`|지정된 ETW\(Windows용 이벤트 추적\) 이벤트 수집을 제어합니다.  ETW 데이터는 프로파일링 데이터\(.vsp\) 파일이 아닌 .itl 파일에 수집됩니다.|  
|[Status](../profiling/status.md)|프로파일러의 상태, 현재 프로파일링 중인 프로세스에 대한 정보 및 프로파일러 제어 권한이 있는 계정을 표시합니다.|  
|[Shutdown](../profiling/shutdown.md)\[**:**`n`\]|프로파일링 데이터 파일을 닫고 프로파일러를 해제합니다.|  
|[GlobalOn](../profiling/globalon-and-globaloff.md)|**VSPerfCmd GlobalOff** 호출 후에 데이터 수집을 다시 시작합니다.|  
|[GlobalOff](../profiling/globalon-and-globaloff.md)|모든 데이터 수집을 중지하지만 프로파일링 세션을 끝내지는 않습니다.|  
|[ProcessOn](../profiling/processon-and-processoff.md) **:** `pid`|**VSPerfCmd ProcessOff** 호출에 의해 프로파일링이 일시 중지된 후, 지정된 프로세스에 대해 데이터 수집을 다시 시작합니다.|  
|[ProcessOff](../profiling/processon-and-processoff.md) **:** `pid`|지정된 프로세스에 대해 데이터 수집을 중지합니다.|  
|[ThreadOn 및 ThreadOff](../profiling/threadon-and-threadoff.md) **:** *tid*|**VSPerfCmd ThreadOff** 호출에 의해 프로파일링이 일시 중지된 후, 지정된 프로세스에 대해 프로파일링을 다시 시작합니다.  계측 방법으로 프로파일링하는 경우에만 **ThreadOn**을 사용합니다.|  
|[ThreadOn 및 ThreadOff](../profiling/threadon-and-threadoff.md) **:** *tid*|지정된 스레드에 대해 프로파일링을 일시 중지합니다.  계측 방법으로 프로파일링하는 경우에만 **ThreadOff**를 사용합니다.|  
|[표시](../profiling/mark.md) **:** *MarkNum*\[**,***MarkText***\]**|프로파일링 데이터 파일에 옵션 텍스트와 함께 표시를 삽입합니다.|  
  
## 샘플링 방법 옵션  
 다음 옵션은 샘플링 프로파일링 방법을 사용하는 경우에만 사용할 수 있습니다.  
  
|옵션|설명|  
|--------|--------|  
|[시작](../profiling/launch.md) **:** *Executable*|지정된 응용 프로그램을 시작하고 프로파일링을 시작합니다.|  
|[Args](../profiling/args.md) **:** *Arguments*|시작된 응용 프로그램에 전달할 명령줄 인수를 지정합니다.|  
|[콘솔](../profiling/console.md)|새 명령 프롬프트 창에서 지정된 명령을 시작합니다.|  
|[연결](../profiling/attach.md) **:** *PID*\[**,***PID*\]|지정된 프로세스의 프로파일링을 시작합니다.  프로세스 ID 또는 프로세스 이름으로 프로세스를 식별할 수 있습니다.|  
|[Detach](../profiling/detach.md)\[**:***PID*\[,*PID*\]\]|지정된 프로세스의 프로파일링을 중지합니다.  프로세스 ID 또는 프로세스 이름으로 프로세스를 식별할 수 있습니다.  프로세스를 지정하지 않으면 모든 프로세스에 대해 프로파일링이 중단됩니다.|  
|[GC](../profiling/gc-vsperfcmd.md)\[**:**{**Allocation** `&#124;` **Lifetime**}\]|.NET 메모리 할당 및 개체 수명 데이터를 수집합니다.  **VSPerfCmd Launch** 옵션에만 사용합니다.|  
  
### 샘플링 간격 옵션  
 다음 옵션은 샘플링 간격의 형식과 기간을 지정합니다.  기본값은 **Timer**입니다.  **Counter** 옵션을 사용하여 CPU 카운터를 간격으로 지정할 수도 있습니다.  이러한 옵션은 **Launch** 또는 프로파일링 세션의 첫 번째 **Attach**에만 지정할 수 있습니다.  
  
|옵션|설명|  
|--------|--------|  
|[PF](../profiling/pf.md)\[**:***n*\]|n\-번째 페이지 폴트마다 샘플링합니다\(기본값\=10\).|  
|[Sys](../profiling/sys-vsperfcmd.md)\[**:***n*\]|n\-번째 시스템 호출마다 샘플링합니다\(기본값\=10\).|  
|[Timer](../profiling/timer.md)\[**:***n*\]|n\-번째 프로세서 주기마다 샘플링합니다\(기본값\=10000000\).|  
  
## 서비스 구성 요소 및 커널 모드 장치 옵션  
 다음 Admin 옵션은 프로파일링 서비스 구성 요소나 커널 모드 장치 드라이버를 지원합니다.  Admin 옵션은 프로파일링 권한을 설정하고 프로파일링되는 서비스나 장치 드라이버를 제어합니다.  
  
 관리자 자격 증명으로 실행되는 명령 프롬프트에서 Admin 옵션을 실행해야 합니다.  
  
|옵션|설명|  
|--------|--------|  
|**Admin:Security** \<**ALLOW&#124;DENY**\> *Right*\[ *Right*\] \<*User*&#124;*Group*\>|지정된 사용자 또는 그룹에 대해 프로파일링 서비스 액세스를 허용하거나 거부합니다.<br /><br /> `Right`은 다음 중 하나일 수 있습니다.<br /><br /> CrossSession \- 사용자에게 서비스 액세스 권한을 부여하여 상호 세션 프로파일링을 수행할 수 있도록 합니다.<br /><br /> SampleProfiling \- 사용자에게 드라이버에 대한 액세스 권한을 부여하여 샘플링 프로파일링을 수행할 수 있도록 합니다.  추적 프로파일링 중에 커널 전환 정보에 액세스하는 데도 사용됩니다.<br /><br /> FullAccess \- 사용자에게 CrossSession 및 SampleProfiling 액세스 권한을 모두 부여합니다.|  
|**Admin:Security, List**|프로파일링 서비스의 현재 상태를 표시하고 사용자 권한을 나열합니다.|  
|**Admin:**  `` \<*Service*&#124;*Driver*\>\<**START**&#124;**STOP**&#124;**INSTALL**&#124;**UNINSTALL**\>|프로파일링 서비스 구성 요소\(서비스\)나 커널 모드 장치 드라이버\(드라이버\)를 시작하거나, 중지하거나, 설치하거나, 제거합니다.|  
|**Admin:**  `` \<*Service*&#124;*Driver*\>**AutoStart** `` \<**ON**&#124;**OFF**\>|다시 시작한 후에 프로파일링 서비스\(서비스\)나 커널 모드 장치 드라이버\(드라이버\)를 자동으로 시작하는 기능을 사용하거나 사용하지 않습니다.|  
  
## VSPerfCmd \/Driver  
 **VSPerfCmd \/Driver** 옵션은 현재 사용되지 않습니다.  이 기능을 위해 **VsPerfCmd Admin** 옵션을 사용합니다.  
  
## 참고 항목  
 [VSInstr](../profiling/vsinstr.md)   
 [VSPerfMon](../profiling/vsperfmon.md)   
 [VSPerfReport](../profiling/vsperfreport.md)