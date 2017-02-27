---
title: "독립 실행형 응용 프로그램의 명령줄 프로파일링 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로파일링 도구, 독립 실행형 응용 프로그램"
  - "독립 실행형 응용 프로그램 프로파일링"
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# 독립 실행형 응용 프로그램의 명령줄 프로파일링
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 단원에서는 명령줄에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구를 사용하여 독립 실행형\(클라이언트\) 응용 프로그램에 대한 성능 통계를 수집하는 절차와 옵션에 대해 설명합니다.  
  
## 일반 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**응용 프로그램 통계 수집:** 샘플링 방법을 사용하여 성능 통계를 수집할 수 있습니다.  샘플링 데이터는 CPU 사용률 문제를 분석하고 응용 프로그램의 일반적인 성능 특성을 이해하는 데 유용합니다.|-   [샘플링을 사용하여 응용 프로그램 통계 수집](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**자세한 타이밍 데이터 수집:** 계측 방법을 사용하여 자세한 타이밍 정보를 수집할 수 있습니다.  계측 데이터는 I\/O 문제를 분석하고 응용 프로그램 시나리오를 세부적으로 분석하는 데 유용합니다.|-   [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**.NET 메모리 데이터 수집:** 샘플링 또는 계측 방법을 사용하여 할당된 개체의 크기 및 개수를 보여 주는 .NET 메모리 할당 데이터를 수집할 수 있습니다.  또한 각 가비지 수집 세대에서 회수된 개체의 크기 및 개수를 보여 주는 개체 수명 데이터도 수집할 수 있습니다.|-   [.NET Framework 메모리 데이터 수집](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**동시성 데이터 수집:** 동시성 방법을 사용하여 CPU 사용률, 스레드 경합, 스레드 마이그레이션, 동기화 지연, 겹친 I\/O 영역 및 기타 시스템 이벤트를 보여 주는 스레드 작업 데이터와 리소스 경합 데이터를 수집할 수 있습니다.|-   [동시성 데이터 수집](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**계층 상호 작용 데이터 추가:** 응용 프로그램에서 Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] 데이터베이스에 대해 실행하는 동기 ADO.NET 호출에 대한 성능 데이터를 추가할 수 있습니다.  계층 상호 작용을 프로파일링 실행에 추가하는 것은, 데이터 명령줄 프로 파일링 도구를 사용하는 특정 프로시저가 필요 합니다.|-   [계층 상호 작용 데이터 수집](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**실습:** 단계별 절차를 따라 샘플링 또는 계측 방법을 사용하여 샘플 클라이언트 응용 프로그램을 프로파일링해 봅니다.|-   [연습: 샘플링을 사용하여 명령줄 프로파일링](../Topic/Walkthrough:%20Command-Line%20Profiling%20Using%20Sampling.md)<br />-   [연습: 계측을 사용하여 명령줄 프로파일링](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)|  
  
## 관련 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**ASP.NET 응용 프로그램 프로파일링**|-   [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**서비스 프로파일링**|-   [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)|