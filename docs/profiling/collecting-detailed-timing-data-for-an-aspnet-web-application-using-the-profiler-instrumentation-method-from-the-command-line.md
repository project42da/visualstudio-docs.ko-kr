---
title: "명령줄에서 프로파일러 계측 방법을 사용하여 ASP.NET 웹 응용 프로그램에 대한 자세한 타이밍 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "instrumentation profiling 메서드"
  - "프로파일링 도구, 계측 방법"
ms.assetid: 29f2fc55-aaf7-4e18-a672-8815455fba73
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 명령줄에서 프로파일러 계측 방법을 사용하여 ASP.NET 웹 응용 프로그램에 대한 자세한 타이밍 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 단원에서는 **VSPerfCmd** 명령줄 도구와 계측 방법을 사용하여 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램에 대한 자세한 성능 데이터를 수집하는 절차와 옵션에 대해 설명합니다.  
  
> [!NOTE]
>  **VSPerfCmd** 도구를 사용하면 프로파일링을 일시 중지했다가 다시 시작하고, 프로세서 및 Windows 성능 카운터에서 추가 데이터를 수집하는 기능을 포함하여 프로파일링 도구의 모든 기능에 액세스할 수 있습니다.  이러한 기능이 필요하지 않은 경우에는 **VSPerfASPNETCmd** 명령줄 도구를 사용할 수도 있습니다.  이 명령줄 도구는 [VSPerfCmd](../profiling/vsperfcmd.md) 명령줄 도구와 달리 환경 변수를 설정하거나 컴퓨터를 다시 부팅할 필요가 없습니다.  자세한 내용은 [VSPerfASPNETCmd를 사용한 빠른 웹 사이트 프로파일링](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)을 참조하십시오.  
  
## 일반 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**정적으로 컴파일된 이진 파일 프로파일링**|-   [방법: 정적으로 컴파일된 ASP.NET 응용 프로그램 계측 및 자세한 타이밍 데이터 수집](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler-by-using-the-command-line.md)|  
|**동적으로 컴파일된 이진 파일 프로파일링**|-   [방법: 동적으로 컴파일된 ASP.NET 응용 프로그램 계측 및 자세한 타이밍 데이터 수집](../Topic/How%20to:%20Instrument%20a%20Dynamically%20Compiled%20ASP.NET%20Web%20Application%20and%20Collect%20Detailed%20Timing%20Data%20with%20the%20Profiler%20by%20Using%20the%20Command%20Line.md)|  
  
## 관련 작업  
  
### ASP.NET 웹 응용 프로그램 프로파일링  
  
|Task|관련 내용|  
|----------|-----------|  
|**샘플링 방법을 사용하여 프로파일링**|-   [샘플링을 사용하여 응용 프로그램 통계 수집](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**메모리 할당 및 가비지 수집 프로파일링**|-   [메모리 데이터 수집](../profiling/collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line.md)|  
|**리소스 경합 및 스레드 작업 프로파일링**|-   [동시성 데이터 수집](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### 계측 방법을 사용하여 프로파일링  
  
|Task|관련 내용|  
|----------|-----------|  
|**독립 실행형\(클라이언트\) 응용 프로그램 프로파일링**|-   [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**서비스 프로파일링**|-   [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
  
### 계측 데이터 뷰 및 보고서 분석  
 [계측 방법 데이터 뷰](../profiling/instrumentation-method-data-views.md)