---
title: "호출자/호출 수신자 뷰 | Microsoft Docs"
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
  - "vs.performance.view.callercallee"
helpviewer_keywords: 
  - "프로파일링 도구, 보고서, 호출자/호출 수신자 뷰"
  - "프로파일링 도구, 호출자/호출 수신자 뷰"
  - "성능 보고서, 호출자/호출 수신자 뷰"
  - "호출자/호출 수신자 뷰"
ms.assetid: d3511bcf-cce0-4cbe-aecb-b94c7c80ad1b
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 호출자/호출 수신자 뷰
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

호출자\/호출 수신자 뷰에는 선택한 함수와 해당 부모 및 자식 함수에 대한 프로파일링 정보가 표시됩니다.  호출자\/호출 수신자 뷰에는 다음 세 개의 표가 있습니다.  
  
 **현재 함수**는 가운데 표에 나타나며, 선택한 함수에 대한 프로파일링 정보를 표시합니다.  프로파일링 실행 시 수집된 모든 함수 호출이 값에 포함됩니다.  
  
 **현재 함수를 호출한 함수**는 위쪽 표에 나타나며, 호출자\(부모\) 함수의 호출에 의해 생성된 선택한\(현재\) 함수의 값의 수를 표시합니다.  
  
 **현재 함수에서 호출된 함수**는 아래쪽 표에 나타나며, 현재 함수가 자식 함수를 호출한 경우 선택한 함수의 호출 수신자\(자식\) 함수에 대한 프로파일링 정보를 표시합니다.  
  
 데이터를 수집하는 데 사용된 프로파일링 방법\(샘플링 또는 계측\) 및 프로파일링 실행 시 .NET 메모리 데이터가 수집되었는지 여부에 따라 호출자\/호출 수신자 뷰에서 사용 가능한 열이 달라집니다.  
  
 뷰의 다른 두 부분에 나열된 함수 중 하나를 두 번 클릭하면 다른 함수를 보고서 뷰의 가운데 부분에 표시되는 현재 함수로 선택할 수 있습니다.  보고서 뷰가 자동으로 업데이트되어 변경 내용을 적용합니다.  
  
 열 이름을 클릭하면 데이터를 정렬할 수 있습니다.  호출자\/호출 수신자 뷰에 열을 더 추가할 수도 있습니다.  자세한 내용은 [방법: 보고서 뷰 열 사용자 지정](../profiling/how-to-customize-report-view-columns.md)을 참조하십시오.  
  
## 참고 항목  
 [호출자 \/ 호출 수신자 뷰](../profiling/caller-callee-view-sampling-data.md)   
 [호출자 \/ 호출 수신자 뷰](../profiling/caller-callee-view-instrumentation-data.md)   
 [호출자 \/ 호출 수신자 뷰 \- 계측](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [호출자 \/ 호출 수신자 뷰 \- 샘플링](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [호출자 \/ 호출 수신자 뷰](../profiling/caller-callee-view-contention-data.md)