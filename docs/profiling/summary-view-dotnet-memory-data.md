---
title: "요약 뷰 - 프로파일러 .NET 메모리 데이터 | Microsoft Docs"
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
  - "요약 뷰"
ms.assetid: 0cb317c3-0ae6-4531-aaa8-447576eec037
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 요약 뷰 - 프로파일러 .NET 메모리 데이터
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

요약 뷰에는 가장 많은 메모리가 할당된 .NET 함수 및 형식과 프로파일링 실행 시 가장 여러 번 만들어진 형식에 대한 정보가 표시됩니다.  알림 링크 및 보고서 목록에 대한 설명을 비롯한 자세한 내용은 [요약 뷰](../profiling/summary-view.md)를 참조하십시오.  
  
## 시간 표시 그래프  
 요약 뷰의 시간 표시 그래프에서는 프로파일링이 발생한 시간 동안 프로파일링된 응용 프로그램에서의 프로세서\(CPU\) 사용률을 보여 줍니다.  시간 표시 그래프를 사용하여 선택한 시간 범위로 뷰를 필터링할 수 있습니다.  자세한 내용은 [방법: 요약 시간 표시 막대에서 보고서 뷰 필터링](../Topic/How%20to:%20Filter%20Report%20Views%20from%20the%20Summary%20Timeline.md)을 참조하십시오.  
  
## 대부분의 메모리를 할당하는 함수  
 프로파일링 실행 시 가장 많은 메모리\(바이트 수\)를 할당한 함수를 나열합니다.  
  
|열|설명|  
|-------|--------|  
|**Name**|함수의 이름.|  
|**바이트 비율\(%\)**|프로파일링 실행 시 전체 할당된 바이트 중 해당 함수나 해당 함수에 의해 호출된 자식 함수에서 할당된 바이트의 백분율입니다.|  
  
## 대부분의 메모리가 할당된 형식  
 프로파일링 실행 시 가장 많은 메모리\(바이트 수\)가 할당된 형식을 나열합니다.  
  
|열|설명|  
|-------|--------|  
|**Name**|형식의 이름입니다.|  
|**바이트 비율\(%\)**|프로파일링 실행 시 전체 할당된 바이트 중 해당 형식에 대해 할당된 바이트의 백분율입니다.|  
  
## 대부분의 인스턴스가 있는 형식  
 대개 프로파일링 실행 중에 만들어진 형식을 나열합니다.  
  
|열|설명|  
|-------|--------|  
|**Name**|형식의 이름입니다.|  
|**인스턴스 비율\(%\)**|프로파일링 실행 시 만들어진 총 .NET 개체 수 중 해당 형식의 인스턴스인 개체의 백분율입니다.|  
  
## 참고 항목  
 [요약 뷰](../profiling/summary-view-sampling-data.md)   
 [요약 뷰](../profiling/summary-view-instrumentation-data.md)