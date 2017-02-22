---
title: "프로파일링 도구 사용 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 프로파일링 도구 사용 규칙
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로파일링 도구 사용 범주의 성능 규칙은 프로파일러를 사용하여 데이터를 가장 효율적으로 수집하는 작업에 대한 지침을 제공합니다.  
  
|||  
|-|-|  
|[DA0002: VSPerfCorProf.dll이 없습니다.](../profiling/da0002-vsperfcorprof-dll-is-missing.md)|명령줄 프로파일링에는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 이진 파일에 대한 불완전한 데이터가 포함될 수 있습니다.  올바른 환경 변수를 설정하지 않은 경우 이 오류가 발생할 수 있습니다.|  
|[DA0003: 커널 샘플이 많습니다.](../profiling/da0003-many-kernel-samples.md)|대상 이진 파일 실행 외부에서 발생한 많은 프로파일링 샘플이 기록되었습니다.  보다 정확한 데이터를 수집하려면 계측 방법을 사용하십시오.|  
|[DA0004: 프로세서 사용률이 높습니다.](../profiling/da0004-high-processor-usage.md)|프로파일링 데이터에 프로파일링 실행 시 프로세서가 계속 사용 중이었던 것으로 나타납니다.  보다 정확한 데이터를 수집하려면 샘플링 방법을 사용하십시오.|  
|[DA0008: 수집되는 샘플 수가 적습니다.](../profiling/da0008-few-samples-collected.md)|프로파일링 실행 시 수집된 샘플 수가 크지 않아 통계적으로 중요하지 않습니다.  프로파일링을 다시 실행하고 응용 프로그램을 보다 길게 실행하는 것이 좋습니다.  또한 데이터를 수집하기 위해 계측 방법을 사용할 수 있습니다.|  
|[DA0026: 과도한 커널 CPU 처리 시간](../Topic/DA0026:%20Excessive%20kernel%20CPU%20time%20processing.md)|프로세서 커널 모드에서 많은 시간 동안 프로파일링이 실행되었습니다.  시간을 메트릭으로 사용하는 대신 시스템 호출을 메트릭으로 사용하는 것이 좋습니다.|  
|[DA0029: 지원되지 않는 CLR 버전](../profiling/da0029-unsupported-clr-version.md)|프로파일링된 이진 파일이 프로파일러에서 지원하지 않는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전을 사용 중입니다.  프로파일러 보고서가 기호 이름을 확인할 수 없습니다.|  
|[DA0030: 데이터베이스 프로젝트에 대한 계층 상호 작용 측정값 수집](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md)|<xref:System.Data?displayProperty=fullName> 네임스페이스에서 메서드에 대한 상당한 횟수의 호출이 수집되었습니다.  데이터베이스 호출에 대한 데이터를 포함하려면 프로파일 실행 시 계층 상호 작용 데이터를 수집하십시오.|