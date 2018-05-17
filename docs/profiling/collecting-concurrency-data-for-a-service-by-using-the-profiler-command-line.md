---
title: 프로파일러 명령줄을 사용하여 서비스에 대한 동시성 데이터 수집 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 275aacba-b2af-4d34-8931-ee30d777a256
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e3bd10121973c88e7a211aa741664b8ffb9b7bbc
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line"></a>프로파일러 명령줄을 사용하여 서비스에 대한 동시성 데이터 수집
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 동시성 방법을 사용하면 CPU 사용률, 스레드 경합, 스레드 마이그레이션, 동기화 지연, 겹친 IO 영역 및 기타 시스템 이벤트를 보여 주는 리소스 경합 데이터 및 스레드 작업 데이터를 수집할 수 있습니다.  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능을 위해 Visual Studio 프로파일러가 이러한 플랫폼에서 데이터를 수집하는 방법을 상당히 변경해야 했습니다. 또한 UWP 앱에는 새로운 수집 기술도 필요합니다. [Windows 8 및 Windows Server 2012 응용 프로그램의 성능 도구](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하세요.  
  
## <a name="common-tasks"></a>일반 작업  
  
|작업|관련 내용|  
|----------|---------------------|  
|**실행 중인.NET 서비스에 연결**|-   [방법: .NET 서비스에 프로파일러를 연결하여 동시성 데이터 수집](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**계층 상호 작용 데이터 추가**|-   [계층 상호 작용 데이터 수집](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**실행 중인 C/C++ 서비스에 연결**|-   [방법: 네이티브 서비스에 프로파일러를 연결하여 동시성 데이터 수집](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>관련 작업  
  
### <a name="profiling-windows-services"></a>Windows 서비스 프로파일링  
  
|작업|관련 내용|  
|----------|---------------------|  
|**샘플링 방법을 사용하여 프로파일링**|-   [샘플링을 사용하여 응용 프로그램 통계 수집](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**계측 방법을 사용하여 프로파일링**|-   [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md)|  
|**Profile.NET 메모리 할당 및 가비지 수집**|-   [.NET 메모리 데이터 수집](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="profiling-concurrency-data"></a>동시성 데이터 프로파일링  
  
|작업|관련 내용|  
|----------|---------------------|  
|**독립 실행형 응용 프로그램 프로파일링**|-   [동시성 데이터 수집](../profiling/collecting-concurrency-data-for-stand-alone-applications.md)|  
|**ASP.NET 웹 응용 프로그램 프로파일링**|-   [동시성 데이터 수집](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="analyzing-concurrency-data-views-and-reports"></a>동시성 데이터 뷰 및 보고서 분석  
 [리소스 경합 데이터 뷰](../profiling/resource-contention-data-views.md)  
  
 [동시성 시각화 도우미](../profiling/concurrency-visualizer.md)  
  
## <a name="reference"></a>참조  
 [명령줄 프로파일링 도구 참조](../profiling/command-line-profiling-tools-reference.md)