---
title: "방법: 프로파일러 명령줄을 통해 동적으로 컴파일된 ASP.NET 웹 응용 프로그램 계측 및 메모리 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2cdd9903-39db-47e8-93dd-5e6a21bc3435
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 프로파일러 명령줄을 통해 동적으로 컴파일된 ASP.NET 웹 응용 프로그램 계측 및 메모리 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 명령줄 도구를 사용하여 동적으로 컴파일된 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램에 대한 자세한 .NET 메모리 할당 및 개체 수명 데이터를 계측 프로파일링 방법으로 수집하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  프로파일링 도구의 명령줄 도구는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 설치 디렉터리의 \\Team Tools\\Performance Tools 하위 디렉터리에 있습니다.  64비트 컴퓨터에서는 64비트 및 32비트 버전의 도구를 모두 사용할 수 있습니다.  프로파일러 명령줄 도구를 사용하려면 해당 도구 경로를 명령 프롬프트 창의 PATH 환경 변수에 추가하거나 명령 자체에 추가해야 합니다.  자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하십시오.  
  
 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램에서 성능 데이터를 수집하려면 [VSInstr.exe](../profiling/vsinstr.md) 도구에서 동적으로 컴파일된 응용 프로그램 파일을 계측할 수 있도록 대상 응용 프로그램의 web.config 파일을 수정합니다.  그런 다음 [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) 도구를 사용하여 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램을 호스팅하는 서버를 구성하고, 적절한 환경 변수를 설정하여 .NET 메모리 프로파일링을 사용하도록 설정한 후, 컴퓨터를 다시 시작합니다.  
  
 데이터를 수집하려면 프로파일러를 시작한 다음 대상 응용 프로그램을 실행합니다.  프로파일러가 응용 프로그램에 연결되어 있는 동안 데이터 수집을 일시 중지했다가 다시 시작할 수 있습니다. 적절한 데이터를 수집했으면 응용 프로그램을 닫고 IIS\(인터넷 정보 서비스\) 작업자 프로세스를 닫은 다음 프로파일러를 종료합니다.  
  
 프로파일링 작업을 완료했으면 web.config 파일과 웹 서버를 원래 상태로 되돌립니다.  
  
## ASP.NET 웹 응용 프로그램 및 웹 서버 구성  
  
#### ASP.NET 웹 응용 프로그램 및 웹 서버를 구성하려면  
  
1.  대상 응용 프로그램의 web.config 파일을 수정합니다.  [방법: 계측할 Web.Config 파일 수정 및 동적으로 컴파일된 ASP.NET 웹 응용 프로그램 프로파일링](../Topic/How%20to:%20Modify%20Web.Config%20Files%20to%20Instrument%20and%20Profile%20Dynamically%20Compiled%20ASP.NET%20Web%20Applications.md)를 참조하십시오.  
  
2.  웹 응용 프로그램을 호스팅하는 컴퓨터에서 명령 프롬프트 창을 엽니다.  
  
3.  프로파일링 환경 변수를 초기화합니다.  다음을 입력합니다.  
  
     **VSPerfClrEnv \/globaltracegc**  
  
     또는  
  
     **VSPerfClrEnv \/globaltracegclife**  
  
    -   **\/globaltracegc**를 사용하면 메모리 할당 데이터를 수집할 수 있습니다.  
  
    -   **\/globaltracegclife**를 사용하면 메모리 할당 데이터 및 개체 수명 데이터를 수집할 수 있습니다.  
  
4.  컴퓨터를 다시 시작합니다.  
  
## 프로파일링 세션 실행  
  
#### ASP.NET 웹 응용 프로그램을 프로파일링하려면  
  
1.  프로파일러를 시작합니다.  다음을 입력합니다.  
  
     **VSPerfCmd** [\/start](../profiling/start.md)**:trace** [\/output](../profiling/output.md)**:**`OutputFile` \[`Options`\]  
  
    -   **\/start:trace** 옵션은 프로파일러를 초기화합니다.  
  
    -   **\/start**와 함께 **\/output:**`OutputFile` 옵션을 사용해야 합니다.  `OutputFile`은 프로파일링 데이터 파일\(.vsp\)의 이름과 위치를 지정합니다.  
  
     다음 옵션을 **\/start:trace** 옵션과 함께 사용할 수 있습니다.  
  
    > [!NOTE]
    >  **\/user** 및 **\/crosssession** 옵션은 대개 ASP.NET 응용 프로그램에 필요합니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스를 소유하는 계정의 선택적 도메인 및 사용자 이름을 지정합니다.  이 옵션은 로그온한 사용자 이외의 사용자 권한으로 프로세스가 실행되는 경우에 필요합니다.  해당 이름은 Windows 작업 관리자에서 프로세스 탭의 사용자 이름 열에 표시됩니다.|  
    |[\/crosssession](../profiling/crosssession.md)|다른 세션에서 프로세스를 프로파일링할 수 있도록 합니다.  이 옵션은 응용 프로그램이 다른 세션에서 실행되고 있는 경우에 필요합니다.  세션 ID는 Windows 작업 관리자에서 프로세스 탭의 세션 ID 열에 표시됩니다.  **\/crosssession**의 약식 표현으로 **\/CS**를 지정해도 됩니다.|  
    |[\/globaloff](../profiling/globalon-and-globaloff.md)|데이터 수집이 일시 중지된 상태에서 프로파일러를 시작합니다.  프로파일링을 다시 시작하려면 [\/globalon](../profiling/globalon-and-globaloff.md)을 사용합니다.|  
    |[\/counter](../profiling/counter.md) **:** `Config`|`Config`에 지정된 프로세서 성능 카운터에서 정보를 수집합니다.  카운터 정보는 각 프로파일링 이벤트에서 수집된 데이터에 추가됩니다.|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|프로파일링 중 수집할 Windows 성능 카운터를 지정합니다.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|**\/wincounter**에만 사용합니다.  Windows 성능 카운터 수집 이벤트의 시간 간격\(밀리초\)을 지정합니다.  기본값은 500밀리초입니다.|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|프로파일링 중 수집할 ETW\(Windows용 이벤트 추적\) 이벤트를 지정합니다.  ETW 이벤트는 별도의 파일\(.etl\)에 수집됩니다.|  
  
2.  일반적인 방식으로 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램을 시작합니다.  
  
## 데이터 수집 제어  
 대상 응용 프로그램이 실행 중일 때는 **VSPerfCmd.exe** 옵션을 사용하여 프로파일러 데이터 파일에 데이터를 기록하는 작업을 시작하고 중지하는 방법으로 데이터 수집을 제어할 수 있습니다.  데이터 수집을 제어하면 응용 프로그램의 시작 또는 종료와 같은 프로그램 실행의 특정 부분에 대해 데이터를 수집할 수 있습니다.  
  
#### 데이터 수집을 시작 및 중지하려면  
  
-   다음 옵션 쌍으로 데이터 수집을 시작하고 중지할 수 있습니다.  각 옵션을 별도의 명령줄에 지정합니다.  데이터 수집을 여러 번 설정하거나 해제할 수 있습니다.  
  
    |옵션|설명|  
    |--------|--------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|모든 프로세스에 대해 데이터 수집을 시작\(**\/globalon**\)하거나 중지\(**\/globaloff**\)합니다.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID` [\/processoff](../profiling/processon-and-processoff.md)**:**`PID`|프로세스 ID\(`PID`\)로 지정된 프로세스에 대해 데이터 수집을 시작\(**\/processon**\)하거나 중지\(**\/processoff**\)합니다.|  
    |[\/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [\/threadoff](../profiling/threadon-and-threadoff.md)**:**`TID`|스레드 ID\(`TID`\)로 지정된 스레드에 대해 데이터 수집을 시작\(**\/threadon**\)하거나 중지\(**\/threadoff**\)합니다.|  
  
-   **VSPerfCmd.exe** [\/mark](../profiling/mark.md) 옵션을 사용하여 데이터 파일에 프로파일링 표시를 삽입할 수도 있습니다.  **\/mark** 명령은 식별자, 타임스탬프 및 선택적 사용자 정의 텍스트 문자열을 추가합니다.  표시를 사용하여 프로파일러 보고서와 데이터 뷰에서 데이터를 필터링할 수 있습니다.  
  
## 프로파일링 세션 종료  
 프로파일링 세션을 종료하려면 대상 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램을 닫고 IIS\(인터넷 정보 서비스\)를 중지하여 프로파일링되는 프로세스를 중지한 다음 프로파일러를 종료합니다.  그런 다음 IIS를 다시 시작합니다.  
  
#### 프로파일링 세션을 종료하려면  
  
1.  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램을 닫습니다.  
  
2.  IIS\(인터넷 정보 서비스\)를 다시 설정하여 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스를 닫습니다.  다음을 입력합니다.  
  
     **IISReset \/stop**  
  
3.  프로파일러를 종료합니다.  다음을 입력합니다.  
  
     **VSPerfCmd** [\/shutdown](../profiling/shutdown.md)  
  
4.  IIS를 다시 시작합니다.  다음을 입력합니다.  
  
     **IISReset \/start**  
  
## 응용 프로그램 및 컴퓨터 구성 복원  
 프로파일링을 모두 완료한 후에는 web.config 파일을 바꾸고, 프로파일링 환경 변수를 지운 다음, 컴퓨터를 다시 시작하여 서버와 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램을 원래 상태로 되돌립니다.  
  
#### 응용 프로그램 및 컴퓨터 구성을 복원하려면  
  
1.  web.config 파일을 원래 파일의 복사본으로 바꿉니다.  
  
2.  \(선택 사항\)  프로파일링 환경 변수를 지웁니다.  다음을 입력합니다.  
  
     **VSPerfCmd \/globaloff**  
  
3.  컴퓨터를 다시 시작합니다.  
  
## 참고 항목  
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md)