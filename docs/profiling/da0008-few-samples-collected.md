---
title: "DA0008: 수집되는 샘플 수가 적습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.rules.DATooFewSamples"
  - "vs.performance.8"
  - "vs.performance.DA0008"
  - "vs.performance.rules.DA0008"
ms.assetid: 8a5b78aa-7b3d-476c-a47d-abfaff3fae7c
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# DA0008: 수집되는 샘플 수가 적습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0008|  
|범주|프로파일링 도구 사용|  
|프로파일링 방법|샘플링|  
|메시지|몇 개의 샘플만 수집되었습니다.  보다 의미 있는 결과를 얻으려면 실행 시간을 늘리거나 샘플링 주기를 더 빠르게 하는 것이 좋습니다.|  
|규칙 유형|정보|  
  
## 원인  
 프로파일링 실행 중 적은 수의 샘플만 수집되었습니다.  
  
## 규칙 설명  
 샘플링 방법을 사용할 경우 데이터가 실제 프로그램 동작을 올바르게 나타낼 수 있도록 하려면 통계적으로 의미 있는 개수의 샘플을 수집해야 합니다.  샘플링 오류를 최소화하려면 1000개 이상의 프로그램 명령 실행 동작 샘플을 수집해야 합니다.  충분한 샘플을 수집하지 못하면 프로파일링 데이터를 분석할 때 잘못된 결과가 생성될 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 통계적으로 의미 있는 결과를 얻을 수 있도록 보다 긴 응용 프로그램 실행을 프로파일링하거나 샘플링 주기를 더 빠르게 하는 것이 좋습니다.  Visual Studio IDE에서 샘플링 주기를 변경하는 방법에 대한 자세한 내용은 [방법: 샘플링 이벤트 선택](../Topic/How%20to:%20Choose%20Sampling%20Events.md)을 참조하십시오.  프로파일링 도구 명령줄을 사용할 때 샘플링 주기를 변경하는 방법에 대한 자세한 내용은 [VSPerfCmd](../profiling/vsperfcmd.md) 참고 자료의 [Timer](../profiling/timer.md)를 참조하십시오.