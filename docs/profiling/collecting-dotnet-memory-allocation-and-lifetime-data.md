---
title: ".NET 메모리 할당 및 수명 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET 메모리 프로파일링 방법"
  - "프로파일링 도구, .NET 메모리 방법"
ms.assetid: 62a6dd5f-db66-4456-9d57-f8913dbfe4d5
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# .NET 메모리 할당 및 수명 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구에서는 .NET 메모리 할당 및 개체 수명 데이터를 수집할 수 있으므로 응용 프로그램의 메모리 관련 성능 문제를 쉽게 찾을 수 있습니다.  
  
-   .NET 메모리 할당에 대한 데이터에는 할당된 .NET Framework 메모리 개체의 크기 및 개수가 포함됩니다.  
  
-   개체 수명 데이터에는 세 개의 가비지 수집 세대에서 가져온 .NET Framework 메모리 개체의 크기 및 개수가 포함됩니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능으로 Visual Studio 프로파일러가 해당 플랫폼에서 데이터를 수집하는 방식에 중요한 변경 사항이 발생합니다.  Windows 스토어 응용 프로그램에는 또한 새 컬렉션 기술이 필요합니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  
  
 샘플링 또는 계측 프로파일링 방법을 사용하여 데이터를 수집할 수 있습니다.  
  
-   샘플링 방법을 사용할 경우 프로파일러에서는 시작되거나 연결된 프로세스에 의해 생성된 .NET 메모리 할당과 개체를 모두 추적합니다.  
  
-   계측 방법을 사용할 경우 프로파일러에서는 계측된 모듈에 의해 생성된 .NET 메모리 할당과 개체만 추적합니다.  
  
> [!IMPORTANT]
>  샘플링 방법으로 .NET 메모리 데이터\(할당, 개체 수명, 또는 둘 모두\)를 수집하는 경우 사용자 지정 샘플링 이벤트는 모두 무시되며, 적절한 메모리 할당 이벤트가 데이터를 수집하는 데 사용됩니다.  
  
 .NET 메모리 할당의 프로파일링을 사용할 경우 할당 뷰도 사용할 수 있습니다.  .NET 수명 데이터의 프로파일링을 사용할 경우에는 개체 수명 뷰도 사용할 수 있습니다.  자세한 내용은 [할당 뷰](../profiling/dotnet-memory-allocations-view.md) 및 [개체 수명 뷰](../profiling/object-lifetime-view.md)를 참조하십시오.  
  
 프로파일링 도구의 명령줄 도구를 사용하여 .NET 메모리 데이터를 수집하는 방법에 대한 자세한 내용은 [명령줄에서 프로파일링 방법 사용](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md)의 ".NET 메모리 방법을 사용하여 메모리 할당 및 개체 수명 데이터 수집"을 참조하십시오.  
  
### .NET 메모리 데이터를 수집하려면  
  
1.  **성능 탐색기**에서 성능 세션을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
2.  *Performance Session* 속성 페이지 **대화 상자에서** 일반 **탭을 클릭하고** .NET 개체 할당 정보 수집 확인란을 선택합니다.  
  
3.  .NET 개체 수명 데이터를 수집하려면 **추가적으로 .NET 개체 수명 정보 수집** 확인란을 선택합니다.  
  
## 일반 작업  
 성능 세션의 *Performance Session* **속성 페이지** 대화 상자에서는 추가 옵션을 지정할 수 있습니다.  이 대화 상자를 열려면 다음을 수행합니다.  
  
-   **성능 탐색기**에서 성능 세션 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
 다음 표에서는 .NET 메모리 데이터를 수집할 때 *Performance Session*  **속성 페이지**대화 상자에서 지정할 수 있는 옵션과 관련된 작업을 설명합니다.  
  
|Task|관련 내용|  
|----------|-----------|  
|**일반** 페이지에서 생성된 프로파일링 데이터 파일\(.vsp\)에 대한 명명 세부 사항을 지정합니다.|-   [Collecting .NET Memory Allocation and Lifetime Data](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [방법: 프로파일링 데이터 파일 이름 옵션 설정](../profiling/how-to-set-performance-data-file-name-options.md)|  
|**시작** 페이지에서 코드 솔루션에 여러 개의 .exe 프로젝트가 포함된 경우 시작할 응용 프로그램을 선택합니다.|-   [계층 상호 작용 데이터 수집](../profiling/collecting-tier-interaction-data.md)|  
|**계층 상호 작용** 페이지에서 프로파일링 실행에 ADO.NET 호출 데이터를 추가합니다.|-   [계층 상호 작용 데이터 수집](../profiling/collecting-tier-interaction-data.md)|  
|**Windows 이벤트** 페이지에서 샘플링 데이터와 함께 수집할 ETW\(Windows용 이벤트 추적\) 이벤트를 하나 이상 지정합니다.|-   [방법: ETW\(Windows용 이벤트 추적\) 데이터 수집](../Topic/How%20to:%20Collect%20Event%20Tracing%20for%20Windows%20\(ETW\)%20Data.md)|  
|**Windows 카운터** 페이지에서 프로파일링 데이터에 표시로 추가할 운영 체제 성능 카운터를 하나 이상 지정합니다.|-   [방법: Windows 카운터 데이터 수집](../profiling/how-to-collect-windows-counter-data.md)|  
|**고급** 페이지에서 응용 프로그램 모듈이 여러 버전의 .NET Framework 런타임을 사용할 경우 프로파일링할 버전을 지정합니다.  기본적으로는 첫 번째로 로드되는 버전이 프로파일링됩니다.|-   [방법: 병렬 시나리오에서 프로파일링할 .NET Framework 런타임 지정](../Topic/How%20to:%20Specify%20the%20.NET%20Framework%20Runtime.md)|  
  
## 계측 작업  
 다음 표에서는 계측 방법을 사용하여 프로파일링할 경우 **속성 페이지** 대화 상자에서 지정할 수 있는 옵션과 관련된 작업을 설명합니다.  
  
|Task|관련 내용|  
|----------|-----------|  
|**이진 파일** 페이지에서 모듈의 계측된 복사본을 저장할 위치를 지정합니다.  기본적으로 원본 이진 파일은 백업 폴더로 이동됩니다.|-   [방법: 계측된 이진 파일 재배치](../profiling/how-to-relocate-instrumented-binaries.md)|  
|**계측** 페이지에서 프로파일링 오버헤드를 줄이기 위해 작은 함수를 프로파일링에서 제외하거나, ASP.NET 웹 페이지의 JavaScript 코드를 프로파일링하거나, 계측 프로세스 전후에 명령 프롬프트에서 실행할 명령을 지정합니다.|-   [방법: 계측에서 간단한 함수 제외 또는 포함](../Topic/How%20to:%20Exclude%20or%20Include%20Short%20Functions%20from%20Instrumentation.md)<br />-   [방법: 웹 페이지에서 JavaScript\(ECMA\) 코드 프로파일링](../Topic/How%20to:%20Profile%20JavaScript%20Code%20in%20Web%20Pages.md)<br />-   [방법: 계측 전 명령 및 계측 후 명령 지정](../Topic/How%20to:%20Specify%20Pre-%20and%20Post-Instrument%20Commands.md)|  
|**CPU 카운터** 페이지에서 프로파일링 데이터에 추가할 프로세서 성능 카운터를 하나 이상 지정합니다.|-   [방법: CPU 카운터 데이터 수집](../profiling/how-to-collect-cpu-counter-data.md)|  
|**고급** 페이지에서 특정 함수를 포함하거나 제외하는 옵션을 비롯하여 추가로 원하는 VSInstr.exe 옵션을 지정합니다.  VSInstr 옵션에 대한 자세한 내용은 [VSInstr](../profiling/vsinstr.md)을 참조하십시오.|-   [방법: 추가 계측 옵션 지정](../Topic/How%20to:%20Specify%20Additional%20Instrumentation%20Options.md)<br />-   [방법: 특정 함수로 계측 제한](../profiling/how-to-limit-instrumentation-to-specific-functions.md)|  
  
## 참고 항목  
 [성능 세션 구성](../profiling/configuring-performance-sessions.md)   
 [방법: 수집 방법 선택](../profiling/how-to-choose-collection-methods.md)   
 [성능 세션 속성](../profiling/performance-session-properties.md)