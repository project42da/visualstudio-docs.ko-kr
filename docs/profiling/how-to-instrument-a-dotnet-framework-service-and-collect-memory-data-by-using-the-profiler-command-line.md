---
title: "방법: 프로파일러 명령줄을 통해 .NET Framework 서비스 계측 및 메모리 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2fa072fc-05fe-4420-99c0-51d2ea3ac4ce
caps.latest.revision: 24
caps.handback.revision: 24
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 프로파일러 명령줄을 통해 .NET Framework 서비스 계측 및 메모리 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 명령줄 도구를 사용하여 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 서비스를 계측하고 메모리 사용량 데이터를 수집하는 방법에 대해 설명합니다.  메모리 할당 데이터만 수집하거나, 메모리 할당 데이터와 개체 수명 데이터를 모두 수집할 수 있습니다.  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능으로 Visual Studio 프로파일러가 해당 플랫폼에서 데이터를 수집하는 방식에 중요한 변경 사항이 발생합니다.  Windows 스토어 응용 프로그램에는 또한 새 컬렉션 기술이 필요합니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  
  
> [!NOTE]
>  운영 체제 시작 시 함께 시작되는 서비스와 같이 컴퓨터가 시작된 후 다시 시작할 수 없는 서비스는 프로파일링할 수 없습니다.  
>   
>  프로파일링 도구의 명령줄 도구는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 설치 디렉터리의 \\Team Tools\\Performance Tools 하위 디렉터리에 있습니다.  64비트 컴퓨터에서는 64비트 및 32비트 버전의 도구를 모두 사용할 수 있습니다.  프로파일러 명령줄 도구를 사용하려면 해당 도구 경로를 명령 프롬프트 창의 PATH 환경 변수에 추가하거나 명령 자체에 추가해야 합니다.  자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하십시오.  
  
## 프로파일링 세션 시작  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 서비스에서 성능 데이터를 수집하려면 [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) 도구를 사용하여 적절한 환경 변수를 초기화하고, [VSInstr.exe](../profiling/vsinstr.md) 도구를 사용하여 서비스 이진 파일의 계측된 복사본을 만듭니다.  
  
 해당 서비스를 호스팅하는 컴퓨터를 프로파일링에 맞게 구성하려면 해당 컴퓨터를 다시 시작해야 합니다.  또한 서비스 제어 관리자에서 서비스를 수동으로 시작해야 합니다.  그런 다음 프로파일러를 시작하고 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 서비스를 시작합니다.  
  
 계측된 구성 요소가 실행되면 메모리 데이터가 데이터 파일에 자동으로 수집됩니다.  프로파일링 세션 중에는 데이터 수집을 일시 중지했다가 다시 시작할 수 있습니다.  
  
 프로파일링 세션을 종료하려면 서비스를 닫은 다음 프로파일러를 명시적으로 종료합니다.  대부분의 경우 세션을 종료할 때 프로파일링 환경 변수를 지우는 것이 좋습니다.  
  
#### .NET Framework 서비스 프로파일링을 시작하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  **VSInstr** 도구를 사용하여 서비스 이진 파일의 계측된 버전을 생성합니다.  
  
3.  서비스 제어 관리자를 사용하여 원본 이진 파일을 계측된 버전으로 바꿉니다.  서비스 시작 유형이 수동으로 설정되어 있는지 확인합니다.  
  
4.  프로파일링 환경 변수를 초기화합니다.  다음을 입력합니다.  
  
     **VSPerfClrEnv** {**\/globaltracegc** &#124; **\/globaltracegclife**}  
  
    -   **\/globaltracegc**와 **\/globaltracegclife**를 사용하면 메모리 할당 데이터와 개체 수명 데이터를 수집할 수 있습니다.  
  
        |옵션|설명|  
        |--------|--------|  
        |**\/globaltracegc**|메모리 할당 데이터만 수집합니다.|  
        |**\/globaltracegclife**|메모리 할당 데이터와 개체 수명 데이터를 수집합니다.|  
  
5.  컴퓨터를 다시 시작합니다.  
  
6.  명령 프롬프트 창을 엽니다.  
  
7.  프로파일러를 시작합니다.  다음을 입력합니다.  
  
     **VSPerfCmd**  [\/start](../profiling/start.md) **:trace**  [\/output](../profiling/output.md) **:** `OutputFile` \[`Options`\]  
  
    -   **\/start: contention** 옵션은 프로파일러를 초기화합니다.  
  
    -   **\/start**와 함께 **\/output:**`OutputFile` 옵션을 사용해야 합니다.  `OutputFile`은 프로파일링 데이터 파일\(.vsp\)의 이름과 위치를 지정합니다.  
  
     다음 옵션을 **\/start:sample** 옵션과 함께 사용할 수 있습니다.  
  
    > [!NOTE]
    >  **\/user** 및 **\/crosssession** 옵션은 대개 서비스에 필요합니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|ASP.NET 작업자 프로세스를 소유하는 계정의 도메인 및 사용자 이름을 지정합니다.  이 옵션은 로그온한 사용자 이외의 사용자 권한으로 프로세스가 실행되는 경우에 필요합니다.  해당 프로세스 소유자는 Windows 작업 관리자에서 프로세스 탭의 사용자 이름 열에 표시됩니다.|  
    |[\/crosssession](../profiling/crosssession.md)|다른 로그온 세션에서 프로세스를 프로파일링할 수 있도록 합니다.  이 옵션은 ASP.NET 응용 프로그램이 다른 세션에서 실행되고 있는 경우에 필요합니다.  세션 ID는 Windows 작업 관리자에서 프로세스 탭의 세션 ID 열에 표시됩니다.  **\/crosssession**의 약식 표현으로 **\/CS**를 지정해도 됩니다.|  
    |[\/waitstart](../profiling/waitstart.md)\[**:**`Interval`\]|프로파일러가 초기화될 때까지 기다릴 수 있는 시간\(초\)을 지정합니다. 이 시간이 지나면 오류가 반환됩니다.  `Interval`을 지정하지 않으면 프로파일러는 무기한 기다립니다.  기본적으로 **\/start**는 즉시 반환됩니다.|  
    |[\/globaloff](../profiling/globalon-and-globaloff.md)|데이터 수집이 일시 중지된 상태에서 프로파일러를 시작하려면 **\/start** 명령줄에 **\/globaloff** 옵션을 추가합니다.  프로파일링을 다시 시작하려면 **\/globalon**을 사용합니다.|  
    |[\/counter](../profiling/counter.md) **:** `Config`|Config에 지정된 프로세서 성능 카운터에서 정보를 수집합니다.  카운터 정보는 각 프로파일링 이벤트에서 수집된 데이터에 추가됩니다.|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|프로파일링 중 수집할 Windows 성능 카운터를 지정합니다.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|**\/wincounter**에만 사용합니다.  Windows 성능 카운터 수집 이벤트의 시간 간격\(밀리초\)을 지정합니다.  기본값은 500밀리초입니다.|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|프로파일링 중 수집할 ETW\(Windows용 이벤트 추적\) 이벤트를 지정합니다.  ETW 이벤트는 별도의 파일\(.etl\)에 수집됩니다.|  
  
8.  필요한 경우 서비스를 시작합니다.  
  
9. 서비스에 프로파일러를 연결합니다.  다음을 입력합니다.  
  
     **VSPerfCmd \/attach:** `PID` &#124;`ProcessName`  
  
    -   서비스의 프로세스 ID 또는 프로세스 이름을 지정합니다.  Windows 작업 관리자에서 실행 중인 모든 프로세스의 프로세스 ID와 이름을 볼 수 있습니다.  
  
## 데이터 수집 제어  
 서비스가 실행 중일 때는 **VSPerfCmd.exe** 옵션으로 파일에 데이터를 기록하는 작업을 시작하고 중지하는 방법으로 데이터 수집을 제어할 수 있습니다.  데이터 수집을 제어하면 응용 프로그램의 시작 또는 종료와 같은 프로그램 실행의 특정 부분에 대해 데이터를 수집할 수 있습니다.  
  
#### 데이터 수집을 시작 및 중지하려면  
  
-   다음과 같은 **VSPerfCmd** 옵션 쌍으로 데이터 수집을 시작하고 중지할 수 있습니다.  각 옵션을 별도의 명령줄에 지정합니다.  데이터 수집을 여러 번 설정하거나 해제할 수 있습니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|모든 프로세스에 대해 데이터 수집을 시작\(**\/globalon**\)하거나 중지\(**\/globaloff**\)합니다.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID`  [\/processoff](../profiling/processon-and-processoff.md) **:** `PID`|프로세스 ID\(`PID`\)로 지정된 프로세스에 대해 데이터 수집을 시작\(**\/processon**\)하거나 중지\(**\/processoff**\)합니다.|  
    |[\/threadon](../profiling/threadon-and-threadoff.md) **:** `TID`  [\/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|스레드 ID\(`TID`\)로 지정된 스레드에 대해 데이터 수집을 시작\(**\/threadon**\)하거나 중지\(**\/threadoff**\)합니다.|  
  
## 프로파일링 세션 종료  
 프로파일링 세션을 종료하려면 계측된 구성 요소를 실행하고 있는 응용 프로그램을 닫은 다음 **VSPerfCmd** [\/shutdown](../profiling/shutdown.md) 옵션을 시작하여 프로파일러를 해제하고 프로파일링 데이터 파일을 닫습니다.  **VSPerfClrEnv \/globaloff** 명령은 프로파일링 환경 변수를 지웁니다.  
  
#### 프로파일링 세션을 종료하려면  
  
1.  서비스 제어 관리자에서 서비스를 중지합니다.  
  
2.  프로파일러를 종료합니다.  다음을 입력합니다.  
  
     **VSPerfCmd \/shutdown**  
  
3.  프로파일링을 모두 완료한 후 프로파일링 환경 변수를 지웁니다.  다음을 입력합니다.  
  
     **VSPerfClrEnv \/globaloff**  
  
     계측된 모듈을 원본으로 바꿉니다.  필요한 경우 서비스의 시작 유형을 다시 구성합니다.  
  
4.  컴퓨터를 다시 시작합니다.  
  
## 참고 항목  
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)   
 [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md)