---
title: "ASP.NET 웹 응용 프로그램의 명령줄 프로파일링 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로파일링 ASP.NET 응용 프로그램"
  - "프로파일링 도구, ASP.NET 응용 프로그램"
ms.assetid: 897c00d5-5767-433b-a960-4a29c6023ede
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# ASP.NET 웹 응용 프로그램의 명령줄 프로파일링
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 단원에서는 명령줄에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구를 사용하여 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램에 대한 성능 데이터를 수집하는 절차와 옵션에 대해 설명합니다.  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능으로 Visual Studio 프로파일러가 해당 플랫폼에서 데이터를 수집하는 방식에 중요한 변경 사항이 발생합니다.  Windows 스토어 응용 프로그램에는 또한 새 컬렉션 기술이 필요합니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  
  
## 일반 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**기본 ASP.NET 프로파일링 데이터의 손쉬운 수집: VSPerfASPNETCmd** 도구를 사용하면 **VSPerfCmd**를 사용할 때 필요한 구성 및 IIS\(인터넷 정보 서비스\) 재시작을 수행하지 않고도 샘플링, 계측, .NET 메모리, 경합 또는 계층 상호 작용 데이터를 수집할 수 있습니다.  하지만 **VSPerfASPNETCmd**에서는 추가 데이터를 수집하거나 데이터 수집을 제어할 수는 없습니다. **Note:**  **VSPerfASPNETCmd**는 독립 실행형 프로파일러를 사용하여 ASP.NET 웹 사이트를 프로파일링할 때 기본적으로 사용되는 도구입니다.|-   [VSPerfASPNETCmd를 사용한 빠른 웹 사이트 프로파일링](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)|  
|**응용 프로그램 통계 수집:** 샘플링 방법을 사용하여 성능 통계를 수집할 수 있습니다.  샘플링 데이터는 CPU 사용량 문제를 분석하고 응용 프로그램의 일반적인 성능 특성을 이해하는 데 유용합니다.|-   [샘플링을 사용하여 응용 프로그램 통계 수집](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**자세한 타이밍 데이터 수집:** 계측 방법을 사용하여 자세한 타이밍 정보를 수집할 수 있습니다.  계측 데이터는 IO 문제를 분석하고 응용 프로그램 시나리오를 세부적으로 분석하는 데 유용합니다.|-   [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method-from-the-command-line.md)|  
|**.NET 메모리 데이터 수집:** 샘플링 또는 계측 방법을 사용하여 할당된 개체의 크기 및 개수를 보여 주는 .NET 메모리 할당 데이터를 수집할 수 있습니다.  또한 각 가비지 수집 세대에서 회수된 개체의 크기 및 개수를 보여 주는 개체 수명 데이터도 수집할 수 있습니다.|-   [메모리 데이터 수집](../profiling/collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line.md)|  
|**동시성 데이터 수집:** 동시성 방법을 사용하여 리소스 경합 데이터를 수집할 수 있습니다. **Note:**  웹 응용 프로그램에 대한 스레드 작업 및 시각화 데이터를 수집할 수는 없습니다.|-   [동시성 데이터 수집](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
|**계층 상호 작용 데이터 추가:** [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램에서 Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] 데이터베이스에 대해 실행하는 동기 [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] 호출에 대한 성능 데이터를 추가할 수 있습니다.|-   [계층 상호 작용 데이터 수집](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## 관련 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**독립 실행형\(클라이언트\) 응용 프로그램 프로파일링**|-   [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**서비스 프로파일링**|-   [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)|