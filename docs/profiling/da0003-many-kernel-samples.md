---
title: "DA0003: 커널 샘플이 많습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.rules.DA0003"
  - "vs.performance.DA0003"
  - "vs.performance.3"
  - "vs.performance.rules.DAManyKernelSamples"
ms.assetid: c1f46f77-eb95-42e5-b340-d86bc9de41b4
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0003: 커널 샘플이 많습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0003|  
|범주|프로파일링 도구 사용|  
|프로파일링 방법|샘플링|  
|메시지|커널 모드일 때 샘플 비율이 높습니다.  이것은 I\/O 작업이 많거나 컨텍스트 전환 비율이 높음을 나타낼 수 있습니다.  계측 모드를 사용하여 응용 프로그램을 다시 프로파일링해 보십시오.|  
|규칙 유형|정보|  
  
## 원인  
 응용 프로그램에 대해 수집된 호출 스택 샘플 중 상당 비율이 커널 모드에서 실행되었습니다.  다른 프로파일링 방법으로 응용 프로그램을 프로파일링해 보십시오.  
  
## 규칙 설명  
 Windows에서는 커널 모드나 사용자 모드에서 코드를 실행할 수 있습니다. 커널 모드는 시스템 모드라고도 합니다. 커널 모드에서는 장치 드라이버 같은 낮은 수준의 시스템 코드만 실행됩니다.  I\/O 작업을 수행하거나, 스레드 또는 프로세스 동기화 기본 형식을 기다리거나, 시스템 호출을 수행할 때 사용자 모드 응용 프로그램이 커널 모드로 전환될 수 있습니다.  
  
 사용자 모드에서 작업을 수행하는 데 많은 시간을 소요하는 응용 프로그램을 프로파일링하는 경우에는 샘플링이 가장 효율적인 방법입니다.  응용 프로그램을 커널 모드로 실행할 때 수집된 샘플 수는 자주 발생하는 I\/O 작업을 나타내거나 컨텍스트 전환의 발생을 나타낼 수 있습니다.  이러한 작업은 샘플링 방법을 사용하여 조사할 수 없습니다.  커널 모드 샘플을 너무 많이 가져온 경우, 샘플링 데이터에 충분한 사용자 모드 샘플이 포함되어 있지 않아 통계적으로 큰 차이가 있을 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 다음 옵션 중 하나를 사용하여 응용 프로그램을 다시 프로파일링하는 것이 좋습니다.  
  
-   계측 방법을 사용하여 프로파일링합니다.  
  
-   샘플링 주기를 더 빠르게 하여 사용자 모드에서 더 많은 샘플을 수집해 봅니다.