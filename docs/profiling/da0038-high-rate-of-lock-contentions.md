---
title: "DA0038: 높은 비율의 잠금 경합 | Microsoft Docs"
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
  - "vs.performance.38"
  - "vs.performance.rules.DA0038"
  - "vs.performance.DA0038"
ms.assetid: ae0c8b2f-17b2-4f3d-a834-aa2f6371753b
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0038: 높은 비율의 잠금 경합
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0038|  
|범주|.NET Framework 사용|  
|프로파일링 방법|샘플링<br /><br /> 계측<br /><br /> .NET 메모리|  
|메시지|.NET 잠금 경합의 비율이 높습니다.  동시성 프로필을 실행하여 이 잠금 경합의 원인을 조사하십시오.|  
|규칙 유형|정보|  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링하는 경우에는 적어도 25개의 샘플을 수집하여 이 규칙을 트리거해야 합니다.  
  
## 원인  
 프로파일링 데이터와 함께 수집된 시스템 성능 데이터가 응용 프로그램 실행 중 잠금 경합이 상당히 높은 비율로 발생했음을 나타냅니다.  동시성 프로파일링 방법으로 다시 프로파일링하여 경합 원인을 확인하는 것이 좋습니다.  
  
## 규칙 설명  
 잠금은 다중 스레드 응용 프로그램에서 한 번에 한 스레드에 의해 연속으로 실행되어야 하는 코드 임계 영역을 보호하는 데 사용됩니다.  Microsoft .NET CLR\(공용 언어 런타임\)에서는 동기화 및 잠금 기본 형식의 전체 집합을 제공합니다.  예를 들어 C\# 언어에서는 lock 문\(Visual Basic의 경우 SyncLock\)을 지원합니다.  관리되는 응용 프로그램에서는 System.Threading 네임스페이스의 Monitor.Enter 및 Monitor.Exit 메서드를 호출하여 잠금을 직접적으로 가져오고 해제할 수 있습니다.  .NET Framework에서는 Mutex, ReaderWriterLock 및 Semaphore를 지원하는 클래스를 비롯하여 추가 동기화 및 잠금 기본 형식을 지원합니다.  자세한 내용은 MSDN 웹 사이트의 .NET Framework 개발자 가이드에서 [동기화 기본 형식 개요](http://go.microsoft.com/fwlink/?LinkId=177867) 를 참조하십시오.  .NET Framework 클래스는 Windows 운영 체제에 기본 제공된 하위 수준 동기화 서비스를 통해 자체적으로 계층화됩니다.  이러한 클래스에는 임계 영역 개체와 다양한 대기 및 이벤트 신호 함수가 포함됩니다.  자세한 내용은 참조는 MSDN Library의 Win32 및 COM 개발에서 [동기화](http://go.microsoft.com/fwlink/?LinkId=177869) 를 참조하세요.  
  
 동기화 및 잠금에 사용되는 .NET Framework 클래스와 네이티브 Windows 개체는 모두 연동 작업을 사용하여 변경해야 하는 공유 메모리 위치 아래에 있습니다.  연동 작업에서는 공유 메모리 위치에 대해 작동하는 하드웨어 관련 명령을 사용하여 원자 작업을 통해 공유 메모리 위치의 상태를 변경합니다.  원자 작업은 항상 컴퓨터의 모든 프로세서 간에 일관됩니다.  Lock 및 WaitHandle은 설정되거나 다시 설정될 때 자동으로 연동 작업을 사용하는 .NET 개체입니다.  연동 작업을 사용하여 스레드로부터 안전한 방식으로 업데이트해야 하는 응용 프로그램에는 다른 공유 메모리 데이터 구조가 있을 수 있습니다.  자세한 내용은 MSND 라이브러리의.NET Framework 섹션 [연동 작업](http://go.microsoft.com/fwlink/?LinkId=177870) 을 참조하십시오.  
  
 동기화와 잠금은 다중 스레드 응용 프로그램이 올바르게 실행되도록 하는 데 사용되는 메커니즘입니다.  다중 스레드 응용 프로그램의 각 스레드는 운영 체제에서 독립적으로 예약되는 독립적 실행 단위입니다.  잠금 경합은 다른 스레드에서 잠금을 보유하고 있기 때문에 잠금을 획득하려고 시도하는 스레드가 지연될 때마다 발생합니다.  
  
 잠금은 대개 중첩됩니다.  임계 영역을 실행하는 스레드에서 다른 잠금을 필요로 하는 함수를 수행하면 중첩이 발생합니다.  따라서 어느 정도의 잠금 중첩은 피할 수 없습니다.  임계 영역에서는 스레드 안전성을 보장하기 위해 잠금을 필요로 하는 .NET Framework 메서드를 호출할 수 있습니다.  응용 프로그램의 임계 영역에서 다른 잠금 핸들을 사용하여 잠그는 .NET Framework 메서드를 호출하면 잠금이 중첩됩니다.  잠금이 중첩될 경우 성능 문제가 발생할 수 있으며 이러한 문제는 해결 및 수정하기가 매우 어렵습니다.  
  
 이 규칙은 프로파일링 실행 중 얻은 측정값이 과도한 양의 잠금 경합이 있음을 나타내면 발생합니다.  잠금 경합이 있으면 잠금을 기다리는 스레드의 실행이 지연됩니다.  낮은 사양의 하드웨어에서 단위 테스트나 부하 테스트를 실행할 때는 매우 적은 양의 잠금 경합이 발생하더라도 이를 조사해야 합니다.  
  
> [!NOTE]
>  프로파일링 데이터에서 보고된 잠금 경합의 비율이 지나치게 높을 경우에는 이 정보 메시지 대신 [DA0039: 매우 높은 비율의 잠금 경합](../profiling/da0039-very-high-rate-of-lock-contentions.md) 경고 메시지가 발생합니다.  
  
## 경고를 조사하는 방법  
 메시지를 두 번 클릭하여 프로파일링 데이터의 [표시](../profiling/marks-view.md) 뷰로 이동합니다.  **.NET CLR LocksAndThreads\\Contention Rate \/ sec** 열을 찾습니다.  프로그램 실행 단계 중 잠금 경합이 다른 단계보다 과도한 특정 단계가 있는지 확인합니다.  
  
 이 규칙은 동시성 프로파일링 방법을 사용하지 않는 경우에만 발생합니다.  동시성 프로파일링 방법은 응용 프로그램에서 잠금 경합과 관련된 성능 문제를 진단하는 데 사용할 수 있는 최상의 도구입니다.  응용 프로그램의 잠금 동작을 이해하려면 동시성 프로파일링 데이터를 수집합니다.  과도하게 경합되는 잠금, 경합되는 잠금을 기다리는 동안 스레드 실행 시간이 지연된 시간 및 관련된 특정 코드를 파악해야 합니다.  동시성 프로필에서는 네이티브 Windows 기능, .NET Framework 클래스 및 그 밖에 응용 프로그램에서 참조하는 타사 라이브러리의 잠금 동작을 비롯하여 모든 잠금 경합에 대한 데이터를 수집합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE에서의 동시성 프로파일링에 대한 자세한 내용은 [스레드 및 프로세스 동시성 데이터 수집](../profiling/collecting-thread-and-process-concurrency-data.md)을 참조하십시오.  명령줄에서의 동시성 프로파일링에 대한 정보로 연결되는 링크는 [명령줄에서 프로파일링 방법 사용](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md)의 **Using the Concurrency Method to Collect Resource Contention and Thread Activity Data** 단원을 참조하십시오.