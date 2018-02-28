---
title: "IDebugApplicationThread110 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110 Interface
ms.assetid: 25bc351f-3451-4387-9302-078f6292ddff
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aee30ae68319810f58bf31f8d0eb32cf8f30d34c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationthread110-interface"></a>IDebugApplicationThread110 인터페이스
에 대 한 많은 기능을 제공 된 [IDebugApplicationThread 인터페이스](../../winscript/reference/idebugapplicationthread-interface.md) 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 인터페이스는 PDM v11.0 이상에 의해 구현됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="methods"></a>메서드  
 `IDebugApplicationThread110` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugApplicationThread110::AsynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread110-asynchronouscallintothread.md)|주 스레드에서 비동기 호출을 만듭니다.|  
|[IDebugApplicationThread110::GetActiveThreadRequestCount](../../winscript/reference/idebugapplicationthread110-getactivethreadrequestcount.md)|현재 처리 중인 메커니즘 전환 되는 PDM의 스레드에서 스레드 요청 수의 수입니다. 0 또는 1, 하지만이 경우 처리를 시작 하지만 스레드에서 동기 호출을 트리거합니다 또는 그렇지 않은 경우 (예를 들어을 트리거하여 디버거에서 실행 되는 IDebugApplicationEvents 이벤트로 스레드를 일시 중단 한 번의 호출 스레드 클 수에 대 한 가능한의 일반적으로 스레드)|  
|[IDebugApplicationThread110::IsSuspendedForBreakPoint](../../winscript/reference/idebugapplicationthread110-issuspendedforbreakpoint.md)|[IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md) 이 스레드에서 호출 되었고 완료 되지 않았습니다.|  
|[IDebugApplicationThread110::IsThreadCallable](../../winscript/reference/idebugapplicationthread110-isthreadcallable.md)|이 스레드가 메커니즘 (예: SynchronousCallInThread) 전환 되는 PDM의 스레드를 사용 하 여 수행 된 호출을 처리할 수 있는 상태입니다.|