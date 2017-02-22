---
title: "호출 트리 뷰 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.view.calltree"
helpviewer_keywords: 
  - "호출 트리 뷰"
  - "성능 보고서, 호출 트리 뷰"
  - "프로파일링 도구 보고서, 호출 트리 뷰"
  - "프로파일링 도구, 호출 트리 뷰"
ms.assetid: b2dbc033-bf95-4d10-8e51-f9462979133e
caps.latest.revision: 34
caps.handback.revision: 34
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 호출 트리 뷰
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

호출 트리 뷰에는 프로파일링된 응용 프로그램에서 이동한 함수 실행 경로가 표시됩니다.  트리의 루트는 응용 프로그램 또는 구성 요소에 대한 진입점입니다.  각 함수 노드에는 호출한 모든 함수 및 이러한 함수 호출에 대한 성능 데이터가 나열됩니다.  
  
 또한 호출 트리 뷰는 가장 많은 시간을 소모하거나 가장 자주 샘플링된 함수의 실행 경로를 확장하여 강조 표시합니다.  성능 부담이 가장 큰 경로를 표시하려면 함수를 마우스 오른쪽 단추로 클릭하고 **실행 부하 과다 경로 확장**을 클릭합니다.  
  
 프로파일링 실행 시 각 프로세스는 루트 노드로 표시됩니다.  시작 노드로 설정할 노드를 마우스 오른쪽 단추로 클릭한 다음 **루트 설정**을 선택하여 호출 트리 뷰의 시작 노드를 설정할 수 있습니다.  
  
 루트 노드를 설정하면 선택한 노드의 하위 트리를 제외한 다른 모든 항목이 뷰에서 제거됩니다.  루트 노드를 보고 있던 노드로 다시 설정할 수 있습니다.  호출 트리 뷰 창에서 마우스 오른쪽 단추를 클릭한 다음 **루트 다시 설정**을 선택합니다.  
  
 호출 트리 뷰는 열을 추가하거나 제거하도록 사용자 지정할 수 있습니다.  **열 이름 제목 표시줄**을 마우스 오른쪽 단추로 클릭하고 **열 추가\/제거**를 선택합니다.  
  
 호출 트리 뷰에서는 표시되는 데이터의 크기를 제한하여 노이즈 감소를 구성할 수 있습니다.  노이즈 감소를 사용하면 뷰에서 성능 문제가 더욱 두드러집니다.  성능 문제를 쉽게 구별할 수 있으면 분석 작업이 더 쉬워집니다.  자세한 내용은 [방법: 보고서 뷰에서 노이즈 감소 구성](../profiling/how-to-configure-noise-reduction-in-report-views.md)을 참조하십시오.  
  
> [!NOTE]
>  노이즈 감소를 사용하는 경우 경고를 표시하도록 구성하면 보고서에 정보 표시줄이 표시됩니다.  
  
 호출 트리 뷰의 열 정의에 대한 자세한 내용은 다음을 참조하십시오.  
  
 [호출 트리 뷰](../profiling/call-tree-view-sampling-data.md)  
  
 [호출 트리 뷰](../profiling/call-tree-view-instrumentation-data.md)  
  
 [호출 트리 뷰 \- 샘플링](../profiling/call-tree-view-dotnet-memory-sampling-data.md)  
  
 [호출 트리 뷰](../profiling/call-tree-view-contention-data.md)  
  
## 참고 항목  
 [프로파일링 도구 보고서 뷰](../profiling/performance-report-views.md)   
 [계측 데이터 값 이해](../profiling/understanding-instrumentation-data-values.md)   
 [샘플링 데이터 값 이해](../profiling/understanding-sampling-data-values.md)