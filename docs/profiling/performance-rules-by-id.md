---
title: "ID별 성능 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a1c934c-4798-4df9-a8ef-eb17ef06b6a2
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# ID별 성능 규칙
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|경고|설명|  
|--------|--------|  
|[DA0001: 연결에 StringBuilder를 사용하십시오.](../Topic/DA0001:%20Use%20StringBuilder%20for%20concatenations.md)|System.String.Concat에 대한 호출이 프로파일링 데이터의 상당 비율을 차지합니다.  여러 세그먼트에서 문자열을 생성하려면 <xref:System.Text.StringBuilder> 클래스를 사용하는 것이 좋습니다.|  
|[DA0002: VSPerfCorProf.dll이 없습니다.](../profiling/da0002-vsperfcorprof-dll-is-missing.md)|프로파일러에서 프로파일링 실행 중 VSPerfCorProf.dll을 찾지 못했습니다.  이 경고는 프로파일러 데이터 수집용 명령줄 도구를 사용할 때 VSPerfCLREnv.cmd 도구를 사용하여 필요한 환경 변수를 초기화하지 않은 경우에 발생합니다.|  
|[DA0003: 커널 샘플이 많습니다.](../profiling/da0003-many-kernel-samples.md)|응용 프로그램에 대해 수집된 호출 스택 샘플 중 상당 비율이 커널 모드에서 실행되었습니다.  다른 프로파일링 방법으로 응용 프로그램을 프로파일링하는 것이 좋습니다.|  
|[DA0004: 프로세서 사용률이 높습니다.](../profiling/da0004-high-processor-usage.md)|계측 방법을 사용하여 수집된 프로파일링 데이터에서 프로세서\(CPU\) 사용률이 상당히 높게 나타났습니다.  CPU 바인딩된 응용 프로그램을 프로파일링할 때는 샘플링 프로파일링 방법을 사용하는 것이 좋습니다.|  
|[DA0005: GC2 수집이 많습니다.](../profiling/da0005-frequent-gc2-collections.md)|2세대 가비지 수집에서 회수되는 .NET 메모리 개체가 매우 많습니다.|  
|[DA0006: 값 형식에 대해 Equals\(\)를 재정의하십시오.](../profiling/da0006-override-equals-parens-for-value-types.md)|public 값 형식의 Equals 메서드 또는 같음 연산자에 대한 호출이 프로파일링 데이터의 상당 비율을 차지합니다.  보다 효율적인 메서드를 구현하는 것이 좋습니다.|  
|[DA0007: 제어 흐름에는 예외를 사용하지 마십시오.](../profiling/da0007-avoid-using-exceptions-for-control-flow.md)|프로파일링 데이터에서 .NET Framework 예외 처리기가 호출된 비율이 높습니다.  다른 제어 흐름 논리를 사용하여 throw되는 예외 수를 줄이는 것이 좋습니다.|  
|[DA0008: 수집되는 샘플 수가 적습니다.](../profiling/da0008-few-samples-collected.md)|프로파일링 실행 중 적은 수의 샘플만 수집되었습니다.  보다 의미 있는 결과를 얻으려면 실행 시간을 늘리거나 샘플링 주기를 더 빠르게 하는 것이 좋습니다.|  
|[DA0009: High % time in JIT](http://msdn.microsoft.com/ko-kr/b60c1767-515c-41d9-81c2-c70d0b7024fd)|응용 프로그램 실행 시간 중 상당 비율이 JIT\(Just\-In\-Time\) 컴파일러에서 소요되었습니다.|  
|[DA0010: GetHashCode의 부담이 큽니다.](../profiling/da0010-expensive-gethashcode.md)|해당 형식의 GetHashCode 메서드에 대한 호출이 프로파일링 데이터의 상당 비율을 차지하거나 이 메서드가 메모리를 할당합니다.|  
|[DA0011: CompareTo의 부담이 큽니다.](../profiling/da0011-expensive-compareto.md)|형식의 CompareTo 메서드가 부담이 크거나 메모리를 할당합니다.|  
|[DA0012: 리플렉션 양이 많습니다.](../Topic/DA0012:%20Significant%20amount%20of%20Reflection.md)|InvokeMember 및 GetMember 등의 System.Reflection 메서드에 대한 호출이나 MemberInvoke 등의 Type 메서드에 대한 호출이 프로파일링 데이터의 상당 비율을 차지합니다.  가능한 경우 이러한 메서드를 종속 어셈블리의 메서드에 대한 초기 바인딩으로 바꾸는 것이 좋습니다.|  
|[DA0013: String.Split 또는 String.Substring 사용률이 높습니다.](../profiling/da0013-high-usage-of-string-split-or-string-substring.md)|System.String.Split 또는 System.String.Substring 메서드에 대한 호출이 프로파일링 데이터의 상당 비율을 차지합니다.  문자열에 부분 문자열이 있는지 테스트할 경우 System.String.IndexOf 또는 System.String.IndexOfAny를 사용하는 것이 좋습니다.|  
|[DA0014: 활성 메모리를 디스크에 페이징하는 비율이 극도로 높습니다.](../Topic/DA0014:%20Extremely%20high%20rates%20of%20paging%20active%20memory%20to%20disk.md)|프로파일링 실행 시 수집된 시스템 성능 데이터가 전체 프로파일링 실행 기간 중 디스크로 페이징되거나 디스크에서 페이징된 활성 메모리의 비율이 매우 높음을 나타냅니다.  페이징 비율이 이렇게 높으면 대개 응용 프로그램 성능과 응답성에 영향이 있습니다.  알고리즘을 수정하여 메모리 할당량을 줄여 보십시오.  더 많은 메모리를 사용하여 컴퓨터에서 다시 프로파일링을 실행하는 응용 프로그램의 메모리 요구 사항을 고려해야 할 수가 있습니다.|  
|[DA0017: 디스크에 대한 높은 활성 메모리 페이징 비율](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|프로파일링 실행 시 수집된 시스템 성능 데이터가 전체 프로파일링 실행 기간 중 디스크로 페이징되거나 디스크에서 페이징된 활성 메모리의 비율이 매우 높음을 나타냅니다.  페이징 비율이 이렇게 높으면 대개 응용 프로그램 성능과 응답성에 영향이 있습니다.  알고리즘을 수정하여 메모리 할당량을 줄여 보십시오.  더 많은 메모리를 사용하여 컴퓨터에서 다시 프로파일링을 실행하는 응용 프로그램의 메모리 요구 사항을 고려해야 할 수가 있습니다.|  
|[DA0018: 프로세스 관리 메모리 한도로 실행 중인 32비트 응용 프로그램](../profiling/da0018-32-bit-application-running-at-process-managed-memory-limits.md)|프로파일링 실행 중 수집된 시스템 데이터가 .NET Framework 메모리 힙이 32비트 프로세스에서 관리되는 힙의 가능한 최대 크기에 근접했음을 나타냅니다.  보고되는 값은 프로파일링되는 프로세스가 활성 상태였던 동안 관찰된 최대값입니다.  응용 프로그램의 관리되는 리소스 사용을 최적화하는 것이 좋습니다.|  
|[DA0021: Gen 1 가비지 수집의 비율이 높습니다.](../profiling/da0021-high-rate-of-gen-1-garbage-collections.md)|프로파일링 중 수집된 시스템 성능 데이터가 .NET Framework 개체에 대한 메모리의 상당 비율이 0세대가 아니라 1세대 가비지 수집에서 회수되었음을 나타냅니다.|  
|[DA0022: Gen 2 가비지 수집의 비율이 높습니다.](../profiling/da0022-high-rate-of-gen-2-garbage-collections.md)|프로파일링 중 수집된 시스템 성능 데이터가 .NET Framework 개체에 대한 메모리의 상당 비율이 0세대 및 1세대가 아니라 2세대 가비지 수집에서 회수되었음을 나타냅니다.|  
|[DA0023: 높은 GC CPU 시간](../profiling/da0023-high-gc-cpu-time.md)|프로파일링 중 수집된 시스템 성능 데이터가 총 응용 프로그램 처리 시간에 비해 가비지 수집에 소요된 시간이 상당히 많음을 나타냅니다.|  
|[DA0024: 과도한 GC CPU 시간](../profiling/da0024-excessive-gc-cpu-time.md)|프로파일링 중 수집된 시스템 성능 데이터가 총 응용 프로그램 처리 시간에 비해 가비지 수집에 소요된 시간이 지나치게 많음을 나타냅니다.|  
|[DA0026: 과도한 커널 CPU 처리 시간](../Topic/DA0026:%20Excessive%20kernel%20CPU%20time%20processing.md)|커널 모드에서 실행된 CPU 시간의 비율이 사용자 모드에서 소요된 시간을 초과했습니다.  프로파일링을 다시 실행하고 시스템 호출\(syscall\) 수를 샘플링하여 커널 모드의 실행 시간이 높은 원인을 확인하는 것이 좋습니다.|  
|[DA0029: 지원되지 않는 CLR 버전](../profiling/da0029-unsupported-clr-version.md)|프로파일링 도구에서 지원되지 않는 .NET Framework 버전 1.1을 사용하는 응용 프로그램을 프로파일링하려고 했습니다.|  
|[DA0030: 데이터베이스 프로젝트에 대한 계층 상호 작용 측정값 수집](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md)|<xref:System.Data> 메서드에 대한 호출이 프로파일링 데이터의 상당 비율을 차지하며, 프로파일링 실행 시 계층 상호 작용 데이터를 수집하지 않았습니다.  프로파일링을 다시 실행하고 계층 상호 작용 데이터를 추가하는 것이 좋습니다.|  
|[DA0038: 높은 비율의 잠금 경합](../profiling/da0038-high-rate-of-lock-contentions.md)|프로파일링 데이터와 함께 수집된 시스템 성능 데이터가 응용 프로그램 실행 중 잠금 경합이 상당히 높은 비율로 발생했음을 나타냅니다.  동시성 프로파일링 방법으로 다시 프로파일링하여 경합 원인을 확인하는 것이 좋습니다.|  
|[DA0039: 매우 높은 비율의 잠금 경합](../profiling/da0039-very-high-rate-of-lock-contentions.md)|프로파일링 데이터와 함께 수집된 시스템 성능 데이터가 응용 프로그램 실행 중 잠금 경합이 매우 높은 비율로 발생했음을 나타냅니다.  동시성 프로파일링 방법으로 다시 프로파일링하여 경합 원인을 확인하는 것이 좋습니다.|  
|[DA0501: 프로파일링 중인 프로세스의 평균 CPU 사용](../Topic/DA0501:%20Average%20CPU%20consumption%20by%20the%20Process%20being%20profiled..md)|이 메시지는 프로세서가 응용 프로그램의 명령을 실행하는 데 소요된 시간의 백분율을 보고합니다.  보고되는 값은 프로파일링되는 프로세스가 활성 상태였던 전체 측정 간격의 평균입니다.  프로세서가 둘 이상인 컴퓨터에서는 이 값이 100%보다 클 수 있습니다.|  
|[DA0502: 프로파일링 중인 프로세스의 최대 CPU 사용](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|이 메시지는 프로세서가 응용 프로그램의 명령을 실행하는 데 소요된 시간의 최대 백분율을 보고합니다.  보고되는 값은 프로파일링되는 프로세스가 활성 상태였던 전체 측정 간격에서 보고된 최대값입니다.  프로세서가 둘 이상인 컴퓨터에서는 이 백분율이 100%보다 클 수 있습니다.|  
|[DA0503: 프로파일링 중인 프로세스에 대한 평균 작업 집합\(바이트\)](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|이 메시지는 프로세스에서 현재 사용하고 있는 실제 메모리\(작업 집합\)의 평균 바이트 크기를 보고합니다.  프로세스 작업 집합은 현재 실제 메모리에 있는 프로세스 주소 공간의 페이지를 나타냅니다.|  
|[DA0504: 프로파일링 중인 프로세스에 대한 최대 작업 집합\(바이트\)](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|이 메시지는 프로세스에서 현재 사용하고 있는 실제 메모리의 최대 바이트 크기를 보고합니다.  프로세스 작업 집합은 현재 실제 메모리에 있는 프로세스 주소 공간의 페이지를 나타냅니다.  이 규칙은 프로파일링이 활성 상태였던 기간 중 프로세스 작업 집합의 최대값을 보고합니다.|  
|[DA0505: 프로파일링 중인 프로세스에 할당되는 평균 전용 바이트](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|이 메시지는 프로세스에서 현재 할당한 가상 메모리\(전용 바이트\)의 평균 바이트 크기를 보고합니다.  전용 바이트는 프로세스에 의해 할당되어 프로세스 내에서 실행 중인 스레드에 의해서만 액세스될 수 있는 가상 메모리 위치를 나타냅니다.|  
|[DA0506: 프로파일링 중인 프로세스에 할당되는 최대 전용 바이트](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|이 메시지는 프로세스에서 현재 할당한 가상 메모리\(전용 바이트\)의 최대 바이트 크기를 보고합니다.  전용 바이트는 프로세스에 의해 할당되어 프로세스 내에서 실행 중인 스레드에 의해서만 액세스될 수 있는 가상 메모리 위치를 나타냅니다.|