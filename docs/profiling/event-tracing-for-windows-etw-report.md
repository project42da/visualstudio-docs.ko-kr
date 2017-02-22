---
title: "ETW(Windows용 이벤트 추적) 보고서 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ETW 프로파일링 보고서"
  - "Windows 프로파일링 보고서용 이벤트 추적"
ms.assetid: 81e88162-b88a-40b6-8b85-a232c8096a47
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# ETW(Windows용 이벤트 추적) 보고서
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ETW\(Windows용 이벤트 추적\) 보고서에는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 성능 세션에서 기록된 ETW 이벤트가 나열됩니다.  ETW 데이터는 이진 파일\(.etl\)에 수집됩니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 인터페이스에서는 ETW 보고서를 표시할 수 없습니다.  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 인터페이스에서 프로파일링 도구를 사용하여 ETW를 수집하는 방법에 대한 자세한 내용은 [방법: ETW\(Windows용 이벤트 추적\) 데이터 수집](../Topic/How%20to:%20Collect%20Event%20Tracing%20for%20Windows%20\(ETW\)%20Data.md)을 참조하십시오.  
  
-   [VSPerfCmd](../profiling/vsperfcmd.md) 명령줄 도구를 사용하여 ETW 데이터를 수집하는 방법에 대한 자세한 내용은 [이벤트](../profiling/events-vsperfcmd.md)를 참조하십시오.  
  
-   ETW 보고서는 **VSReport \/Summary:ETW** 명령을 사용하여 생성합니다.  자세한 내용은 [VSPerfReport](../profiling/vsperfreport.md)을 참조하십시오.  
  
|열|설명|  
|-------|--------|  
|**타임스탬프**|이벤트가 발생한 시기를 식별합니다.|  
|**프로세스 ID**|이벤트를 생성한 프로세스를 식별합니다.|  
|**스레드 ID**|이벤트를 생성한 스레드를 식별합니다.|  
|**설명**|이벤트 공급자를 식별합니다.|  
|**형식**|이벤트 형식을 식별합니다.|  
|**속성**|이벤트의 속성입니다.  각 이벤트는 쉼표로 구분되고 대괄호로 묶인 이름\/값 쌍입니다.|