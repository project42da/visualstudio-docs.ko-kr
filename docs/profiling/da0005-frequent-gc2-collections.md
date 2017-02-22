---
title: "DA0005: GC2 수집이 많습니다. | Microsoft Docs"
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
  - "vs.performance.DA0005"
  - "vs.performance.rules.DAManyGC2Collections"
  - "vs.performance.5"
  - "vs.performance.rules.DA0005"
ms.assetid: 8d3f267c-8a74-4cf4-91a5-0b06a76dc2bd
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0005: GC2 수집이 많습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0005|  
|범주|.NET Framework 사용|  
|프로파일링 방법|.NET 메모리|  
|메시지|2세대 가비지 수집에서 많은 개체가 수집되고 있습니다.|  
|메시지 형식|경고|  
  
## 원인  
 2세대 가비지 수집에서 회수되는 .NET 메모리 개체가 매우 많습니다.  
  
## 규칙 설명  
 Microsoft .NET CLR\(공용 언어 런타임\)에서는 가비지 수집기를 사용하여 응용 프로그램이 더 이상 사용하지 않는 개체에서 메모리를 회수하는 자동 메모리 관리 메커니즘을 제공합니다.  가비지 수집기는 많은 할당의 수명이 짧다는 가정에 따른 세대 기반 기능입니다.  지역 변수 등은 수명이 짧아야 합니다.  새로 만들어진 개체는 0세대\(Gen 0\)에서 시작된 후 가비지 수집 실행 시 수집되지 않으면 1세대로 진행되었다가 응용 프로그램이 여전히 해당 개체를 사용할 경우 마지막으로 2세대로 전환됩니다.  
  
 0세대에 있는 개체는 자주 수집되며 일반적으로 매우 효율적으로 수집됩니다.  1세대에 있는 개체는 수집되는 빈도가 적으며 덜 효율적으로 수집됩니다.  마지막으로, 2세대에 있는 수명이 긴 개체는 더 적은 빈도로 수집되어야 합니다.  완전 가비지 수집 실행인 2세대 수집은 가장 부담이 큰 작업이기도 합니다.  
  
 이 규칙은 2세대 가비지 수집이 비율적으로 너무 많이 수행된 경우에 발생합니다.  1세대에서 수집되지 않고 유지되지만 2세대 전체 수집에서 수집될 수 있는 짧은 수명의 개체가 너무 많으면 메모리 관리 비용이 상당히 증가할 수 있습니다.  자세한 내용은 MSDN 웹 사이트에서 Rico Mariani's Performance Tidbits의 [Mid\-life crisis](http://go.microsoft.com/fwlink/?LinkId=177835) 게시물을 참조하십시오.  
  
## 경고를 조사하는 방법  
 [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md) 보고서를 검토하여 응용 프로그램의 메모리 할당 패턴을 파악합니다.  [개체 수명 뷰](../profiling/object-lifetime-view.md)를 사용하여 프로그램의 데이터 개체 중 2세대에서 수집되지 않고 남아 있다가 해당 세대에서 회수되는 개체를 확인합니다.  [할당 뷰](../profiling/dotnet-memory-allocations-view.md)를 사용하여 이러한 할당이 발생한 실행 경로를 확인합니다.  
  
 가비지 수집 성능을 향상시키는 방법에 대한 자세한 내용은 Microsoft 웹 사이트의 [가비지 수집기 기본 및 성능 힌트](http://go.microsoft.com/fwlink/?LinkId=148226) 를 참조하십시오.  자동 가비지 수집의 오버헤드에 대한 자세한 내용은 [대형 개체 힙 살펴보기](http://go.microsoft.com/fwlink/?LinkId=177836)를 참조하십시오.