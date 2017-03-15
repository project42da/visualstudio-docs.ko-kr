---
title: "프로파일링 도구에서 리소스 경합 데이터 값 이해 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "동시성 프로파일링 방법"
  - "프로파일링 도구, 동시성 방법"
ms.assetid: 071c0f0f-1eba-4dc8-ae87-0810e4086dd0
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 프로파일링 도구에서 리소스 경합 데이터 값 이해
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

리소스 컨텐션 프로파일링에서는 응용 프로그램에서 경쟁하는 스레드가 공유 리소스에 액세스할 수 있을 때까지 대기하게 될 때마다 자세한 호출 스택 정보를 수집합니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 리소스 경합 보고서에는 총 경합 수와 대기가 발생한 모듈, 함수, 소스 코드 줄 및 명령에서 리소스를 기다린 총 시간이 표시됩니다.  
  
-   포괄 값은 리소스 경합에 의해 함수가 대기해야 했던 총 경합 수와 해당 함수가 기다린 총 시간을 표시합니다.  해당 함수가 호출한 자식 함수에 의해 발생한 경합도 포괄 값에 포함됩니다.  
  
-   전용 값은 함수가 대기해야 했던 경합 중 해당 함수 본문의 코드에 의해 발생한 경합 수만 표시합니다.  자식 함수에 의해 발생한 경합은 포함되지 않습니다.  또한 함수의 전용 시간에는 해당 함수 본문의 문에 의해 발생한 대기 시간만 포함됩니다.  
  
 리소스 경합 보고서 뷰에는 개별 경합 이벤트를 시간에 따라 보여 주고 특정 이벤트를 생성한 호출 스택을 보여 주는 시간 표시 그래프도 포함됩니다.  자세한 내용은 다음 항목 중 하나를 참조하십시오.  
  
-   [스레드 정보 뷰](../profiling/thread-details-view-contention-data.md)  
  
-   [리소스 정보 뷰](../profiling/resource-details-view-contention-data.md)  
  
 동시성 프로파일링의 두 번째 모드에 대한 자세한 내용은 [동시성 시각화 도우미](../profiling/concurrency-visualizer.md)를 참조하십시오.