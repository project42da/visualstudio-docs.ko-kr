---
title: "요약 뷰 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.view.summary"
helpviewer_keywords: 
  - "성능 보고서, 요약 뷰"
  - "프로파일링 도구 보고서, 요약 뷰"
  - "프로파일링 도구, 요약 뷰"
  - "요약 뷰"
ms.assetid: 98a1eb71-bbf5-4ce7-8559-cdc29f082c4b
caps.latest.revision: 37
caps.handback.revision: 37
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 요약 뷰
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

요약 뷰에는 프로파일링 실행 시 성능 부담이 가장 큰 함수 또는 개체에 대한 정보가 표시됩니다.  이 뷰는 프로파일링 방법의 성능 메트릭을 기반으로 가장 비싼 함수 또는 개체의 시간 표시 막대 그래프 및 두 개 이상의 목록을 제공합니다.  이 보기의 데이터는 사용된 프로파일링 방법\(샘플링, 계측 또는 동시성\) 및 .NET 메모리 할당이 수집되었는지 여부에 따라 달라집니다.  
  
 동시성 데이터의 요약 뷰를 제외한 모든 요약 뷰의 경우 요약 뷰의 시간 표시 그래프에서는 프로파일링이 발생한 시간 동안 프로파일링된 응용 프로그램의 프로세서\(CPU\) 사용률을 보여 줍니다.  
  
-   그래프에 시간 세그먼트를 지정하는 경우 해당 세그먼트에 대한 데이터를 다시 분석하거나 시간 표시 막대를 지정한 세그먼트로 확대\/축소할 수 있습니다.  자세한 내용은 [방법: 요약 시간 표시 막대에서 보고서 뷰 필터링](../Topic/How%20to:%20Filter%20Report%20Views%20from%20the%20Summary%20Timeline.md)을 참조하십시오.  
  
-   요약 뷰 목록에서 함수를 클릭하여 해당 함수에 대한 함수 정보 뷰를 열 수 있습니다.  함수를 마우스 오른쪽 단추로 클릭하면 다른 보기 옵션을 볼 수 있습니다.  
  
-   요약 뷰 목록에 나타나는 항목의 수를 수정하려면 **도구** 메뉴를 열고 **옵션**을 가리킨 다음 **성능 도구**를 클릭합니다.  **일반 설정**에서 **요약 뷰의 함수 개수** 설정을 수정합니다.  
  
## 알림 링크  
 알림 목록의 링크를 클릭하여 보고서에 대한 표시 옵션을 설정할 수도 있습니다.  목록은 시간 표시 막대 그래프 오른쪽에 있습니다.  
  
|||  
|-|-|  
|**비\-사용자 코드 표시**<br /><br /> **내 코드만 표시**|계측 방법을 사용하여 수집된 네이티브 코드 또는 프로파일링 데이터에 사용할 수 없습니다.  사용자 코드\(**Show Just My Code**\)의 데이터만 표시와 시스템 코드\(**Show Non\-User Code**\)를 포함한 모든 코드의 데이터 표시 사이를 전환합니다.  기본적으로 데이터는 사용자 코드로 제한됩니다.  설정을 변경하려면 [방법: 내 코드만 표시하도록 보고서 뷰 필터링](../Topic/How%20to:%20Filter%20Profiling%20Tools%20Report%20Views%20to%20Display%20Just%20My%20Code.md)를 참조하십시오.|  
|**보기 지침**|**오류 목록** 창에 성능 규칙 경고를 표시합니다.  자세한 내용은 [성능 규칙을 사용하여 데이터 분석](../profiling/using-performance-rules-to-analyze-data.md)을 참조하십시오.|  
  
## 보고서  
 보고서 목록에서 링크를 클릭하여 다른 뷰를 열고 보고서를 비교, 저장 또는 필터링할 수 있습니다.  목록은 시간 표시 막대 그래프 오른쪽에 있습니다.  
  
|||  
|-|-|  
|**트리밍된 호출 트리 표시**|호출 트리 뷰에 가장 비싼 실행 경로를 표시합니다.  자세한 내용은 [호출 트리 뷰](../profiling/call-tree-view.md)을 참조하십시오.|  
|**핫 선 표시**|계측 방법을 사용하여 수집된 프로파일링 데이터에는 사용할 수 없습니다.  줄 뷰에 가장 비싼 소스 코드 줄을 표시합니다.  자세한 내용은 [줄 뷰](../profiling/lines-view.md)을 참조하십시오.|  
|**보고서 비교**|다른 프로파일링 데이터 파일을 지정하여 현재 파일과 비교할 수 있는 **비교할 분석 파일을 선택합니다.** 창을 표시합니다.  자세한 내용은 [프로파일링 도구 데이터 파일 비교](../profiling/comparing-performance-data-files.md)을 참조하십시오.|  
|**보고서 데이터 내보내기**|쉼표로 구분된 값 \(.csv\) 또는 .xml 파일로 저장하기 위한 보고서 뷰를 하나 이상 지정할 수 있는 **보고서 내보내기** 대화 상자를 표시합니다.  자세한 내용은 [How to: Export Profiling Tools Reports](http://msdn.microsoft.com/ko-kr/174b5bd3-df9b-4fd4-88d4-76032ab90451)을 참조하십시오.|  
|**분석된 보고서 저장**|현재 프로파일 데이터 파일을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]용 인터페이스에서 더 빨리 여는 .vsps 파일로 저장합니다.  자세한 내용은 [How to: Save Analyzed Profiling Data Files](http://msdn.microsoft.com/ko-kr/0340ddde-caf4-48ac-8af3-d15dcdade556)을 참조하십시오.|  
|**보고서 데이터 필터링**|보고서 보기에서 데이터를 제한하는 조건을 지정할 수 있는 프로파일링 보고서 필터 창을 표시합니다.  자세한 내용은 [프로파일링 도구 보고서 뷰 필터](../profiling/performance-report-view-filter.md)을 참조하십시오.|  
|**전체 화면 표시\/숨기기**|보고서 보기를 위해 전체 화면 모드로 전환합니다.|  
  
## 참고 항목  
 [요약 뷰](../profiling/summary-view-sampling-data.md)   
 [요약 뷰](../profiling/summary-view-instrumentation-data.md)   
 [요약 뷰](../profiling/summary-view-dotnet-memory-data.md)