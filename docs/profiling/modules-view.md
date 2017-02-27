---
title: "모듈 뷰 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.view.modules"
helpviewer_keywords: 
  - "모듈 뷰"
  - "프로파일링 도구 보고서, 모듈 뷰"
  - "프로파일링 도구, 모듈 뷰"
ms.assetid: 4314a404-2120-425b-be42-180cd4bac840
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# 모듈 뷰
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

모듈 뷰에는 프로파일링 데이터의 모듈이 나열되며,  각 모듈은 계층 트리의 루트 노드입니다.  모듈의 프로파일링된 함수는 모듈 노드 아래에 나열됩니다.  프로파일링 데이터가 샘플링 방법으로 수집된 경우 줄 정보는 함수 노드 아래에 나열되고 명령 포인터 데이터는 줄 노드 아래에 나열됩니다.  
  
 모듈 성능 데이터의 뷰를 표시하거나 닫으려면 모듈 이름을 확장하거나 축소합니다.  
  
 열을 추가하거나 제거하려면 보고서 창을 마우스 오른쪽 단추로 클릭한 다음 **열 추가\/제거**를 선택합니다.  열 이름을 클릭하면 데이터를 정렬할 수 있습니다.  자세한 내용은 [방법: 보고서 뷰 열 사용자 지정](../profiling/how-to-customize-report-view-columns.md)을 참조하십시오.  
  
 데이터를 수집하는 데 사용된 프로파일링 방법\(샘플링 또는 계측\) 및 프로파일링 실행 시 .NET 메모리 데이터가 수집되었는지 여부에 따라 모듈 뷰에서 사용 가능한 열이 달라집니다.  
  
## 참고 항목  
 [모듈 뷰](../profiling/modules-view-sampling-data.md)   
 [모듈 뷰](../profiling/modules-view-instrumentation-data.md)   
 [모듈 뷰 \- 계측](../profiling/modules-view-dotnet-memory-instrumentation-data.md)   
 [모듈 뷰 \- 샘플링](../profiling/modules-view-dotnet-memory-sampling-data.md)   
 [모듈 뷰](../profiling/modules-view-contention-data.md)