---
title: IDebugBreakpointUnboundEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBreakpointUnboundEvent2
helpviewer_keywords: IDebugBreakpointUnboundEvent2
ms.assetid: 6b1e1863-0c64-4d85-8ab9-aface522fdea
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa2e9e50205a400616bf71d0e60d60f4a826bdb6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugbreakpointunboundevent2"></a>IDebugBreakpointUnboundEvent2
이 인터페이스는 바인딩된 중단점이 해제 되었음을 로드 프로그램이 바운드 세션 디버그 관리자 (SDM)을 알려 줍니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugBreakpointUnboundEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 중단점에 대 한 지원의 일부로이 인터페이스를 구현합니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다 (은 SDM 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 액세스로는 `IDebugEvent2` 인터페이스).  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 DE을 만들어 바인딩된 중단점을 바인딩 해제 된 경우이 이벤트 개체를 보냅니다. 이벤트를 사용 하 여 보내집니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 은 SDM 디버깅 중인 프로그램에는 연결 된 경우 제공한 콜백 함수입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugBreakpointUnboundEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)|상태가 바인딩 해제 된 중단점을 가져옵니다.|  
|[GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)|중단점이 바인딩된 없습니다. 이유를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 디버그 엔진 DLL 또는 클래스를 언로드할 때 해당 모듈의 코드에 바인딩된 모든 중단점 디버깅 중인 프로그램에서 바인딩 해제 되어야 합니다. `IDebugBreakpointUnboundEvent2` 각 바인딩 해제 된 중단점을 위해 전송 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)