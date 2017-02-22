---
title: "함수 뷰 - 프로파일러 .NET 메모리 샘플링 데이터 | Microsoft Docs"
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
  - "함수 뷰"
ms.assetid: 5d9c6302-2ffd-430e-9535-13ce795f9f7c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 함수 뷰 - 프로파일러 .NET 메모리 샘플링 데이터
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

샘플링 방법을 사용하여 수집된 .NET 메모리 할당 프로파일링 데이터에 대한 함수 뷰에는 프로파일링 실행 중 메모리를 할당한 함수의 목록이 표시되고 해당 할당의 크기 및 개수가 보고됩니다.  
  
|열|설명|  
|-------|--------|  
|**프로세스 ID**|프로파일링 실행의 PID\(프로세스 ID\)입니다.|  
|**프로세스 이름**|프로세스의 이름입니다.|  
|**모듈 이름**|함수가 포함된 모듈의 이름입니다.|  
|**모듈 경로**|함수가 포함된 모듈의 경로입니다.|  
|**소스 파일**|이 함수의 정의가 포함된 소스 파일입니다.|  
|**함수 이름**|함수의 정규화된 이름입니다.|  
|**함수 줄 번호**|소스 파일에서 이 함수가 시작되는 줄 번호입니다.|  
|**함수 주소**|함수의 주소입니다.|  
|**포괄 할당**|이 함수와 해당 자식 함수에서 할당된 총 개체 수입니다.|  
|**포함 할당 비율\(%\)**|프로파일링 실행 시 할당된 전체 개체 중 해당 함수의 포괄 할당이었던 개체의 백분율입니다.|  
|**제외 할당**|호출 스택의 맨 위에서 함수가 직접 실행 중일 때 만들어진 개체 수입니다.  이 개수는 자식 함수에서 만들어진 개체를 포함하지 않습니다.|  
|**제외 할당 비율\(%\)**|프로파일링 실행 시 할당된 전체 개체 중 해당 함수의 제외 할당이었던 개체의 백분율입니다.|  
|**포함 바이트**|이 함수와 해당 자식 함수가 할당한 메모리 바이트 수입니다.|  
|**포함 바이트 비율\(%\)**|프로파일링 실행 시 할당된 전체 메모리 바이트 중 해당 함수의 포괄 바이트였던 메모리 바이트의 백분율입니다.|  
|**제외 바이트**|이 함수가 할당한 메모리 바이트 수로, 해당 자식 함수가 할당한 메모리 바이트 수는 제외됩니다.|  
|**제외 바이트 비율\(%\)**|프로파일링 실행 시 할당된 전체 메모리 바이트 중 이 함수의 제외 바이트였던 개체의 백분율입니다.|  
  
## 참고 항목  
 [함수 뷰 \- 계측](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [함수 뷰](../profiling/functions-view-sampling-data.md)   
 [함수 뷰](../profiling/functions-view-instrumentation-data.md)