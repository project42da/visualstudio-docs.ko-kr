---
title: "리소스 모니터링 성능 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0f77faf-0a05-4718-a2c5-47934be40868
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# 리소스 모니터링 성능 규칙
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

리소스 모니터링 범주의 성능 메시지는 응용 프로그램 성능에 대한 추가 데이터를 제공합니다.  이 데이터를 사용하여 성능 문제를 분석할 수 있습니다.  이 규칙은 정보를 제공하기 위한 것으로 모든 프로파일링 실행에 대해 보고됩니다.  
  
|||  
|-|-|  
|[DA0501: 프로파일링 중인 프로세스의 평균 CPU 사용](../Topic/DA0501:%20Average%20CPU%20consumption%20by%20the%20Process%20being%20profiled..md)|이 메시지는 프로세서가 응용 프로그램의 명령을 실행하는 데 소요된 시간의 백분율을 보고합니다.  보고되는 값은 프로파일링되는 프로세스가 활성 상태였던 전체 측정 간격의 평균입니다.|  
|[DA0502: 프로파일링 중인 프로세스의 최대 CPU 사용](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|이 메시지는 프로세서가 응용 프로그램의 명령을 실행하는 데 소요된 시간의 최대 백분율을 보고합니다.  보고되는 값은 프로파일링되는 프로세스가 활성 상태였던 전체 측정 간격에서 보고된 최대값입니다.|  
|[DA0503: 프로파일링 중인 프로세스에 대한 평균 작업 집합\(바이트\)](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|이 메시지는 프로파일링이 활성 상태일 때 프로세스에 사용된 실제 메모리의 평균 크기\(바이트\)를 보고합니다.  이 실제 메모리 측정값을 작업 집합이라고 합니다.|  
|[DA0504: 프로파일링 중인 프로세스에 대한 최대 작업 집합\(바이트\)](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|이 메시지는 프로파일링이 활성 상태일 때 프로세스에 사용된 실제 메모리의 최대 크기\(바이트\)를 보고합니다.|  
|[DA0505: 프로파일링 중인 프로세스에 할당되는 평균 전용 바이트](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|이 메시지는 프로파일링이 활성 상태일 때 프로세스에서 바이트로 할당한 가상 메모리의 평균 크기를 보고합니다.  이 가상 메모리 측정값을 *전용 바이트*라고 합니다.  전용 바이트는 프로세스에 의해 할당되어 프로세스 내에서 실행 중인 스레드에 의해서만 액세스될 수 있는 가상 메모리 위치를 나타냅니다.|  
|[DA0506: 프로파일링 중인 프로세스에 할당되는 최대 전용 바이트](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|이 메시지는 프로파일링이 활성 상태일 때 프로세스에서 전용 바이트로 할당한 가상 메모리의 최대 크기를 보고합니다.|