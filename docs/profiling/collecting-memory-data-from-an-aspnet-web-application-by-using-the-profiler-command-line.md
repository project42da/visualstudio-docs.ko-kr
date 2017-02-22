---
title: "프로파일러 명령줄을 사용하여 ASP.NET 웹 응용 프로그램의 메모리 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
ms.assetid: 57acf2b0-327a-4c0e-8078-ac2f6d99457d
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 프로파일러 명령줄을 사용하여 ASP.NET 웹 응용 프로그램의 메모리 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 단원에서는 **VSPerfCmd** 명령줄 도구를 사용하여 ASP.NET 웹 응용 프로그램에 대한 메모리 할당 및 개체 수명 데이터를 수집하는 절차와 옵션에 대해 설명합니다.  
  
> [!NOTE]
>  **VSPerfCmd** 도구를 사용하면 프로파일링을 일시 중지했다가 다시 시작하고, 프로세서 및 Windows 성능 카운터에서 추가 데이터를 수집하는 기능을 포함하여 프로파일링 도구의 모든 기능에 액세스할 수 있습니다.  이러한 기능이 필요하지 않은 경우에는 **VSPerfASPNETCmd** 명령줄 도구를 사용할 수도 있습니다.  이 명령줄 도구는 [VSPerfCmd](../profiling/vsperfcmd.md) 명령줄 도구와 달리 환경 변수를 설정하거나 컴퓨터를 다시 부팅할 필요가 없습니다.  자세한 내용은 [VSPerfASPNETCmd를 사용한 빠른 웹 사이트 프로파일링](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)을 참조하십시오.  
  
## 일반 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**실행 중인 ASP.NET 응용 프로그램에 프로파일러 연결**|-   [방법: ASP.NET 웹 응용 프로그램에 프로파일러를 연결하여 메모리 데이터 수집](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)|  
|**정적으로 컴파일된 이진 파일 계측**|-   [방법: 정적으로 컴파일된 ASP.NET 응용 프로그램 계측 및 메모리 데이터 수집](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
|**동적으로 컴파일된 이진 파일 계측**|-   [방법: 동적으로 컴파일된 ASP.NET 응용 프로그램 계측 및 메모리 데이터 수집](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
  
## 관련 작업  
  
### ASP.NET 웹 응용 프로그램 프로파일링  
  
|Task|관련 내용|  
|----------|-----------|  
|**샘플링 방법을 사용하여 프로파일링**|-   [샘플링을 사용하여 응용 프로그램 통계 수집](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**계측 방법을 사용하여 프로파일링**|-   [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method-from-the-command-line.md)|  
|**리소스 경합 및 스레드 작업 프로파일링**|-   [동시성 데이터 수집](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### .NET Framework 메모리 데이터 프로파일링  
  
|Task|관련 내용|  
|----------|-----------|  
|**독립 실행형\(클라이언트\) 응용 프로그램 프로파일링**|-   [.NET Framework 메모리 데이터 수집](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**서비스 프로파일링**|-   [.NET 메모리 데이터 수집](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### .NET 메모리 데이터 뷰 및 보고서 분석  
 [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md)  
  
## 참고 항목  
 [명령줄 프로파일링 도구 참조](../profiling/command-line-profiling-tools-reference.md)