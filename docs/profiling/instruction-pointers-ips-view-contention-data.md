---
title: "IP(명령 포인터) 뷰 - 프로파일러 경합 데이터 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령 포인터 뷰"
ms.assetid: f5e49c24-d4cf-4f87-977d-37e3223d1196
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IP(명령 포인터) 뷰 - 프로파일러 경합 데이터
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

경합 데이터의 IP 뷰에는 프로파일링 실행 시 실행이 차단되었던 어셈블리 명령에 대한 데이터가 나열됩니다.  
  
 다음 표에서는 명령 포인터 뷰에 표시되는 열 값을 설명합니다.  
  
|열|설명|  
|-------|--------|  
|**차단된 전용 시간**|해당 함수에서 차단된 시간입니다.|  
|**차단된 전용 시간 비율\(%\)**|해당 명령이 실행되는 동안 차단된 시간의 백분율입니다.|  
|**전용 경합**|해당 명령이 실행되는 동안 발생한 경합 수입니다.|  
|**전용 경합 비율\(%\)**|프로파일링 실행 시 전체 경합 중 해당 명령이 실행될 때 발생한 경합의 백분율입니다.|  
|**함수 주소**|로드된 이진 파일에서 해당 함수의 시작 메모리 주소입니다.|  
|**함수 이름**|해당 명령이 포함된 함수의 이름입니다.|  
|**명령 주소**|로드된 이진 파일에서 해당 명령의 메모리 주소입니다.|  
|**함수 줄 번호**|소스 파일에서 이 함수가 시작되는 줄 번호입니다.|  
|**모듈 이름**|해당 명령이 포함된 모듈의 이름입니다.|  
|**모듈 경로**|해당 명령이 포함된 모듈의 경로입니다.|  
|**프로세스 ID**|프로파일링되는 프로세스의 PID\(프로세스 ID\)입니다.|  
|**프로세스 이름**|프로세스의 이름입니다.|  
|**소스 문자 시작**|소스 파일 줄에서 해당 명령이 시작되는 문자의 오프셋입니다.|  
|**소스 문자 끝**|소스 파일 줄에서 해당 명령이 끝나는 문자의 오프셋입니다.|  
|**소스 파일**|해당 명령이 포함된 소스 파일입니다.|  
|**소스 줄 시작**|소스 파일에서 해당 명령이 시작되는 줄 번호입니다.|  
|**소스 줄 끝**|소스 파일에서 해당 명령이 끝나는 줄 번호입니다.|  
  
## 참고 항목  
 [방법: 보고서 뷰 열 사용자 지정](../profiling/how-to-customize-report-view-columns.md)   
 [IP\(명령 포인터\) 뷰](../profiling/instruction-pointers-ips-view.md)   
 [IP\(명령 포인터\) 뷰 \- 샘플링](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)   
 [IP\(명령 포인터\) 뷰](../profiling/instruction-pointers-ips-view-sampling-data.md)