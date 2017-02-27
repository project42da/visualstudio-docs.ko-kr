---
title: "DA0026: 과도한 커널 CPU 처리 시간 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.rules.DA0026"
  - "vs.performance.DA0026"
  - "vs.performance.26"
ms.assetid: 4cfc8a29-b29b-4a72-b386-03d8856fdf8a
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# <a name="da0026-excessive-kernel-cpu-time-processing"></a>DA0026: 과도한 커널 CPU 처리 시간
|||  
|-|-|  
|규칙 ID|TODO|  
|범주|프로파일링 도구 사용|  
|프로파일링 방법|샘플링|  
|메시지|커널 모드 CPU 시간이 비교적 긴 것으로 측정되었습니다. SysCall 샘플링을 사용하면서 원인을 조사해 보세요.|  
|규칙 유형|정보|  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링할 경우 이 규칙을 트리거하려면 10개 이상의 샘플을 수집해야 합니다.  
  
## <a name="cause"></a>원인  
 커널 모드에서 실행된 CPU 시간이 사용자 모드에서 걸린 시간을 초과했습니다. 다시 프로파일링하고 시스템 호출(syscall) 수를 샘플링하여 높은 커널 모드 실행 시간의 원인을 확인해 보세요.  
  
## <a name="rule-description"></a>규칙 설명  
 커널 모드 실행에서 응용 프로그램이 사용한 시간이 비교적 길면 추가 조사가 수행될 수 있습니다. 사용자 모드 응용 프로그램이 커널 모드로 전환되어 I/O 작업을 수행하거나, 스레드 또는 프로세스 동기화 기본 형식을 기다리거나, 시스템 호출을 수행합니다. 응용 프로그램이 수행하는 시스템 호출 종류 및 시스템 호출을 기반으로 샘플 호출 스택을 수집하는 옵션을 선택할 경우 이 시스템 호출을 처리하는 함수 종류를 조사할 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 응용 프로그램이 수행하는 시스템 호출 종류를 조사하려면 프로필을 다시 실행하고 시스템 호출을 기반으로 샘플을 수집하는 옵션을 선택합니다. 자세한 내용은 IDE 내부에서 프로파일링 도구를 실행 중인 경우 [방법: 샘플링 이벤트 선택](../profiling/how-to-choose-sampling-events.md)을 참조하세요. 명령줄에서 프로파일링 도구를 실행할 경우 프로파일링 도구 명령줄 도구 참조에서 [VSPerfCmd](../profiling/vsperfcmd.md) 항목의 **샘플링 간격 옵션** 섹션을 참조하세요.


<!--HONumber=Feb17_HO4-->


