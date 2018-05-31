---
title: 프로파일러 명령줄을 사용하여 독립 실행형 응용 프로그램에 대한 동시성 데이터 수집 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- concurrency profiling method
- profiling tools,concurrency method
ms.assetid: 0a2c6d8a-50b3-48aa-b617-9137b049d21e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 20ae775a6dc49dd2a6dd3cb391eeaf69ff7fa32c
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2018
ms.locfileid: "34335946"
---
# <a name="collect-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line"></a>프로파일러 명령줄을 사용하여 독립 실행형 응용 프로그램에 대한 동시성 데이터 수집
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 동시성 방법을 사용하면 CPU 사용률, 스레드 경합, 스레드 마이그레이션, 동기화 지연, 겹친 IO 영역 및 기타 시스템 이벤트를 보여 주는 리소스 경합 데이터 및 스레드 작업 데이터를 수집할 수 있습니다.  
  

## <a name="common-tasks"></a>일반 작업  
  
|작업|관련 콘텐츠|  
|----------|---------------------|  
|**.NET Framework 응용 프로그램 시작 및 동시성 데이터 프로파일링**|-   [방법: .NET Framework 응용 프로그램을 시작하여 동시성 데이터 수집](../profiling/how-to-launch-a-stand-alone-dotnet-framework-app-to-collect-concurrency-data.md)|  
|**C/C++ 응용 프로그램 시작 및 동시성 데이터 프로파일링**|-   [방법: 네이티브 응용 프로그램을 시작하여 동시성 데이터 수집](../profiling/how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**실행 중인 .NET Framework 응용 프로그램에 프로파일러 연결**|-   [방법: .NET Framework 응용 프로그램에 프로파일러를 연결하여 동시성 데이터 수집](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-concurrency-data.md)|  
|**실행 중인 C/C++ 응용 프로그램에 프로파일러 연결**|-   [방법: 네이티브 응용 프로그램에 프로파일러 연결 및 동시성 데이터 수집](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>관련 작업
  
### <a name="profile-stand-alone-applications"></a>독립 실행형 응용 프로그램 프로파일링  
  
|작업|관련 콘텐츠|  
|----------|---------------------|  
|**샘플링 방법을 사용하여 프로파일링**|-   [샘플링을 사용하여 응용 프로그램 통계 수집](../profiling/collecting-application-statistics-for-stand-alone-applications.md)|  
|**계측 방법을 사용하여 프로파일링**|-   [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application.md)|  
|**.NET 메모리 할당 및 가비지 수집 프로파일링**|-   [.NET Framework 메모리 데이터 수집](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications.md)|  
|**계층 상호 작용 데이터 추가**|-   [계층 상호 작용 데이터 수집](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
### <a name="profile-concurrency-issues"></a>동시성 문제 프로파일링  
  
|작업|관련 콘텐츠|  
|----------|---------------------|  
|**ASP.NET 응용 프로그램 프로파일링**|-   [동시성 데이터 수집](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
|**서비스 프로파일링**|-   [동시성 데이터 수집](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
  
### <a name="analyze-concurrency-data-views-and-reports"></a>동시성 데이터 뷰 및 보고서 분석  
 [리소스 경합 데이터 뷰](../profiling/resource-contention-data-views.md)  
  
 [동시성 시각화 도우미](../profiling/concurrency-visualizer.md)  
  
## <a name="reference"></a>참조  
 [명령줄 프로파일링 도구 참조](../profiling/command-line-profiling-tools-reference.md)