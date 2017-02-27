---
title: "서비스의 명령줄 프로파일링 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로파일링 도구, 서비스"
  - "서비스 프로파일링"
ms.assetid: f0d62318-b0e8-49c6-9a30-9f7a6adef2f6
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# 서비스의 명령줄 프로파일링
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 단원에서는 명령줄에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구를 사용하여 Windows 서비스에 대한 성능 데이터를 수집하는 절차와 옵션에 대해 설명합니다.  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능으로 Visual Studio 프로파일러가 해당 플랫폼에서 데이터를 수집하는 방식에 중요한 변경 사항이 발생합니다.  Windows 스토어 응용 프로그램에는 또한 새 컬렉션 기술이 필요합니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  
  
## 일반 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**응용 프로그램 통계 수집:** 샘플링 방법을 사용하여 성능 통계를 수집할 수 있습니다.  샘플링 데이터는 CPU 사용률 문제를 분석하고 응용 프로그램의 일반적인 성능 특성을 이해하는 데 유용합니다.|-   [샘플링을 사용하여 응용 프로그램 통계 수집](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**자세한 타이밍 데이터 수집:** 계측 방법을 사용하여 자세한 타이밍 정보를 수집할 수 있습니다.  계측 데이터는 IO 문제를 분석하고 응용 프로그램 시나리오를 세부적으로 분석하는 데 유용합니다.|-   [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**.NET 메모리 데이터 수집:** 샘플링 또는 계측 방법을 사용하여 할당된 개체의 크기 및 개수를 보여 주는 .NET 메모리 할당 데이터를 수집할 수 있습니다.  또한 각 가비지 수집 세대에서 회수된 개체의 크기 및 개수를 보여 주는 개체 수명 데이터도 수집할 수 있습니다.|-   [.NET 메모리 데이터 수집](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
|**동시성 데이터 수집:** 동시성 방법을 사용하여 CPU 사용률, 스레드 경합, 스레드 마이그레이션, 동기화 지연, 겹친 IO 영역 및 기타 시스템 이벤트를 보여 주는 스레드 작업 데이터와 리소스 경합 데이터를 수집할 수 있습니다.|-   [동시성 데이터 수집](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
|**계층 상호 작용 데이터 추가:** 서비스에서 Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] 데이터베이스에 대해 실행하는 동기 ADO.NET 호출에 대한 성능 데이터를 추가할 수 있습니다.|-   [계층 상호 작용 데이터 수집](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## 관련 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**독립 실행형\(클라이언트\) 응용 프로그램 프로파일링**|-   [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**ASP.NET 응용 프로그램 프로파일링**|-   [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)|