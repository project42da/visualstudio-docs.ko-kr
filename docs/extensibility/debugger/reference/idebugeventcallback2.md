---
title: IDebugEventCallback2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEventCallback2
helpviewer_keywords:
- IDebugEventCallback2
ms.assetid: 2c935ee0-2e22-4be0-a852-73736f33c8c9
caps.latest.revision: 15
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 165f973fa9139f281211e6b01167b3d7044166df
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugeventcallback2"></a>IDebugEventCallback2
이 인터페이스는 세션 디버그 관리자 (SDM)로 디버그 이벤트를 보내는 디버그 엔진 (DE)에 의해 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugEventCallback2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]디버그 엔진에서 이벤트를 받도록이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 SDM 호출할 때 일반적으로 디버그 엔진이이 인터페이스는 [연결](../../../extensibility/debugger/reference/idebugprogram2-attach.md), [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md), 또는 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)합니다. 디버그 엔진은 SDM를 호출 하 여 이벤트를 보냅니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugEventCallback2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)|디버깅은 SDM에 이벤트 알림을 보냅니다.|  
  
## <a name="remarks"></a>설명  
 하지만 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 및 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 수행는 지정 된 `IDebugEventCallback2` 인터페이스의 경우 이것이 및 인터페이스 포인터에 null 값은 항상 합니다. 대신, 디버그 엔진을 사용 해야 합니다는 `IDebugEventCallback2` 인터페이스에 대 한 호출에서 받은 [연결](../../../extensibility/debugger/reference/idebugprogram2-attach.md), [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md), 또는 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)합니다.  
  
 패키지를 구현 하는 경우 [IDebugEventCallback](../../../extensibility/debugger/reference/idebugeventcallback2.md) 관리 코드에서 좋습니다는 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 에 전달 되는 다양 한 인터페이스에 대해 호출 될 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [연결](../../../extensibility/debugger/reference/idebugprogram2-attach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)