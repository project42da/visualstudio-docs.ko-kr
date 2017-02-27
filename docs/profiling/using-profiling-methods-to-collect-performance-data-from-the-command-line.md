---
title: "명령줄에서 프로파일링 방법을 사용하여 성능 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5613fafc-f298-4e7a-9a2d-a853b61cdf9c
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# 명령줄에서 프로파일링 방법을 사용하여 성능 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 명령줄 도구와 옵션을 선택할 때는 프로파일링할 응용 프로그램의 종류, 사용할 프로파일링 방법, 대상 응용 프로그램이 네이티브 코드로 작성되었는지 아니면 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 코드로 작성되었는지 등의 요소를 고려합니다.  
  
 이 항목에서는 선택하는 프로파일링 방법에 따라 명령줄 절차 항목을 구성합니다.  
  
## 항목 내용  
 [샘플링 방법을 사용하여 성능 통계 수집](#BKMK_Using_the_sampling_method_to_collect_performance_statistics)  
  
 [계측 방법을 사용하여 자세한 타이밍 데이터 수집](#BKMK_Using_the_instrumentation_method_to_collect_detailed_timing_data)  
  
 [.NET 메모리 메서드를 사용하여 메모리 할당 및 개체 수명 데이터 수집](#BKMK_Using__NET_memory_methods_to_collect_memory_allocation_and_object_lifetime_data)  
  
 [동시성 방법을 사용하여 리소스 경합 및 스레드 작업 데이터 수집](#BKMK_Using_the_concurrency_method_to_collect_resource_contention_and_thread_activity_data)  
  
 [프로파일링 실행에 계층 상호 작용 데이터 추가](#BKMK_Adding_tier_interaction_data_to_a_profiling_run)  
  
##  <a name="BKMK_Using_the_sampling_method_to_collect_performance_statistics"></a> 샘플링 방법을 사용하여 성능 통계 수집  
 프로파일링 도구의 샘플링 방법은 프로파일링 실행 시 지정된 간격으로 성능 데이터를 수집하는 방법입니다.  샘플링 데이터는 CPU 바인딩된 성능 문제를 파악하는 데 유용하므로 응용 프로그램의 성능을 조사하려는 경우에 이 방법을 사용하면 좋습니다.  
  
 프로파일러와 응용 프로그램을 동시에 시작하거나, 실행 중인 응용 프로그램 인스턴스에 프로파일러를 연결할 수 있습니다.  
  
|Task|대상 응용 프로그램 종류|  
|----------|-------------------|  
|**응용 프로그램 시작**|-   [독립 실행형 응용 프로그램](../profiling/how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line.md)|  
|**실행 중인 프로세스에 연결**|-   [.NET Framework 독립 실행형 응용 프로그램](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)<br />-   [네이티브 독립 실행형 응용 프로그램](../Topic/How%20to:%20Attach%20the%20Profiler%20to%20a%20Native%20Stand-Alone%20Application%20and%20Collect%20Application%20Statistics%20by%20Using%20the%20Command%20Line.md)<br />-   [ASP.NET 웹 응용 프로그램](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [.NET 서비스](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [네이티브 서비스](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|  
  
##  <a name="BKMK_Using_the_instrumentation_method_to_collect_detailed_timing_data"></a> 계측 방법을 사용하여 자세한 타이밍 데이터 수집  
 프로파일링 도구의 계측 방법은 소프트웨어 프로브가 포함된 응용 프로그램 이진 파일의 복사본에서 성능 데이터를 수집하여 성능 정보를 기록하는 방법입니다.  계측 데이터는 계측되는 각 함수가 시작될 때와 끝날 때, 그리고 계측되는 함수에서 다른 함수를 호출할 때마다 수집됩니다.  계측 방법은 디스크 사용량과 같은 I\/O 문제가 포함된 성능 문제를 찾는 데 유용합니다.  
  
 [VInstr.exe](../profiling/vsinstr.md) 도구를 사용하여 계측된 이진 파일을 만들 수 있습니다.  프로파일러를 초기화한 후에는 대상 응용 프로그램을 실행할 때 계측된 이진 파일에서 데이터가 자동으로 수집됩니다.  
  
 **대상 응용 프로그램 종류**  
  
-   [.NET Framework 독립 실행형 구성 요소](../profiling/how-to-instrument-a-stand-alone-dotnet-framework-component-and-collect-timing-data-with-the-profiler-from-the-command-line.md)  
  
-   [네이티브 독립 실행형 구성 요소](../profiling/how-to-instrument-a-native-stand-alone-component-and-collect-timing-data-with-the-profiler-from-the-command-line.md)  
  
-   [정적으로 컴파일된 ASP.NET 웹 응용 프로그램](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler-by-using-the-command-line.md)  
  
-   [동적으로 컴파일된 ASP.NET 웹 응용 프로그램](../Topic/How%20to:%20Instrument%20a%20Dynamically%20Compiled%20ASP.NET%20Web%20Application%20and%20Collect%20Detailed%20Timing%20Data%20with%20the%20Profiler%20by%20Using%20the%20Command%20Line.md)  
  
-   [.NET 서비스](../profiling/how-to-instrument-a-dotnet-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)  
  
-   [네이티브 서비스](../profiling/how-to-instrument-a-native-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)  
  
##  <a name="BKMK_Using__NET_memory_methods_to_collect_memory_allocation_and_object_lifetime_data"></a> .NET 메모리 메서드를 사용하여 메모리 할당 및 개체 수명 데이터 수집  
 프로파일링 도구의 .NET 메모리 방법을 사용하면 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 메모리 할당 데이터와 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 개체 수명에 대한 정보를 수집할 수 있습니다.  
  
 프로파일러를 사용하여 대상 응용 프로그램을 시작하고, 실행 중인 응용 프로그램 인스턴스에 프로파일러를 연결하고, 응용 프로그램의 계측된 버전을 만들어 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 메모리 데이터와 함께 자세한 타이밍 정보를 수집할 수 있습니다.  
  
|Task|대상 응용 프로그램 종류|  
|----------|-------------------|  
|**응용 프로그램 시작**|-   [독립 실행형 .NET Framework 응용 프로그램](../Topic/How%20to:%20Launch%20a%20Stand-Alone%20.NET%20Framework%20Application%20with%20the%20Profiler%20to%20Collect%20Memory%20Data%20by%20Using%20the%20Command%20Line.md)|  
|**실행 중인 프로세스에 연결**|-   [.NET Framework 독립 실행형 응용 프로그램](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [ASP.NET 웹 응용 프로그램](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [.NET 서비스](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-memory-data-by-using-the-command-line.md)|  
|**모듈 계측**|-   [.NET Framework 독립 실행형 구성 요소](../profiling/how-to-instrument-a-stand-alone-dotnet-framework-component-and-collect-memory-data-with-the-profiler-by-using-the-command-line.md)<br />-   [정적으로 컴파일된 ASP.NET 웹 응용 프로그램](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)<br />-   [동적으로 컴파일된 ASP.NET 웹 응용 프로그램](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)<br />-   [.NET 서비스](../profiling/how-to-instrument-a-dotnet-framework-service-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
  
##  <a name="BKMK_Using_the_concurrency_method_to_collect_resource_contention_and_thread_activity_data"></a> 동시성 방법을 사용하여 리소스 경합 및 스레드 작업 데이터 수집  
 프로파일링 도구의 동시성 방법을 사용하면 다중 스레드 응용 프로그램에서 리소스 경합 데이터와 스레드 및 프로세스 작업 데이터를 수집할 수 있습니다.  
  
 프로파일러를 사용하여 응용 프로그램을 시작하거나, 실행 중인 응용 프로그램 인스턴스에 프로파일러를 연결할 수 있습니다.  
  
|Task|대상 응용 프로그램 종류|  
|----------|-------------------|  
|**응용 프로그램 시작**|-   [독립 실행형 .NET Framework 응용 프로그램](../profiling/how-to-launch-a-stand-alone-dotnet-framework-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [독립 실행형 네이티브 응용 프로그램](../profiling/how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**실행 중인 프로세스에 연결**|-   [.NET Framework 독립 실행형 응용 프로그램](../Topic/How%20to:%20Attach%20the%20Profiler%20to%20a%20.NET%20Framework%20Stand-Alone%20Application%20to%20Collect%20Concurrency%20Data%20by%20Using%20the%20Command%20Line.md)<br />-   [네이티브 독립 실행형 응용 프로그램](../Topic/How%20to:%20Attach%20the%20Profiler%20to%20a%20Native%20Stand-Alone%20Application%20and%20Collect%20Concurrency%20Data%20by%20Using%20the%20Command%20Line.md)<br />-   [ASP.NET 웹 응용 프로그램](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [.NET 서비스](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [네이티브 서비스](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
##  <a name="BKMK_Adding_tier_interaction_data_to_a_profiling_run"></a> 프로파일링 실행에 계층 상호 작용 데이터 추가  
 계층 상호 작용을 프로파일링 실행에 추가하는 것은, 데이터 명령줄 프로 파일링 도구를 사용하는 특정 프로시저가 필요 합니다.  [계층 상호 작용 데이터 수집](../profiling/adding-tier-interaction-data-from-the-command-line.md)을 참조하십시오.  
  
## 참고 항목  
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)