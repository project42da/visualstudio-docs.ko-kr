---
title: IDebugEngineProgram2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2
helpviewer_keywords:
- IDebugEngineProgram2 interface
ms.assetid: 151003a9-2e4d-4acf-9f4d-365dfa6b9596
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ff075605371d39f9d3ff04df01c7022c52e809ef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugengineprogram2"></a>IDebugEngineProgram2
이 인터페이스는 다중 스레드 디버깅을 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugEngineProgram2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 동시 다중 스레드 디버깅을 지원 하도록이 인터페이스를 구현 합니다. 이 인터페이스를 구현 하는 동일한 개체에서 구현 됩니다는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수는 `IDebugProgram2` 인터페이스입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugEngineProgram2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[Stop](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)|이 프로그램에서 실행 중인 모든 스레드를 중지 합니다.|  
|[WatchForThreadStep](../../../extensibility/debugger/reference/idebugengineprogram2-watchforthreadstep.md)|실행 (또는 실행에 대 한 감시 중지)에 대 한 감시 지정한 스레드에서 발생 합니다.|  
|[WatchForExpressionEvaluationOnThread](../../../extensibility/debugger/reference/idebugengineprogram2-watchforexpressionevaluationonthread.md)|허용 (하거나 허용 하지 않는) 프로그램이 중지 하는 경우에 지정한 스레드에서 발생 되는 식 계산 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스에 대 한 응답에서을 호출 하는 visual Studio는 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 이벤트 프로그램의 "감시에 대 한 스레드 단계" 및 "조사식 스레드에 대 한 식 평가에서" 상태를 설정할 수 있습니다. [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) 때마다 라고 프로그램 중지 된 것 이며이 방법을 모든 스레드를 종료 하는 프로그램을 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)