---
title: "방법: 프로파일러 명령줄을 사용하여 .NET 서비스 계측 및 자세한 타이밍 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9f73593a-69a7-41b7-a21c-81d3ab0eb8fe
caps.latest.revision: 27
caps.handback.revision: 27
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 프로파일러 명령줄을 사용하여 .NET 서비스 계측 및 자세한 타이밍 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] 프로파일링 도구의 명령줄 도구를 사용하여 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 서비스를 계측하고 자세한 타이밍 데이터를 수집하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  운영 체제가 시작될 때만 시작되는 서비스와 같이 컴퓨터가 시작된 후 다시 시작할 수 없는 서비스는 계측 방법으로 프로파일링할 수 없습니다.  
>   
>  프로파일링 도구의 명령줄 도구는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 설치 디렉터리의 \\Team Tools\\Performance Tools 하위 디렉터리에 있습니다.  64비트 컴퓨터에서는 64비트 및 32비트 버전의 도구를 모두 사용할 수 있습니다.  프로파일러 명령줄 도구를 사용하려면 해당 도구 경로를 명령 프롬프트 창의 PATH 환경 변수에 추가하거나 명령 자체에 추가해야 합니다.  자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하십시오.  
>   
>  계층 상호 작용을 프로파일링 실행에 추가하는 것은, 데이터 명령줄 프로 파일링 도구를 사용하는 특정 프로시저가 필요 합니다.  [계층 상호 작용 데이터 수집](../profiling/adding-tier-interaction-data-from-the-command-line.md)를 참조하십시오.  
  
 계측 방법을 사용하여 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 서비스에서 자세한 타이밍 데이터를 수집하려면 [VSInstr.exe](../profiling/vsinstr.md) 도구를 사용하여 해당 구성 요소의 계측된 버전을 생성합니다.  그런 다음 계측되지 않은 버전의 서비스를 계측된 버전으로 바꿔 서비스가 수동으로 시작되도록 구성합니다.  [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) 도구를 사용하여 전역 프로파일링 환경 변수를 초기화하고 호스트 컴퓨터를 다시 시작한 다음 프로파일러를 시작합니다.  그런 다음 프로파일러를 시작합니다.  
  
 서비스가 시작되면 타이밍 데이터가 데이터 파일에 자동으로 수집됩니다.  프로파일링 세션 중에는 데이터 수집을 일시 중지했다가 다시 시작할 수 있습니다.  
  
 프로파일링 세션을 종료하려면 서비스를 해제한 다음 프로파일러를 명시적으로 종료합니다.  대부분의 경우 세션을 종료할 때 프로파일링 환경 변수를 지우는 것이 좋습니다.  
  
## 프로파일러를 사용하여 응용 프로그램 시작  
  
#### .NET Framework 서비스 프로파일링을 시작하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  **VSInstr** 도구를 사용하여 서비스 이진 파일의 계측된 버전을 생성합니다.  
  
3.  원본 이진 파일을 계측된 버전으로 바꿉니다.  Windows 서비스 제어 관리자에서 서비스 시작 유형이 수동으로 설정되어 있는지 확인합니다.  
  
4.  [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 프로파일링 환경 변수를 초기화합니다.  다음을 입력합니다.  
  
     **VSPerfClrEnv \/globaltraceon**  
  
5.  컴퓨터를 다시 시작합니다.  
  
6.  명령 프롬프트 창을 엽니다.  
  
7.  프로파일러를 시작합니다.  다음을 입력합니다.  
  
     **VSPerfCmd \/start:trace \/output:** `OutputFile` \[`Options`\]  
  
    -   [\/start](../profiling/start.md) **:trace** 옵션은 프로파일러를 초기화합니다.  
  
    -   **\/start**와 함께 [\/output](../profiling/output.md)**:**`OutputFile` 옵션을 사용해야 합니다.  `OutputFile`은 프로파일링 데이터 파일\(.vsp\)의 이름과 위치를 지정합니다.  
  
     다음 옵션 중 하나를 **\/start:trace** 옵션과 함께 사용할 수 있습니다.  
  
    > [!NOTE]
    >  **\/user** 및 **\/crosssession** 옵션은 대개 서비스를 프로파일링하는 데 필요합니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|프로파일링되는 프로세스를 소유하는 계정의 도메인 및 사용자 이름을 지정합니다.  이 옵션은 로그온한 사용자 이외의 사용자 권한으로 프로세스가 실행되는 경우에만 필요합니다.  해당 프로세스 소유자는 Windows 작업 관리자에서 프로세스 탭의 사용자 이름 열에 표시됩니다.|  
    |[\/crosssession](../profiling/crosssession.md)|다른 세션에서 프로세스를 프로파일링할 수 있도록 합니다.  이 옵션은 응용 프로그램이 다른 세션에서 실행되고 있는 경우에 필요합니다.  세션 ID는 Windows 작업 관리자에서 프로세스 탭의 세션 ID 열에 표시됩니다.  **\/crosssession**의 약식 표현으로 **\/CS**를 지정해도 됩니다.|  
    |[\/waitstart](../profiling/waitstart.md)\[**:**`Interval`\]|프로파일러가 초기화될 때까지 기다릴 수 있는 시간\(초\)을 지정합니다. 이 시간이 지나면 오류가 반환됩니다.  `Interval`을 지정하지 않으면 프로파일러는 무기한 기다립니다.  기본적으로 **\/start**는 즉시 반환됩니다.|  
    |[\/globaloff](../profiling/globalon-and-globaloff.md)|데이터 수집이 일시 중지된 상태에서 프로파일러를 시작하려면 **\/start** 명령줄에 **\/globaloff** 옵션을 추가합니다.  프로파일링을 다시 시작하려면 **\/globalon**을 사용합니다.|  
    |[\/counter](../profiling/counter.md) **:** `Config`|Config에 지정된 프로세서 성능 카운터에서 정보를 수집합니다.  카운터 정보는 각 프로파일링 이벤트에서 수집된 데이터에 추가됩니다.|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|프로파일링 중 수집할 Windows 성능 카운터를 지정합니다.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|**\/wincounter**에만 사용합니다.  Windows 성능 카운터 수집 이벤트의 시간 간격\(밀리초\)을 지정합니다.  기본값은 500밀리초입니다.|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|프로파일링 중 수집할 ETW\(Windows용 이벤트 추적\) 이벤트를 지정합니다.  ETW 이벤트는 별도의 파일\(.etl\)에 수집됩니다.|  
  
8.  Windows 서비스 제어 관리자에서 서비스를 시작합니다.  
  
## 데이터 수집 제어  
 서비스가 실행 중일 때 **VSPerfCmd.exe** 옵션을 사용하여 프로파일러 데이터 파일에 데이터를 쓰는 작업을 시작하거나 중지할 수 있습니다.  데이터 수집을 제어하면 서비스의 시작 또는 종료와 같은 프로그램 실행의 특정 부분에 대해 데이터를 수집할 수 있습니다.  
  
#### 데이터 수집을 시작 및 중지하려면  
  
-   다음과 같은 **VSPerfCmd** 옵션 쌍으로 데이터 수집을 시작하고 중지할 수 있습니다.  각 옵션을 별도의 명령줄에 지정합니다.  데이터 수집을 여러 번 설정하거나 해제할 수 있습니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|모든 프로세스에 대해 데이터 수집을 시작\(**\/globalon**\)하거나 중지\(**\/globaloff**\)합니다.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID` [\/processoff](../profiling/processon-and-processoff.md)**:**`PID`|프로세스 ID\(`PID`\)로 지정된 프로세스에 대해 데이터 수집을 시작\(**\/processon**\)하거나 중지\(**\/processoff**\)합니다.|  
    |[\/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [\/threadoff](../profiling/threadon-and-threadoff.md)**:**`TID`|스레드 ID\(`TID`\)로 지정된 스레드에 대해 데이터 수집을 시작\(**\/threadon**\)하거나 중지\(**\/threadoff**\)합니다.|  
  
## 프로파일링 세션 종료  
 프로파일링 세션을 종료하려면 계측된 구성 요소를 실행하고 있는 서비스를 중지한 다음 **VSPerfCmd** [\/shutdown](../profiling/shutdown.md) 옵션을 호출하여 프로파일러를 해제하고 프로파일링 데이터 파일을 닫습니다.  **VSPerfClrEnv \/globaloff** 명령은 프로파일링 환경 변수를 지웁니다.  
  
 새 환경 설정을 적용하려면 컴퓨터를 다시 시작해야 합니다.  
  
#### 프로파일링 세션을 종료하려면  
  
1.  서비스 제어 관리자에서 서비스를 중지합니다.  
  
2.  프로파일러를 종료합니다.  다음을 입력합니다.  
  
     **VSPerfCmd \/shutdown**  
  
3.  프로파일링을 모두 완료한 후 프로파일링 환경 변수를 지웁니다.  다음을 입력합니다.  
  
     **VSPerfClrEnv \/globaloff**  
  
4.  계측된 모듈을 원본으로 바꿉니다.  필요한 경우 서비스의 시작 유형을 다시 구성합니다.  
  
5.  컴퓨터를 다시 시작합니다.  
  
## 참고 항목  
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)   
 [계측 방법 데이터 뷰](../profiling/instrumentation-method-data-views.md)