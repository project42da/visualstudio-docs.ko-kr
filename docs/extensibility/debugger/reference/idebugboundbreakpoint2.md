---
title: IDebugBoundBreakpoint2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBoundBreakpoint2
helpviewer_keywords: IDebugBoundBreakpoint2 interface
ms.assetid: df33c52e-ded2-48a0-951d-1f36c8fc922e
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6ce63ce7f7d6a4f438c0e9f622c34a2231afd6ef
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugboundbreakpoint2"></a>IDebugBoundBreakpoint2
이 인터페이스 코드 위치에 바인딩되는 중단점을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugBoundBreakpoint2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 중단점에 대 한 지원의 일부로이 인터페이스를 구현합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 호출 [바인딩할](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) 이 인터페이스를 만듭니다. 에 대 한 호출이 [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md) 및 [다음](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md) 또한이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugBoundBreakpoint2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)|지정 된 바인딩된 중단점 만들어진 보류 중인 중단점을 가져옵니다.|  
|[우편 번호](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)|이 바인딩된 중단점의 상태를 가져옵니다.|  
|[GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md)|바인딩된 중단점이 현재 적중된 횟수를 가져옵니다.|  
|[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)|이 중단점을 설명 하는 중단점 해상도를 가져옵니다.|  
|[사용 하도록 설정](../../../extensibility/debugger/reference/idebugboundbreakpoint2-enable.md)|중단점을 해제 하거나 사용 합니다.|  
|[SetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-sethitcount.md)|이 바인딩된 중단점의 적중된 횟수를 설정합니다.|  
|[SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)|설정 하거나 바인딩된 중단점이와 관련 된 조건을 변경 합니다.|  
|[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)|패스 횟수가 중단점과 연결 된 바인딩된 변경 또는 설정 합니다.|  
|[삭제](../../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)|중단점을 삭제합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)   
 [다음](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md)   
 [바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)