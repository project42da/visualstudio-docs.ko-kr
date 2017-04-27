---
title: "DA0018: 프로세스 관리 메모리 한도로 실행 중인 32비트 응용 프로그램 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.18"
  - "vs.performance.DA0018"
  - "vs.performance.rules.DA0018"
ms.assetid: 98eb2d96-f92f-42f9-915c-e5ac2330ffbf
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# DA0018: 프로세스 관리 메모리 한도로 실행 중인 32비트 응용 프로그램
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0018|  
|범주|프로파일링 도구 사용|  
|프로파일링 방법|샘플링|  
|메시지|관리되는 메모리 할당이 32비트 프로세스의 기본 제한에 근접하고 있습니다.  응용 프로그램이 메모리 바인딩될 수 있습니다.|  
|규칙 유형|경고|  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링하는 경우에는 적어도 10개의 샘플을 수집하여 이 규칙을 트리거해야 합니다.  
  
## 원인  
 프로파일링 실행 중 수집된 시스템 데이터가 .NET Framework 메모리 힙이 32비트 프로세스에서 관리되는 힙의 도달 가능한 최대 크기에 근접했음을 나타냅니다.  이 최대 크기는 기본값으로,  전용 바이트에 할당할 수 있는 프로세스 주소 공간의 총 크기를 기반으로 합니다.  보고되는 값은 프로파일링되는 프로세스가 활성 상태였던 동안 관찰된 최대값입니다.  .NET 메모리 프로파일링 방법을 사용하여 다시 프로파일링하고 응용 프로그램의 관리되는 리소스 사용을 최적화하는 것이 좋습니다.  
  
 관리되는 힙의 크기가 기본 제한에 근접하면 자동 가비지 수집 프로세스가 더 자주 호출되어야 합니다.  이 경우 메모리 관리의 오버헤드가 증가합니다.  
  
 이 규칙은 32비트 컴퓨터에서 실행되는 32비트 응용 프로그램에 대해서만 발생합니다.  
  
## 규칙 설명  
 Microsoft .NET CLR\(공용 언어 런타임\)에서는 가비지 수집기를 사용하여 응용 프로그램이 더 이상 사용하지 않는 개체에서 메모리를 회수하는 자동 메모리 관리 메커니즘을 제공합니다.  가비지 수집기는 많은 할당의 수명이 짧다는 가정에 따른 세대 기반 기능입니다.  지역 변수 등은 수명이 짧아야 합니다.  새로 만들어진 개체는 0세대\(Gen 0\)에서 시작된 후 가비지 수집 실행 시 수집되지 않으면 1세대로 진행되었다가 응용 프로그램이 여전히 해당 개체를 사용할 경우 마지막으로 2세대로 전환됩니다.  
  
 85 KB 보다 큰 경우에 관리 되는 개체는 대형 개체 힙에 있는 가비지 수집 및 압축 보다 작은 여러 개체를 자주 할당 됩니다. 대형 개체는 보다 지속적인 것을 아니라 지속적인 대형 개체를 자주 할당 되는 소형 개체 최악의 상태로 단편화 힙를 생성할 수 있습니다 간주 되므로 별도로 관리 됩니다.  
  
 관리되는 힙의 총 크기가 기본 제한에 근접하면 일반적으로 메모리 관리의 오버헤드는 응용 프로그램의 응답성과 확장성에 영향을 줄 수 있을 정도로 증가합니다.  
  
## 경고를 조사하는 방법  
 오류 목록 창에서 메시지를 두 번 클릭하여 [표시](../profiling/marks-view.md) 뷰로 이동합니다.  **.NET CLR Memory\\\# Bytes in all Heaps** 및 **\# Total committed bytes** 열을 찾습니다.  프로그램 실행 단계 중 관리되는 메모리 할당이 다른 단계보다 과도한 특정 단계가 있는지 확인합니다.  **\# Bytes in all Heaps** 열의 값을 **.NET CLR Memory\\\# Gen 0 Collections**, **.NET CLR Memory\\\# Gen 1 Collections** 및 **.NET CLR Memory\\\# Gen 2 Collections** 열에 보고된 가비지 수집 비율과 비교하여 관리되는 메모리 할당의 패턴이 가비지 수집 비율에 영향을 주고 있는지 확인합니다.  
  
 .NET Framework 응용 프로그램에서 공용 언어 런타임은 관리되는 힙의 총 크기를 프로세스 주소 공간에서 전용 영역이 차지하는 최대 크기의 1\/2보다 약간 낮은 수준으로 제한합니다.  32비트 컴퓨터에서 실행되는 32비트 프로세스의 경우 프로세스 주소 공간의 전용 부분에 대한 상한은 2GB입니다.  관리되는 힙의 총 크기가 기본 제한에 근접하기 시작하면 메모리 관리의 오버헤드가 증가하고 응용 프로그램 성능이 저하될 수 있습니다.  
  
 관리되는 메모리의 과도한 오버헤드가 문제가 되는 경우 다음 옵션 중 하나를 선택합니다.  
  
-   응용 프로그램의 관리되는 메모리 리소스 사용 최적화  
  
     또는  
  
-   32비트 프로세스의 최대 가상 메모리 크기에 대한 아키텍처 제약 조건을 완화하기 위한 단계 수행  
  
 응용 프로그램의 관리되는 메모리 리소스 사용을 최적화하려면 .NET 메모리 할당 프로파일링 실행을 통해 관리되는 메모리 할당 데이터를 수집합니다.  [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md) 보고서를 검토하여 응용 프로그램의 메모리 할당 패턴을 파악합니다.  
  
 [개체 수명 뷰](../profiling/object-lifetime-view.md)를 사용하여 프로그램의 데이터 개체 중 세대에서 수집되지 않고 남아 있다가 해당 세대에서 회수되는 개체를 확인합니다.  
  
 [할당 뷰](../profiling/dotnet-memory-allocations-view.md)를 사용하여 이러한 할당이 발생한 실행 경로를 확인합니다.  
  
 가비지 수집 성능을 향상시키는 방법에 대한 자세한 내용은 MSDN 웹 사이트에서 .NET Framework 기술 문서, [가비지 수집기 기본 및 성능 힌트](http://go.microsoft.com/fwlink/?LinkId=177946)를 참조하십시오.  
  
 프로세스 주소 공간 중 전용 부분의 가상 메모리 크기에 대한 아키텍처 제약 조건을 완화하려면 이 32비트 프로세스를 64비트 컴퓨터에서 실행해 봅니다.  64비트 컴퓨터의 32비트 프로세스는 최대 4GB의 전용 가상 메모리를 사용할 수 있습니다.  
  
 64비트 컴퓨터에서 실행되는 64비트 프로세스는 최대 8TB의 가상 메모리를 사용할 수 있습니다.  따라서 네이티브 64비트 응용 프로그램으로 실행되도록 응용 프로그램을 다시 컴파일하는 것이 좋습니다.  이 규칙은 단지 정보용이며 수정 작업이 필요하지 않을 수 있습니다.