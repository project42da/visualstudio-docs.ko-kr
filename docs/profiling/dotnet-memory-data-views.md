---
title: "프로파일링 도구의 .NET 메모리 데이터 뷰 | Microsoft Docs"
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
  - ".NET 메모리 프로파일링 방법 뷰"
  - "프로파일링 도구, .NET 메모리 프로파일링 뷰"
ms.assetid: 79184d8e-769b-4ace-be2b-521147772081
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 프로파일링 도구의 .NET 메모리 데이터 뷰
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 단원에는 .NET 메모리 프로파일링 데이터가 들어 있는 프로파일러 데이터 파일의 뷰 및 보고서에 대한 참조 정보가 포함되어 있습니다.  
  
## 단원 내용  
 [요약 뷰](../profiling/summary-view-dotnet-memory-data.md)  
 대부분의 메모리를 할당한 함수 및 형식이 표시됩니다.  
  
 [할당 뷰](../profiling/dotnet-memory-allocations-view.md)  
 프로파일링 실행 시 할당된 형식과 해당 형식 할당을 초래한 호출 트리\(실행 경로\)가 표시됩니다.  
  
 [개체 수명 뷰](../profiling/object-lifetime-view.md)  
 프로파일링 실행 시 할당된 형식과 해당 형식의 인스턴스 수, 크기\(바이트\) 및 가비지 수집 세대가 표시됩니다.  
  
 [호출 트리 뷰 \- 샘플링](../profiling/call-tree-view-dotnet-memory-sampling-data.md)  
 프로파일링 실행 시 함수의 실행 경로와 메모리 할당 데이터를 나타내는 계층적 트리가 표시됩니다.  
  
 [모듈 뷰 \- 샘플링](../profiling/modules-view-dotnet-memory-sampling-data.md)  
 .NET 메모리 할당 데이터가 모듈별로 구성되고 메모리가 할당될 때 실행 중이었던 함수, 소스 코드 줄 및 명령이 표시됩니다.  
  
 [호출자 \/ 호출 수신자 뷰 \- 샘플링](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)  
 선택한 함수, 선택한 함수를 호출한 함수 및 선택한 함수가 호출한 함수에 대한 메모리 할당 데이터가 표시됩니다.  
  
 [함수 뷰 \- 샘플링](../profiling/functions-view-dotnet-memory-sampling-data.md)  
 프로파일링 실행 시 함수에 대한 메모리 할당 데이터가 표시됩니다.  
  
 [줄 뷰 \- 샘플링](../profiling/lines-view-dotnet-memory-sampling-data.md)  
 프로파일링 실행 시 함수의 소스 코드 줄에 대한 메모리 할당 데이터가 표시됩니다.  
  
 [IP\(명령 포인터\) 뷰 \- 샘플링](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)  
 프로파일링 실행 시 함수의 명령에 대한 메모리 할당 데이터가 표시됩니다.  
  
 [호출 트리 뷰 \- 계측](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)  
 프로파일링 실행 시 계측된 함수에 대한 실행 경로, 메모리 할당 데이터 및 자세한 타이밍 데이터를 나타내는 계층적 트리가 표시됩니다.  
  
 [모듈 뷰 \- 계측](../profiling/modules-view-dotnet-memory-instrumentation-data.md)  
 프로파일링 데이터가 모듈별로 구성되고 모듈의 함수, 메모리 할당 데이터 및 자세한 타이밍 정보가 표시됩니다.  
  
 [호출자 \/ 호출 수신자 뷰 \- 계측](../profiling/caller-callee-view-net-memory-instrumentation-data.md)  
 선택한 계측 함수, 선택한 함수를 호출한 함수 및 선택한 함수가 호출한 함수에 대한 메모리 할당 데이터와 자세한 타이밍 정보가 표시됩니다.  
  
 [함수 뷰 \- 계측](../profiling/functions-view-dotnet-memory-instrumentation-data.md)  
 프로파일링 실행 시 계측된 함수에 대한 메모리 할당 데이터가 표시됩니다.  
  
## 참조  
 [함수 정보 뷰](../profiling/function-details-view.md)  
 선택한 함수와 해당 함수를 호출하거나 해당 함수에 의해 호출된 함수 간의 관계가 그래픽 차트로 표시됩니다.  
  
 [프로세스 뷰](../profiling/process-view.md)  
 프로세스 및 스레드의 시작 및 종료 시간이 표시됩니다.  
  
 [표시 뷰](../profiling/marks-view.md)  
 프로파일링 데이터 파일에 삽입된 ETW 목록 및 샘플링이벤트가 표시됩니다.  
  
## 관련 단원  
 [샘플링 방법 데이터 뷰](../profiling/profiler-sampling-method-data-views.md)  
 샘플링 방법으로 생성된 프로파일러 데이터 파일의 뷰 및 보고서에 대한 참조 정보입니다.  
  
 [계측 방법 데이터 뷰](../profiling/instrumentation-method-data-views.md)  
 계측 방법으로 생성된 프로파일러 데이터 파일의 뷰 및 보고서에 대한 참조 정보입니다.