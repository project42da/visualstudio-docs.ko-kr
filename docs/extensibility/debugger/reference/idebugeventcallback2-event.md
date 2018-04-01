---
title: IDebugEventCallback2::Event | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEventCallback2::Event
helpviewer_keywords:
- IDebugEventCallback2::Event
ms.assetid: e5a3345b-d460-4e40-8f5b-3111c56a2ed9
caps.latest.revision: 10
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0a7e5d4d20ae7e4409599a77250986b759f152fb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugeventcallback2event"></a>IDebugEventCallback2::Event
디버그 이벤트의 알림을 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Event(   
   IDebugEngine2*  pEngine,  
   IDebugProcess2* pProcess,  
   IDebugProgram2* pProgram,  
   IDebugThread2*  pThread,  
   IDebugEvent2*   pEvent,  
   REFIID          riidEvent,  
   DWORD           dwAttrib  
);  
```  
  
```csharp  
int Event(   
   IDebugEngine2  pEngine,  
   IDebugProcess2 pProcess,  
   IDebugProgram2 pProgram,  
   IDebugThread2  pThread,  
   IDebugEvent2   pEvent,  
   ref Guid       riidEvent,  
   uint           dwAttrib  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pEngine`  
 [in] [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 이 이벤트를 전송 하는 디버그 엔진 (DE)을 나타내는 개체입니다. 이 매개 변수를 채울는 DE 필요 합니다.  
  
 `pProcess`  
 [in] [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 이벤트가 발생 하는 프로세스를 나타내는 개체입니다. 이 매개 변수는 세션 디버그 관리자 (SDM) 채워집니다. DE는 항상이 매개 변수에 대해 null 값을 전달합니다.  
  
 `pProgram`  
 [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 이 이벤트가 발생 하는 프로그램을 나타내는 개체입니다. 대부분의 이벤트에 대 한이 매개 변수가 아닌 경우 null 값  
  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 이 이벤트가 발생 하는 스레드를 나타내는 개체입니다. 중지 이벤트에 대 한이 매개 변수 스택 프레임은이 매개 변수에서 가져온 대로 null 값이 될 수 없습니다.  
  
 `pEvent`  
 [in] [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 디버그 이벤트를 나타내는 개체입니다.  
  
 `riidEvent`  
 [in] 얻을 수는 이벤트 인터페이스를 식별 하는 GUID는 `pEvent` 매개 변수입니다.  
  
 `dwAttrib`  
 [in] 플래그의 조합 된 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md) 열거 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출 하는 경우는 `dwAttrib` 매개 변수에서 반환 된 값을 일치 해야 합니다는 [GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md) 이벤트 개체에서 호출할 때 메서드에 전달 된는 `pEvent` 매개 변수입니다.  
  
 모든 디버그 이벤트는 이벤트 자체 비동기 인지 여부에 관계 없이 비동기적으로 게시 됩니다. DE이이 메서드를 호출할 때 반환 값 나타내지 않습니다 이벤트가 처리 되었는지 여부, 이벤트 수신 되었는지 여부를만. 실제로 대부분의 경우 이벤트 처리 되지 않았습니다이 메서드가 반환 될 때입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)