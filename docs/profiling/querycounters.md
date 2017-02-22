---
title: "QueryCounters | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8059d4b2-af61-4a47-a6c2-8da5c0741c74
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# QueryCounters
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**QueryCounters** 옵션은 컴퓨터에서 사용할 수 있는 CPU\(하드웨어\) 성능 카운터를 나열합니다.  
  
 **QueryCounters**는 명령줄에서 단독 옵션으로 사용해야 합니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /QueryCounters  
```  
  
#### 매개 변수  
 없음  
  
## 설명  
 계측 방법을 사용하는 경우 프로파일러에서는 데이터 수집 이벤트가 발생할 때마다 하나 이상의 CPU 성능 카운터에 대한 값을 수집할 수 있습니다.  샘플링 프로파일링 방법을 사용하는 경우에는 하나의 카운터 이벤트와 샘플링 간격으로 사용할 이벤트 발생 횟수를 지정할 수 있습니다.  
  
 프로세서에 따라 각기 다른 CPU 성능 카운터를 노출합니다.  프로파일러는 거의 모든 프로세서에서 사용할 수 있는 일반 카운터 집합을 정의합니다.  **QueryCounters** 옵션은 일반 카운터의 이름과 프로세서별 카운터의 이름을 모두 나열합니다.  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)