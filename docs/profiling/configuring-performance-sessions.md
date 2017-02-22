---
title: "프로파일링 도구의 성능 세션 구성 | Microsoft Docs"
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
  - "일반 작업, 성능"
  - "일반 작업, 프로파일링 도구"
  - "프로파일링 도구, 일반 작업"
  - "성능, 데이터 수집"
ms.assetid: e1c3ba41-ffca-4edf-9a7f-8a5a9244ef9b
caps.latest.revision: 36
caps.handback.revision: 36
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 프로파일링 도구의 성능 세션 구성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구를 사용하면 많은 유형의 응용 프로그램에 대한 다양한 성능 데이터를 수집할 수 있습니다.  이 단원에서는 **성능 마법사**와 성능 세션 및 대상 이진 파일의 속성을 사용하여 프로파일링 도구에서 관심 있는 데이터를 수집하도록 구성하는 방법을 보여 줍니다.  프로파일링 도구 구성 속성을 사용하여 프로파일링 실행 시 수집되는 데이터의 양을 제어할 수도 있습니다.  자세한 내용은 [데이터 수집 제어](../profiling/controlling-data-collection.md)을 참조하십시오.  
  
> [!NOTE]
>  대부분의 경우 성능 마법사의 기본 속성을 사용하면 프로파일링 데이터를 효과적으로 수집할 수 있습니다.  자세한 내용은 [초보자를 위한 성능 프로파일링 지침](../profiling/beginners-guide-to-performance-profiling.md) 및 [시작](../profiling/getting-started-with-performance-tools.md)를 참조하십시오.  
  
## 일반 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**기본 프로파일링 옵션 설정:** Microsoft 기호 서버를 사용하도록 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]를 구성해야 합니다.  이렇게 하면 최신 버전의 Windows와 다른 Microsoft 응용 프로그램에 대한 함수 및 매개 변수 이름 등의 기호에 액세스할 수 있습니다.  프로파일링 세션이 시작되기 전에 프로파일링 도구에 대한 시스템 권한과 프로파일링 데이터 파일의 이름 등 다른 일반 옵션을 지정할 수도 있습니다.|-   [방법: Windows 기호 정보 참조](../profiling/how-to-reference-windows-symbol-information.md)<br />-   [방법: 기호 정보 직렬화](../profiling/how-to-serialize-symbol-information.md)<br />-   [방법: 현재 프로파일링 세션 설정](../Topic/How%20to:%20Set%20the%20Current%20Session.md)<br />-   [방법: 프로파일링 권한 설정](../profiling/how-to-set-permissions.md)<br />-   [방법: 프로파일링 데이터 파일 이름 옵션 설정](../profiling/how-to-set-performance-data-file-name-options.md)|  
|**수집할 데이터 지정:** 프로파일링 세션을 구성하는 절차는 프로파일링할 대상 응용 프로그램의 유형과 수집하려는 성능 데이터의 형식에 따라 달라집니다.|-   [방법: 수집 방법 선택](../profiling/how-to-choose-collection-methods.md)<br />-   [샘플링을 사용하여 성능 통계 수집](../profiling/collecting-performance-statistics-by-using-sampling.md)<br />-   [.NET 메모리 할당 및 수명 데이터 수집](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)<br />-   [방법: 웹 페이지에서 JavaScript\(ECMA\) 코드 프로파일링](../Topic/How%20to:%20Profile%20JavaScript%20Code%20in%20Web%20Pages.md)<br />-   [스레드 및 프로세스 동시성 데이터 수집](../profiling/collecting-thread-and-process-concurrency-data.md)<br />-   [추가 성능 데이터 수집](../profiling/collecting-additional-performance-data.md)|  
|**고급 구성 옵션 설정:** 여러 버전의 CLR\(공용 언어 런타임\)을 로드하는 .NET Framework 응용 프로그램을 프로파일링하는 경우 프로파일링할 버전을 지정할 수 있습니다.  성능 세션에 여러 .exe 파일이 있는 경우에는 이진 파일의 시작 순서를 설정할 수 있습니다.|-   [방법: 병렬 시나리오에서 프로파일링할 .NET Framework 런타임 지정](../Topic/How%20to:%20Specify%20the%20.NET%20Framework%20Runtime.md)<br />-   [방법: 시작할 이진 파일 지정](../profiling/how-to-specify-the-binary-to-start.md)|  
  
## 관련 단원  
 [데이터 수집 제어](../profiling/controlling-data-collection.md)  
  
## 참고 항목  
 [프로파일링 도구 사용](../profiling/performance-explorer.md)