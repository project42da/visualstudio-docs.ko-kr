---
title: "DA0502: 프로파일링 중인 프로세스의 최대 CPU 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.rules.DA0502"
  - "vs.performance.DA0502"
  - "vs.performance.502"
ms.assetid: 1ee53df5-b0dc-4265-9d4f-527830d08725
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# DA0502: 프로파일링 중인 프로세스의 최대 CPU 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0502|  
|범주|리소스 모니터링|  
|프로파일링 방법|모두|  
|메시지|이 규칙은 참고용으로만 제공됩니다.  Process\(\)\\% Processor Time 카운터는 프로파일링하고 있는 프로세스의 CPU 사용을 측정합니다.  보고된 값은 모든 측정 간격에 걸쳐 관측된 최대값입니다.|  
|규칙 유형|정보|  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링하는 경우에는 적어도 10개의 샘플을 수집하여 이 규칙을 트리거해야 합니다.  
  
## 규칙 설명  
 이 메시지는 프로세서가 응용 프로그램의 명령을 실행하는 데 소요된 시간의 최대 백분율을 보고합니다.  보고되는 값은 프로파일링되는 프로세스가 활성 상태였던 전체 측정 간격에서 보고된 최대값입니다.  프로세서가 둘 이상인 컴퓨터에서는 이 백분율이 100%보다 클 수 있습니다.  
  
## 규칙 데이터 사용 방법  
 이 규칙 값을 사용하여 프로그램의 여러 버전 또는 빌드 간에 성능을 비교하거나, 여러 프로파일링 시나리오에서의 응용 프로그램 성능을 확인할 수 있습니다.