---
title: "프로파일링 방법 이해 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.wizard.methodpage"
helpviewer_keywords: 
  - "프로파일링 도구, 프로파일링 방법"
ms.assetid: ea4881fd-bd04-4875-9b7b-28490d6706f9
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# 프로파일링 방법 이해
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 프로파일링 도구는 성능 데이터를 수집하는데 사용 할 수 있는 다섯 가지 방법을 제공합니다.  이 항목에서는 각각의 방법을 설명하고 데이터를 수집할 때 특정 방법을 사용하는 것이 적절한 몇 가지 시나리오를 제공합니다.  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능으로 Visual Studio 프로파일러가 해당 플랫폼에서 데이터를 수집하는 방식에 중요한 변경 사항이 발생합니다.  Windows 스토어 응용 프로그램에는 또한 새 컬렉션 기술이 필요합니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  
  
|메서드|설명|  
|---------|--------|  
|[샘플링](#sampling)|응용 프로그램에서 수행하는 작업에 대한 통계 데이터를 수집합니다.|  
|[계측](#instrumentation)|각 함수 호출에 대한 자세한 타이밍 정보를 수집합니다.|  
|[동시성](#concurrency)|다중 스레드 응용 프로그램에 대한 자세한 정보를 수집합니다.|  
|[.NET 메모리](#net_memory)|.NET 메모리 할당 및 가비지 수집에 대한 자세한 정보를 수집합니다.|  
|[계층 상호 작용](#tier_interaction)|SqlServer 데이터베이스를 대상으로 한 동기 ADO.NET 함수 호출에 대한 정보를 수집합니다.<br /><br /> 계층 상호 작용 프로파일링은 [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], 또는 [!INCLUDE[vs_pro_current_short](../profiling/includes/vs_pro_current_short_md.md)] 을 사용하여 수집 될 수 있습니다.  하지만, 계층 상호 작용 프로 파일링 데이터는 [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] 또는 [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] 에서만 볼 수 있습니다.|  
  
 일부 프로파일링 방법을 사용하여 소프트웨어 및 하드웨어 성능 카운터와 같은 추가 데이터를 수집할 수도 있습니다.  자세한 내용은 [추가 성능 데이터 수집](../profiling/collecting-additional-performance-data.md)을 참조하십시오.  
  
##  <a name="sampling"></a> 샘플링  
 샘플링 프로파일링 방법에서는 프로파일링 실행 중 응용 프로그램에서 수행되는 작업에 대한 통계 데이터를 수집합니다.  샘플링 방법은 단순하면서 응용 프로그램 메서드의 실행에 거의 영향을 주지 않습니다.  
  
 샘플링은 Visual Studio 프로파일링 도구의 기본 방법입니다.  다음과 같은 경우에 유용합니다.  
  
-   응용 프로그램의 성능을 처음 탐색하는 경우  
  
-   프로세서\(CPU\) 사용률과 관련된 성능 문제를 조사하려는 경우  
  
 샘플링 프로파일링 방법은 컴퓨터 프로세서를 설정된 간격으로 중단하고 함수 호출 스택을 수집합니다.  실행 중인 함수의 경우 전용 샘플 수가 증가하고, 호출 스택에서 해당 함수를 호출하는 모든 함수의 경우 포괄 샘플 수가 증가합니다.  샘플링 보고서에서는 프로파일링된 모듈, 함수, 소스 코드 줄 및 명령에 대해 이러한 샘플 수의 합계를 제공합니다.  
  
 기본적으로 프로파일러에서는 샘플링 간격을 CPU 사이클로 설정합니다.  간격 유형을 다른 CPU 성능 카운터로 변경하고 해당 간격의 카운터 이벤트 수를 설정할 수 있습니다.  ADO.NET을 통해 SQL 서버 데이터베이스를 대상으로 수행된 쿼리에 대한 정보를 제공하는 TIP\(계층 상호 작용 프로파일링\) 데이터도 수집할 수 있습니다.  
  
 [샘플링을 사용하여 성능 통계 수집](../profiling/collecting-performance-statistics-by-using-sampling.md)  
  
 [샘플링 데이터 값 이해](../profiling/understanding-sampling-data-values.md)  
  
 [샘플링 방법 데이터 뷰](../profiling/profiler-sampling-method-data-views.md)  
  
##  <a name="instrumentation"></a> 계측  
 계측 프로파일링 방법에서는 프로파일링되는 응용 프로그램의 함수 호출에 대한 자세한 타이밍 정보를 수집합니다.  계측 프로파일링은 다음과 같은 경우에 유용합니다.  
  
-   디스크 I\/O와 같은 입력\/출력 병목 현상을 조사하려는 경우  
  
-   특정 모듈 또는 함수 집합을 자세하게 조사하려는 경우  
  
 계측 방법에서는 계측되는 파일의 각 함수와 해당 함수에 의해 실행되는 각 함수 호출에 대한 타이밍 정보를 캡처하는 코드를 이진 파일에 삽입합니다.  또한 함수에서 파일에 쓰기와 같은 작업을 호출하는 시기를 식별합니다.  계측 보고서에서는 네 개의 값을 사용하여 함수 또는 소스 코드 줄에 소요된 총 시간을 나타냅니다.  
  
-   경과된 포괄 시간 \- 함수 또는 소스 줄을 실행하는 데 걸리는 총 시간입니다.  
  
-   응용 프로그램 포괄 시간 \- 운영 체제 호출에 걸리는 시간을 제외하고 함수 또는 소스 줄을 실행하는 데 걸리는 시간입니다.  
  
-   경과된 전용 시간 \- 함수 본문의 코드 또는 소스 코드 줄을 실행하는 데 걸리는 시간입니다.  해당 함수 또는 소스 줄에 의해 호출된 함수를 실행하는 데 걸리는 시간은 제외됩니다.  
  
-   응용 프로그램 전용 시간 \- 함수 본문의 코드 또는 소스 코드 줄을 실행하는 데 걸리는 시간입니다.  운영 체제에 대한 호출을 실행하는 데 걸리는 시간과 해당 함수 또는 소스 줄에 의해 호출된 함수를 실행하는 데 걸리는 시간은 제외됩니다.  
  
 계측 방법을 사용하여 CPU 성능 카운터와 소프트웨어 성능 카운터를 모두 수집할 수도 있습니다.  
  
 [계측 데이터 값 이해](../profiling/understanding-instrumentation-data-values.md)  
  
 [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)  
  
 [계측 방법 데이터 뷰](../profiling/instrumentation-method-data-views.md)  
  
##  <a name="concurrency"></a> 동시성  
 동시성 프로파일링 방법에서는 다중 스레드 응용 프로그램에 대한 정보를 수집합니다.  리소스 경합 프로파일링은 경쟁하는 스레드가 공유 리소스에 액세스하기 위해 대기하게 될 때마다 자세한 호출 스택 정보를 수집합니다.  또한 동시성 시각화는 다중 스레드 응용 프로그램이 해당 응용 프로그램, 하드웨어, 운영 체제 및 호스트 컴퓨터의 다른 프로세스와 상호 작용하는 방식에 대한 보다 일반적인 정보를 수집합니다.  
  
-   리소스 경합 보고서에는 총 경합 수와 대기가 발생한 모듈, 함수, 소스 코드 줄 및 명령에서 리소스를 기다린 총 시간이 표시됩니다.  시간 표시 그래프에는 경합이 발생한 시점이 표시됩니다.  
  
-   동시성 시각화 도우미에는 성능 병목 지점, 불충분한 CPU 사용률, 스레드 경합, 스레드 마이그레이션, 동기화 지연, 겹쳐 있는 I\/O 영역 및 기타 정보를 찾는 데 사용할 수 있는 그래픽 정보가 표시됩니다.  가능한 경우 그래픽 출력은 해당 호출 스택 및 소스 코드 데이터와 연결됩니다.  동시성 시각화 데이터는 명령줄 및 Windows 응용 프로그램의 경우에만 수집할 수 있습니다.  
  
 [리소스 경합 데이터 값 이해](../profiling/understanding-resource-contention-data-values.md)  
  
 [스레드 및 프로세스 동시성 데이터 수집](../profiling/collecting-thread-and-process-concurrency-data.md)  
  
 [리소스 경합 데이터 뷰](../profiling/resource-contention-data-views.md)  
  
 [동시성 시각화 도우미](../profiling/concurrency-visualizer.md)  
  
##  <a name="net_memory"></a> .NET 메모리  
 .NET 메모리 할당 프로파일링 방법에서는 프로파일링되는 응용 프로그램에서 .NET Framework 개체가 할당될 때마다 컴퓨터 프로세서가 중단됩니다.  개체 수명 데이터도 수집되는 경우 프로파일러에서는 .NET Framework 가비지 수집이 수행된 후마다 프로세서를 중단합니다.  
  
 프로파일러에서는 할당에서 만들어지거나 가비지 수집에서 삭제된 개체의 형식, 크기 및 수에 대한 정보를 수집합니다.  
  
-   할당 이벤트가 발생하면 프로파일러에서는 함수 호출 스택에 대한 추가 정보를 수집합니다.  현재 실행 중인 함수의 경우 전용 할당 수가 증가하고, 호출 스택에서 해당 함수를 호출하는 모든 함수의 경우 포괄 할당 수가 증가합니다. .NET 메모리 보고서에서는 프로파일링된 형식, 모듈, 함수, 소스 코드 줄 및 명령에 대해 이러한 할당 수의 합계를 제공합니다.  
  
-   가비지 수집이 발생하면 프로파일러에서는 삭제된 개체에 대한 데이터와 각 가비지 수집 세대의 개체에 대한 정보를 수집합니다.  프로파일링 실행이 종료되면 프로파일러에서는 명시적으로 삭제되지 않은 개체에 대한 데이터를 기록합니다.  개체 수명 보고서에는 프로파일링 실행 중 할당된 각 형식에 대한 합계가 표시됩니다.  
  
 .NET 메모리 프로파일링은 샘플링 또는 계측 모드에서 사용할 수 있습니다.  어떤 모드를 선택하든 .NET 메모리 프로파일링에 고유한 할당 및 개체 수명 보고서에는 영향을 주지 않습니다.  
  
-   샘플링 모드에서 .NET 메모리 프로파일링을 실행할 경우 프로파일러에서는 .NET 메모리 할당 이벤트를 간격으로 사용하며, 할당된 개체 수와 할당된 총 바이트 수를 보고서에 포괄 및 전용 값으로 표시합니다.  
  
-   계측 모드에서 .NET 메모리 프로파일링을 실행할 경우에는 포괄 및 전용 할당 값과 함께 자세한 타이밍 정보가 수집됩니다.  
  
 [메모리 할당 및 개체 수명 데이터 값 이해](../profiling/understanding-memory-allocation-and-object-lifetime-data-values.md)  
  
 [.NET 메모리 할당 및 수명 데이터 수집](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)  
  
 [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md)  
  
##  <a name="tier_interaction"></a> 계층 상호 작용  
 계층 상호 작용 프로파일링에서는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 페이지 또는 기타 응용 프로그램과 [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] 데이터베이스 간의 동기 [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] 호출에 대한 정보를 프로파일링 데이터 파일에 추가합니다.  이 데이터에는 호출 수 및 시간과 최대 시간 및 최소 시간이 포함됩니다.  계층 상호 작용 데이터는 샘플링, 계측, .NET 메모리 또는 동시성 방법으로 수집되는 프로파일링 데이터에 추가할 수 있습니다.  
  
 ![계층 상호 작용 프로파일링 데이터](../profiling/media/tierinteraction_profilingtools.png "TierInteraction\_ProfilingTools")  
프로파일링 도구에서 수집된 계층 상호 작용 데이터  
  
 [계층 상호 작용 데이터 수집](../profiling/collecting-tier-interaction-data.md)  
  
 [계층 상호 작용 뷰](../profiling/tier-interaction-views.md)  
  
## 참고 항목  
 [방법: 웹 사이트에 대한 성능 데이터 수집](../profiling/how-to-collect-performance-data-for-a-web-site.md)   
 [초보자를 위한 성능 프로파일링 지침](../profiling/beginners-guide-to-performance-profiling.md)