---
title: "DA0504: 프로파일링 중인 프로세스에 대한 최대 작업 집합(바이트) | Microsoft Docs"
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
  - "vs.performance.DA0504"
  - "vs.performance.504"
  - "vs.performance.rules.DA0504"
ms.assetid: 36e71603-ece7-4000-85fc-9da4eed61bf2
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0504: 프로파일링 중인 프로세스에 대한 최대 작업 집합(바이트)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0504|  
|범주|리소스 관리|  
|프로파일링 방법|모두|  
|메시지|이 정보는 참고용으로만 수집됩니다.  Process Working Set 카운터는 프로파일링하고 있는 프로세스의 실제 메모리 사용량을 측정합니다.  보고된 값은 모든 측정 간격에 걸쳐 관측된 최대값입니다.|  
|규칙 유형|정보|  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링하는 경우에는 적어도 10개의 샘플을 수집하여 이 규칙을 트리거해야 합니다.  
  
## 규칙 설명  
 이 메시지는 프로세스에서 현재 사용하고 있는 실제 메모리의 최대 바이트 크기를 보고합니다.  프로세스 작업 집합은 현재 실제 메모리에 있는 프로세스 주소 공간의 페이지를 나타냅니다.  이 규칙은 프로파일링이 활성 상태였던 기간 중 프로세스 작업 집합의 최대값을 보고합니다.  
  
 보고되는 값에는 프로세스에서 참조한 공유 메모리 세그먼트의 상주 페이지가 포함됩니다.  프로세스에서 참조하는 공유 DLL은 계산되는 공유 메모리 세그먼트에 포함됩니다.  프로세스 작업 집합의 값은 공유 메모리 세그먼트 때문에 프로세스에서 할당한 가상 메모리 크기보다 높을 수 있습니다.  
  
 프로세스 작업 집합의 크기는 프로세스에서 실제로 사용하고 있는 가상 메모리의 크기를 반영합니다.  또한 이 크기는 응용 프로그램을 실행하는 데 사용할 수 있는 실제 메모리\(또는 RAM\)의 크기와 실행 중인 다른 프로세스에서 해당 실제 메모리에 대해 발생하는 경합에 따라 영향을 받습니다.  프로세스 작업 집합에 대 한 자세한 내용은 참조 [Working Set](http://go.microsoft.com/fwlink/?LinkId=177830) msdn Windows 메모리 관리 설명서에 있습니다.  
  
## 규칙 데이터 사용 방법  
 이 규칙은 Windows 성능 모니터링 기능에서 이 측정 데이터를 수집하며 이를 정보용으로만 보고합니다.  보고된 값을 사용하여 프로그램의 여러 버전 또는 빌드 간에 성능을 비교하거나, 여러 테스트 시나리오에서의 응용 프로그램 성능을 확인할 수 있습니다.  
  
 오류 목록 창에서 메시지를 두 번 클릭하여 프로파일링 데이터의 [표시 뷰](../profiling/marks-view.md)로 이동합니다.  **Process\\Working Set** 및 **Memory\\Pages\/sec** 카운터 열을 찾습니다.  그런 다음 **Process\\Working Set**의 최대값을 찾고 이를 **Memory\\Pages\/sec** 값과 비교합니다.  작업 집합 최대값은 페이징 IO 활동이 감소된 간격과 관련이 있는 경우가 많습니다. 특히, 컴퓨터의 메모리가 제한된 경우가 해당됩니다.