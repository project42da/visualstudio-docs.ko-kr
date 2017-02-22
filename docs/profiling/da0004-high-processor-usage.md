---
title: "DA0004: 프로세서 사용률이 높습니다. | Microsoft Docs"
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
  - "vs.performance.rules.DAHighProcessorUsage"
  - "vs.performance.rules.DA0004"
  - "vs.performance.DA0004"
  - "vs.performance.4"
ms.assetid: 2c4fb569-929e-4f1d-8c50-b590ee371351
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0004: 프로세서 사용률이 높습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0004|  
|범주|프로파일링 도구 사용|  
|프로파일링 방법|계측<br /><br /> 샘플링|  
|메시지|프로세서 사용률이 지속적으로 75% 이상입니다.  CPU 바인딩된 응용 프로그램에 샘플링 모드를 사용해 보십시오.|  
|규칙 유형|정보|  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링하는 경우에는 적어도 10개의 샘플을 수집하여 이 규칙을 트리거해야 합니다.  
  
## 원인  
 계측 방법을 사용하여 수집된 프로파일링 데이터에서 프로세서\(CPU\) 사용률이 상당히 높게 나타났습니다.  CPU 바인딩된 응용 프로그램을 프로파일링할 때는 샘플링 프로파일링 방법을 사용하는 것이 좋습니다.  
  
## 규칙 설명  
 이 프로파일링을 실행하는 동안 프로세서가 계속 사용 중이었습니다.  CPU 사용률이 높으면 CPU 바인딩된 응용 프로그램일 수 있습니다.  계측된 프로필은 일반적으로 CPU 사용 시나리오를 조사하는 가장 효과적인 방법이 아닙니다.  프로세서에서 명령을 실행하는 데 많은 시간을 소요하는 응용 프로그램을 프로파일링하는 경우에는 일반적으로 샘플링이 가장 효율적인 방법입니다.  
  
## 위반 문제를 해결하는 방법  
 함수 타이밍이 필요하거나 프로세서 병목보다 입\/출력을 알고 싶은 경우가 아니면 계측 방법 대신 샘플링 방법을 사용하여 응용 프로그램을 다시 프로파일링하는 것이 좋습니다.