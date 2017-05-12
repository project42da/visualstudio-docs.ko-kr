---
title: "IDebugApplicationThread110 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplicationThread110 인터페이스"
ms.assetid: 25bc351f-3451-4387-9302-078f6292ddff
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IDebugApplicationThread110 인터페이스
더 많은 기능을 제공는 [IDebugApplicationThread 인터페이스](../../winscript/reference/idebugapplicationthread-interface.md) 인터페이스.  
  
> [!IMPORTANT]
>  V11.0 PDM 및 큰이 인터페이스를 구현 합니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 메서드  
 `IDebugApplicationThread110` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDebugApplicationThread110::AsynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread110-asynchronouscallintothread.md)|주 스레드에서 비동기 호출을 만듭니다.|  
|[IDebugApplicationThread110::GetActiveThreadRequestCount](../../winscript/reference/idebugapplicationthread110-getactivethreadrequestcount.md)|현재 PDM의 스레드 전환 메커니즘에서에서 얼마나 많은 스레드가 요청을 처리 하는 수입니다.  일반적으로 0 또는 1, 하지만 클 하나의 스레드가 호출 처리를 시작 하지만 트리거하는 동기 호출 스레드를 또는 그렇지 않은 경우 \(예를 들어, 디버거가 스레드에서 발생 하는 IDebugApplicationEvents 이벤트를 트리거하지\) 스레드를 일시 중단 하는 경우이 값이|  
|[IDebugApplicationThread110::IsSuspendedForBreakPoint](../../winscript/reference/idebugapplicationthread110-issuspendedforbreakpoint.md)|[IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md)이 스레드에서 호출 되 고 아직 완료 되지 않았습니다.|  
|[IDebugApplicationThread110::IsThreadCallable](../../winscript/reference/idebugapplicationthread110-isthreadcallable.md)|이 스레드는 PDM 스레드 전환 메커니즘 \(예: SynchronousCallInThread\)를 사용 하 여 호출을 처리할 수 있는 상태에서입니다.|