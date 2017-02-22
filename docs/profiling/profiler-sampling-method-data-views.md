---
title: "프로파일러 샘플링 방법 데이터 뷰 | Microsoft Docs"
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
  - "프로파일링 도구, 샘플링 데이터 뷰"
  - "샘플링 데이터 뷰"
ms.assetid: 798de693-e43a-4056-aff5-48310c2172c5
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 프로파일러 샘플링 방법 데이터 뷰
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 단원에는 샘플링 방법으로 생성된 프로파일러 데이터 파일의 뷰 및 보고서에 대한 참조 정보가 포함되어 있습니다.  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능으로 Visual Studio 프로파일러가 해당 플랫폼에서 데이터를 수집하는 방식에 중요한 변경 사항이 발생합니다.  Windows 스토어 응용 프로그램에는 또한 새 컬렉션 기술이 필요합니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  
  
## 단원 내용  
 [요약 뷰](../profiling/summary-view-sampling-data.md)  
 샘플이 수집될 때 가장 빈번하게 실행되고 있던 함수와 가장 많은 개별 작업을 수행하고 있던 함수가 표시됩니다.  
  
 [호출 트리 뷰](../profiling/call-tree-view-sampling-data.md)  
 함수의 실행 경로가 계층적 트리로 표시됩니다.  
  
 [모듈 뷰](../profiling/modules-view-sampling-data.md)  
 프로파일링 데이터가 모듈별로 구성되고 샘플이 수집될 때 실행 중이었던 함수, 소스 코드 줄 및 명령이 표시됩니다.  
  
 [호출자 \/ 호출 수신자 뷰](../profiling/caller-callee-view-sampling-data.md)  
 선택한 함수와 해당 함수를 호출하거나 해당 함수에 의해 호출된 함수에 대한 프로파일링 데이터가 표시됩니다.  
  
 [함수 뷰](../profiling/functions-view-sampling-data.md)  
 프로파일링이 함수별로 구성되고 샘플이 수집될 때 실행 중이었던 함수가 표시됩니다.  
  
 [줄 뷰](../profiling/lines-view-sampling-data.md)  
 샘플이 수집될 때 실행 중이었던 소스 코드 줄이 표시됩니다.  
  
 [IP\(명령 포인터\) 뷰](../profiling/instruction-pointers-ips-view-sampling-data.md)  
 샘플이 수집될 때 실행 중이었던 소스 코드 줄이 표시됩니다.  
  
## 참조  
 [프로세스 뷰](../profiling/process-view.md)  
 프로세스 및 스레드의 시작 및 종료 시간이 표시됩니다.  
  
 [표시 뷰](../profiling/marks-view.md)  
 프로파일링 데이터 파일에 삽입된 ETW 목록 및 샘플링이벤트가 표시됩니다.  
  
 [함수 정보 뷰](../profiling/function-details-view.md)  
 선택한 함수와 해당 함수를 호출하거나 해당 함수에 의해 호출된 함수 간의 관계가 그래픽 차트로 표시됩니다.  
  
## 관련 단원  
 [계측 방법 데이터 뷰](../profiling/instrumentation-method-data-views.md)  
 계측 방법으로 생성된 프로파일러 데이터 파일의 뷰 및 보고서에 대한 참조 정보입니다.  
  
 [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md)  
 .NET 메모리 데이터를 포함하는 프로파일러 데이터 파일의 뷰 및 보고서에 대한 참조 정보입니다.  
  
## 참고 항목  
 [샘플링 데이터 값 이해](../profiling/understanding-sampling-data-values.md)