---
title: "일반 성능 세션 옵션 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.property.general"
ms.assetid: 6b60bd1b-2198-4261-b84e-9b2d8494a992
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 일반 성능 세션 옵션 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

성능 세션에 대한 속성 대화 상자의 **일반** 페이지에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구 성능 세션에 대한 수집 방법과 프로파일링 데이터 명명 규칙을 설정할 수 있습니다.  **성능 탐색기**에서 이 대화 상자를 열려면 성능 세션을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
## 데이터 수집 방법 선택  
 **프로파일링 수집** 아래의 옵션 중 하나를 선택하여 기본 수집 방법을 설정할 수 있습니다.  다음 표에서는 이러한 옵션에 대해 설명합니다.  
  
|||  
|-|-|  
|**샘플링**:  샘플링 방법은 정기적인 간격으로 프로파일링 정보를 수집하는 방법입니다.  이 방법은 프로세서 사용률 문제를 찾는 데 유용하며 대부분의 성능 확인을 시작하는 데 권장되는 방법입니다.|-   [샘플링을 사용하여 성능 통계 수집](../profiling/collecting-performance-statistics-by-using-sampling.md)|  
|**계측**:  계측 방법은 프로파일링 실행 중 모듈에 포함된 함수의 각 시작, 종료 및 함수 호출을 기록하는 프로파일링 코드를 모듈 복사본에 삽입하는 방법입니다.  이 방법은 코드 섹션에 대한 자세한 타이밍 정보를 수집하고 입력 및 출력 작업이 응용 프로그램 성능에 미치는 영향을 이해하는 데 유용합니다.|-   [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)|  
|**동시성**:  동시성 방법은 스레드가 응용 프로그램 리소스에 대한 액세스 잠금이 해제될 때까지 기다리는 경우와 같이 코드 실행을 차단하는 각 이벤트에 대한 데이터를 수집하는 방법입니다.  이 방법은 다중 스레드 응용 프로그램을 분석하는 데 유용합니다.|-   [스레드 및 프로세스 동시성 데이터 수집](../profiling/collecting-thread-and-process-concurrency-data.md)|  
  
 샘플링 또는 계측 방법을 사용하여 .NET 메모리 데이터를 수집할 수 있습니다.  **.NET 메모리 프로파일링** 아래에서 데이터 형식을 선택합니다.  
  
|||  
|-|-|  
|**.NET 개체 할당 정보 수집**:  기본적으로는 할당된 개체의 개수 및 크기가 데이터에 포함됩니다.  .NET 메모리 데이터 수집을 사용하거나 사용하지 않도록 설정하려면 이 확인란을 선택하거나 선택 취소합니다.<br /><br /> **추가적으로 .NET 개체 수명 정보 수집**:  메모리 개체를 확보하는 데 사용된 가비지 수집 세대에 대한 데이터를 포함하려면 이 확인란을 선택합니다.|-   [.NET 메모리 할당 및 수명 데이터 수집](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)|  
  
 프로 파일링 세션 페이지는 일시 중지, 다시 시작, 프로 파일링을 중지할 수 있는 곳에서, 응용 프로그램 프로 파일링을 시작하면 나타납니다.  
  
 ![프로파일링 세션 페이지](../profiling/media/prof_profilingsessionpage.png "PROF\_ProfilingSessionPage")  
  
## 프로파일링 데이터 파일 옵션 설정  
  
|||  
|-|-|  
|**보고서**:  기본적으로 프로파일링 데이터 파일\(.vsp\)은 프로파일링된 응용 프로그램의 이름을 따라 이름이 지정되며 솔루션 또는 프로젝트 폴더에 저장됩니다.  이름에는 날짜 문자열도 추가되며 중복 이름을 방지하기 위해 증분 숫자가 데이터 파일에 추가됩니다.  이러한 옵션을 변경할 수 있습니다.|-   [방법: 프로파일링 데이터 파일 이름 옵션 설정](../profiling/how-to-set-performance-data-file-name-options.md)|