---
title: IDebugEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEvent2
helpviewer_keywords: IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0d783cb13ee227e317afe9b49abedb6f53e9fa76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugevent2"></a>IDebugEvent2
이 인터페이스는 중단점에서 중지 하는 등의 중요 한 디버그 정보 및 디버깅 메시지와 같은 중요 하지 않은 정보를 모두 전달 하기 위해 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 및 사용자 지정 포트 공급자 이벤트의 다른 모든 인터페이스와 같은 개체에이 인터페이스를 구현합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 인터페이스에 지정 된 ID (IID) 인수를 사용 하 여 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 또는 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md), 세션 디버그 관리자 (SDM) 호출 하면 중지 [QueryInterface](/cpp/atl/queryinterface) 에 `IDebugEvent2` 가져오는 인터페이스를 적절 한 이벤트 인터페이스입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|이 디버그 이벤트에 대 한 특성을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 와 같은 보다 구체적인 이벤트 인터페이스 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)IDebugEvent2 인터페이스에서 파생 되지 않은 있지만와 같은 개체에는 별도 인터페이스로 구현 대신 않습니다, `IDebugEvent2`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)