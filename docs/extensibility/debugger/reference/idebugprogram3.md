---
title: IDebugProgram3 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugProgram3 interface
ms.assetid: 4301ba23-c00c-4ce5-8b1e-3f27da312034
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 328fe3c863c4233c984db6de8bc992ea91b6a4d7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogram3"></a>IDebugProgram3
이 인터페이스는 프로세스에서 실행 되 고 확장 하는 프로그램 나타냅니다 [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md) 스레드 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProgram3 : IDebugProgram3  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 및 사용자 지정 포트 공급자는 프로세스에는 프로그램을 나타내며이 인터페이스를 구현 합니다. 세션 디버그 관리자 (SDM)도 정보를 제공 하려면이 인터페이스를 구현 [연결](../../../extensibility/debugger/reference/idebugprogram2-attach.md)합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 이벤트 새 프로그램에 대해이 인터페이스를 반환 합니다. 이 인터페이스는 여러 인터페이스에 있는 많은 메서드의 매개 변수도도 사용 됩니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugProgram3`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[ExecuteOnThread](../../../extensibility/debugger/reference/idebugprogram3-executeonthread.md)|프로그램을 실행합니다. 스레드를 사용자가을 실행할 때 보고 디버거 정보를 제공 하는 스레드 반환 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="remarks"></a>설명  
 프로그램은 하나 이상의 프로그램 구성 된 프로세스 동안 사용 하는 특정 런타임 아키텍처에서 실행 중인 스레드 컨테이너.  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)   
 [다음](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)