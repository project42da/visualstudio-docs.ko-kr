---
title: "프로파일링 도구에서 데이터 수집 제어 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로파일링 도구 고급 작업"
  - "프로파일링 도구, 고급 작업"
ms.assetid: e713ad63-b948-46f3-8db9-59b30922ebe5
caps.latest.revision: 27
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 27
---
# 프로파일링 도구에서 데이터 수집 제어
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구를 사용하여 성능 세션 도중 프로파일링 데이터가 수집되는 시기를 제어하고 프로파일링되는 함수를 지정할 수 있습니다.  이 단원에서는 **성능 탐색기** 및 **데이터 수집 제어** 창에서 데이터 수집을 시작 및 중지하는 방법과 프로파일링 데이터가 수집되는 개체를 제한하는 방법에 대해 설명합니다.  
  
## 일반 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**프로파일링 시작 및 중지:** 응용 프로그램이 시작될 때 응용 프로그램 프로파일링을 시작하거나, 이미 실행 중인 프로세스에 프로파일러를 연결할 수 있습니다.  대상 응용 프로그램이 실행 중인 경우 데이터 수집을 일시 중지했다가 다시 시작할 수 있습니다.  프로파일링 세션을 종료하려면 대상 응용 프로그램을 닫거나 실행 중인 프로세스에서 프로파일러를 분리합니다.|-   [방법: 프로파일링 시작 및 종료](../profiling/how-to-start-and-end-performance-data-collection.md)<br />-   [방법: 실행 중인 프로세스에 프로파일러 연결 및 분리](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md)<br />-   [방법: 프로파일링 일시 중지 및 다시 시작](../Topic/How%20to:%20Pause%20and%20Resume%20Performance%20Data%20Collection.md)|  
|**수집되는 데이터를 제한하도록 계측 프로파일링 구성:** 성능 세션 구성 속성을 사용하여 계측 방법을 사용하는 프로파일링 실행 시 수집되는 데이터를 제한할 수 있습니다.  특정 .dll 파일, 네임스페이스, 클래스 및 함수를 포함하거나 제외할 수 있습니다.  지정한 크기 임계값을 충족하지 않는 함수를 제외할 수도 있습니다.|-   [방법: 계측을 특정 DLL로 제한](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)<br />-   [방법: 특정 함수로 계측 제한](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [방법: 계측에서 간단한 함수 제외 또는 포함](../Topic/How%20to:%20Exclude%20or%20Include%20Short%20Functions%20from%20Instrumentation.md)|  
  
## 관련 단원  
 [성능 세션 구성](../profiling/configuring-performance-sessions.md)  
  
## 참고 항목  
 [프로파일링 도구 사용](../profiling/performance-explorer.md)