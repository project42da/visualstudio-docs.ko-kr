---
title: "방법: 계측 방법을 사용하여 CPU 카운터 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.property.cpucounters"
helpviewer_keywords: 
  - "프로파일링 도구, 포팅 가능한 CPU 카운터 사용"
  - "성능 도구, 포팅 가능한 CPU 카운터"
ms.assetid: 102fb6ca-5fbf-4b05-925f-56912ce3f44b
caps.latest.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 21
---
# 방법: 계측 방법을 사용하여 CPU 카운터 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

CPU 이벤트 카운터는 하드웨어 관련 성능 데이터를 수집하는 데 사용됩니다.  이 항목에서는 계측 프로 파일링 방법을 사용하는 경우 이벤트 카운터 데이터를 수집하는 방법을 보여줍니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 CPU 카운터 이벤트에는 다음 두 가지 종류가 있습니다.  
  
-   이식 가능한 이벤트 – 특정 CPU에 관계없이 수집할 수 있는 CPU 이벤트  
  
-   플랫폼 이벤트 \- 특정 CPU와 결합된 CPU 이벤트  
  
 이식 가능한 이벤트에는 Instructions Retired 및 Non Halted Cycles 같은 일반 이벤트, CPU 버퍼 이벤트, 분기 이벤트 및 L2 캐시 이벤트가 포함됩니다.  사용 가능한 플랫폼 이벤트 카운터는 프로세서 제조업체에서 결정합니다.  
  
 이벤트 범주는 이식 가능한 카운터와 플랫폼 카운터 간에 공유할 수 있습니다.  예를 들어 두 형식 모두에서 공통적으로 자주 나타나는 데이터 범주는 다음과 같습니다.  
  
-   메모리 이벤트  
  
-   프런트 엔드 이벤트  
  
-   분기 이벤트  
  
 성능 카운터 데이터는 프로파일러에서 다음과 같은 두 가지 방식으로 수집할 수 있습니다.  
  
-   계측을 통해 프로파일링할 경우 하나 이상의 카운터에서 데이터를 수집합니다.  
  
-   샘플링을 통해 프로파일링할 경우 카운터 이벤트를 샘플링 간격으로 지정합니다.  자세한 내용은 [방법: 샘플링 이벤트 선택](../Topic/How%20to:%20Choose%20Sampling%20Events.md)을 참조하십시오.  
  
### 계측을 통해 프로파일링할 경우 CPU 성능 카운터 데이터를 수집하려면  
  
1.  성능 세션 **속성 페이지**에서 **CPU 카운터**를 클릭합니다.  
  
2.  **CPU 카운터 수집** 확인란을 선택합니다.  
  
3.  수집할 샘플 이벤트를 찾을 때까지 **사용 가능한 성능 카운터** 트리를 확장합니다.  
  
4.  수집할 이벤트마다 이벤트를 선택하고 오른쪽 화살표를 클릭하여 해당 이벤트를 **선택한 카운터** 목록에 추가합니다.  
  
    > [!NOTE]
    >  **사용 가능한 성능 카운터**는 **CPU 카운터 수집** 확인란을 선택한 경우에만 활성화됩니다.  
  
## 참고 항목  
 [성능 세션 구성](../profiling/configuring-performance-sessions.md)   
 [성능 세션 속성](../profiling/performance-session-properties.md)   
 [CPU 및 Windows 카운터](../profiling/cpu-and-windows-counters.md)   
 [방법: 샘플링 이벤트 선택](../Topic/How%20to:%20Choose%20Sampling%20Events.md)