---
title: IDebugExceptionEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugExceptionEvent2
helpviewer_keywords: IDebugExceptionEvent2 interface
ms.assetid: 53d32e59-a84b-4710-833e-c5ab08100516
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4aa1c643a07f15f361c77c618d717cc2655277c6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugexceptionevent2"></a>IDebugExceptionEvent2
디버그 엔진 (DE)는 현재 실행 중인 프로그램에서 예외가 throw 될 때이 인터페이스를 세션 디버그 관리자 (SDM)를 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugExceptionEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 예외가 디버깅 중인 프로그램에서 발생 했음을 보고할이 인터페이스를 구현 합니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다. SDM 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 액세스로는 `IDebugEvent2` 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 DE을 만들고 예외를 보고 하기 위해이 이벤트 개체를 보냅니다. 이벤트를 사용 하 여 보내집니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결할 때는 SDM에서 제공 되는 콜백 함수입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugExceptionEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)|이 이벤트를 발생 시킨 예외에 대 한 자세한 정보를 가져옵니다.|  
|[GetExceptionDescription](../../../extensibility/debugger/reference/idebugexceptionevent2-getexceptiondescription.md)|이 이벤트를 발생 시킨 throw 된 예외에 대 한 이해 하기 쉬운 설명을 가져옵니다.|  
|[CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)|디버그 엔진 (DE) 실행이 다시 시작 하는 경우 디버깅 중인 프로그램에이 예외를 전달 하는 옵션을 지원 여부를 결정 합니다.|  
|[PassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md)|예외를 삭제 해야 하는 경우 또는 예외 실행이 다시 시작 하는 경우 디버깅 중인 프로그램에 전달 해야 하는지 여부를 지정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="remarks"></a>설명  
 이벤트를 보내기 전에 DE 확인 하는 경우이 예외 이벤트가 지정 된 첫째 또는 둘째 예외에 대 한 이전 호출에서 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)합니다. 첫째 예외를 지정 된 경우는 `IDebugExceptionEvent2` 이벤트가 SDM로 전송 됩니다. 파일이 없으면는 DE 예외를 처리 하도록 응용 프로그램에 제공 합니다. 없는 예외 처리기가 제공 하 고 예외는 둘째 예외로 지정 된 경우는 `IDebugExceptionEvent2` 이벤트가 SDM로 전송 됩니다. 그렇지 않은 경우는 DE 프로그램의 실행을 다시 시작 하 고 운영 체제 또는 런타임 예외를 처리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)