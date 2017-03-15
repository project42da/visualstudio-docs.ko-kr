---
title: "명령줄에서 기본 프로파일링 보고서 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d73e21e-c04e-48ea-91cc-e517a5f2cd3f
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 명령줄에서 기본 프로파일링 보고서 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 .vsp 또는 .vsps 프로파일링 데이터 파일에서 쉼표로 구분된 값\(.csv\) 보고서를 생성하는 기본 VSPerfReport 명령에 대해 설명합니다.  모든 보고서 옵션에 대한 자세한 내용은 [VSPerfReport](../profiling/vsperfreport.md)를 참조하십시오.  
  
## 보고서 명령  
 다음 명령 중 하나를 사용하여 지정한 프로파일링 데이터 파일에 대한 보고서를 만들 수 있습니다.  
  
 **VSPerfReport** `VSPFile` **\/Summary:All**  
 .vsp 또는 .vsps 파일에 사용할 수 있는 모든 보고서를 생성합니다.  
  
 **VSPerfReport** `VSPFile` **\/Summary:**`ReportType`\[,`ReportType`...\]  
 지정한 형식의 보고서를 생성합니다.  
  
 **VSPerfReport** `VSPFile` **\/CallTrace**  
 각 데이터 수집 이벤트를 나열하는 보고서를 생성합니다.  계측에만 해당됩니다.  
  
## 요약 보고서 형식 매개 변수  
 다음 표에서는 지정된 보고서 형식 옵션으로 생성되는 보고서에 대해 설명합니다.  보고서의 열은 데이터를 수집하는 데 사용된 프로파일링 방법에 따라 달라집니다.  
  
|요약 매개 변수|보고서 설명|보고서 참조|  
|--------------|------------|------------|  
|**CallerCallee**|함수 간의 부모\/자식 관계를 나타냅니다.|-   [샘플링 데이터](../profiling/caller-callee-view-sampling-data.md)<br />-   [계측 데이터](../profiling/caller-callee-view-instrumentation-data.md)<br />-   [.NET 메모리 샘플링 데이터](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)<br />-   [.NET 메모리 계측 데이터](../profiling/caller-callee-view-net-memory-instrumentation-data.md)<br />-   [경합 데이터](../profiling/caller-callee-view-contention-data.md)|  
|**Function**|프로파일링 데이터가 함수별로 표시됩니다.|-   [샘플링 데이터](../profiling/functions-view-sampling-data.md)<br />-   [계측 데이터](../profiling/functions-view-instrumentation-data.md)<br />-   [.NET 메모리 샘플링 데이터](../profiling/functions-view-dotnet-memory-sampling-data.md)<br />-   [.NET 메모리 계측 데이터](../profiling/functions-view-dotnet-memory-instrumentation-data.md)<br />-   [경합 데이터](../profiling/functions-view-contention-data.md)|  
|**CallTree**|프로파일링 실행 시 함수의 실행 경로와 프로파일링 데이터를 나타냅니다.|-   [계측 데이터](../profiling/call-tree-view-instrumentation-data.md)<br />-   [샘플링 데이터](../profiling/call-tree-view-sampling-data.md)<br />-   [.NET 메모리 샘플링 데이터](../profiling/call-tree-view-dotnet-memory-sampling-data.md)<br />-   [.NET 메모리 계측 데이터](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)<br />-   [경합 데이터](../profiling/call-tree-view-contention-data.md)|  
|**Counter**|프로파일링 실행 중 수집된 Windows 성능 카운터 값과 프로파일링 표시를 나열합니다.|-   [표시 뷰](../profiling/marks-view.md)|  
|**Ip**|프로파일링 데이터를 명령별로 나열합니다.|-   [샘플링 데이터](../profiling/instruction-pointers-ips-view-sampling-data.md)<br />-   [.NET 메모리 샘플링 데이터](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)<br />-   [경합 데이터](../profiling/instruction-pointers-ips-view-contention-data.md)|  
|**Life**|할당된 개체의 수명을 나열합니다.|-   [개체 수명 뷰](../profiling/object-lifetime-view.md)|  
|**Line**|프로파일링 데이터를 소스 코드 줄별로 나열합니다.|-   [샘플링 데이터](../profiling/lines-view-sampling-data.md)<br />-   [.NET 메모리 샘플링 데이터](../profiling/lines-view-dotnet-memory-sampling-data.md)<br />-   [경합 데이터](../profiling/lines-view-contention-data.md)|  
|**Header**|프로파일링 데이터 파일 헤더 정보를 표시합니다.|파일에만 해당됩니다.|  
|**Mark**|프로파일링 실행 시 수집된 프로파일링 표시를 나열합니다.|-   [표시 뷰](../profiling/marks-view.md)|  
|**Module**|모듈의 프로파일링 데이터를 나열합니다.|-   [샘플링 데이터](../profiling/modules-view-sampling-data.md)<br />-   [계측 데이터](../profiling/modules-view-instrumentation-data.md)<br />-   [.NET 메모리 샘플링 데이터](../profiling/modules-view-dotnet-memory-sampling-data.md)<br />-   [.NET 메모리 계측 데이터](../profiling/modules-view-dotnet-memory-instrumentation-data.md)<br />-   [경합 데이터](../profiling/modules-view-contention-data.md)|  
|**Process**|프로세스의 프로파일링 데이터를 나열합니다.|-   [프로세스 뷰](../profiling/process-view.md)<br />-   [경합 데이터](../profiling/process-view-contention-data.md)|  
|**Thread**|스레드의 프로파일링 데이터를 나열합니다.|-   [프로세스 뷰](../profiling/process-view.md)|  
|**Type**|할당 프로파일링 데이터를 형식별로 나열합니다.|-   [할당 뷰](../profiling/dotnet-memory-allocations-view.md)|  
|**Contention**|리소스 경합을 표시합니다.|-   [리소스 경합](../profiling/resource-contentions-view-contention-data.md)|  
|**RuleWarnings**|성능 규칙 문제를 나열합니다.|-   규칙 문제의 CheckId, 설명 및 소스 코드 위치를 나열합니다.|  
|**ETW**|프로파일링 실행 시 수집된 모든 ETW\(Windows용 이벤트 추적\) 이벤트를 나열합니다.|-   [ETW 보고서](../profiling/event-tracing-for-windows-etw-report.md)|