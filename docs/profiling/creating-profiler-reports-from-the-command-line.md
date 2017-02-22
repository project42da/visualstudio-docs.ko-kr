---
title: "명령줄에서 프로파일러 보고서 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c886f8af-2014-4fec-9b24-d98b68ecafb7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 명령줄에서 프로파일러 보고서 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**VSPerfReport** 명령줄 도구를 사용하여 프로파일링 데이터 파일\(.vsp\)에서 .xml 또는 쉼표로 구분된 값\(.csv\) 형식의 보고서를 만들 수 있습니다.  VSPerfReport 보고서 유형은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 대한 인터페이스의 테이블 기반 뷰와 일치합니다.  코드만 표시 하고 프로 파일링 데이터 파일의 한 세그먼트만 표시할 보고서를 필터링 할 수 있습니다.  자세한 내용은 [VSPerfReport](../profiling/vsperfreport.md)을 참조하십시오.  
  
 .vsp 파일에 기호를 포함하고 보다 작으면서 빠르게 열 수 있는 미리 분석된 보고서 파일\(.vsps\)을 만들어 프로파일링 데이터 파일을 공유하기 쉽게 만들 수도 있습니다.  
  
## 일반 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**기본 보고서를 만듭니다.** VSPerfReport 보고서 형식을 모두 또는 일부 만듭니다.|-   [기본 보고서 만들기](../profiling/creating-basic-profiling-reports-from-the-command-line.md)|  
|**두 프로파일링 데이터 파일을 비교합니다.** 두 프로파일링 데이터 파일의 성능 데이터를 비교하는 "diff" 보고서를 만듭니다.|-   [방법: 명령 프롬프트에서 프로파일러 비교 보고서 만들기](../profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt.md)|  
|**호출 추적 및 ETW\(Windows용 이벤트 추적\) 데이터를 봅니다.** 응용 프로그램 함수의 각 진입 및 종료 지점과 해당 함수에서 실행되는 다른 함수에 대한 각 호출과 관련된 타이밍 정보를 나열하는 호출 추적 보고서를 만듭니다.  또는 프로파일링 실행 시 수집된 모든 ETW 이벤트의 세부 목록을 만듭니다.|-   [방법: 호출 추적 보고서 만들기](../profiling/how-to-create-a-profiling-tools-call-trace-report.md)|  
|**보고서를 필터링합니다.** 프로파일링 데이터 파일에서 해당 코드의 함수만으로 또는 특정 시간으로 보고서를 제한합니다.|-   [방법: 명령줄에서 보고서 필터링](../profiling/how-to-filter-reports-from-the-command-line.md)|  
|**이식 가능한 프로파일링 데이터 파일을 만듭니다.** 프로파일링 데이터를 보다 쉽게 공유하려면 .vsp 파일에 프로파일링 실행에 대한 기호를 포함합니다.  크기가 작고 빠르게 열 수 있는 미리 분석된 프로파일링 데이터 파일\(.vsps\)을 만들 수도 있습니다.|-   [이식 가능한 프로파일링 데이터 파일 만들기](../profiling/creating-portable-profiling-data-files-from-the-command-line.md)|