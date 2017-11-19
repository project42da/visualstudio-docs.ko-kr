---
title: IDebugEngine2::ContinueFromSynchronousEvent | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine2::ContinueFromSynchronousEvent
helpviewer_keywords: IDebugEngine2::ContinueFromSynchronousEvent
ms.assetid: 9a57dfcd-df8e-4be5-b1fe-bd853e3c6bb2
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cb28083d62ad200152cac0b49f99a06a693f34dd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugengine2continuefromsynchronousevent"></a>IDebugEngine2::ContinueFromSynchronousEvent
세션 디버그 관리자 (SDM) 디버그 엔진 (DE)은 SDM 이전에 보낸 동기 디버그 이벤트를 수신 되어 처리를 나타내기 위해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ContinueFromSynchronousEvent(   
   IDebugEvent2* pEvent  
);  
```  
  
```csharp  
HRESULT ContinueFromSynchronousEvent(   
   IDebugEvent2 pEvent  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pEvent`  
 [in] [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 입니다 디버거가 이제 계속 이전에 보낸된 동기 이벤트를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 DE가 나타내는 이벤트의 소스 했는지 확인 해야 합니다는 `pEvent` 매개 변수입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 간단한에이 메서드를 구현 하는 방법을 보여 줍니다 `CEngine` 구현 하는 개체는 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 인터페이스입니다.  
  
```cpp  
HRESULT CEngine::ContinueFromSynchronousEvent(IDebugEvent2* pEvent)  
{  
   HRESULT hr;  
  
   // Create a pointer to a unique event interface defined for batch file  
   // breaks.    
   IAmABatchFileEvent *pBatEvent;  
   // Check for successful query for the unique batch file event  
   // interface.  
   if (SUCCEEDED(pEvent->QueryInterface(IID_IAmABatchFileEvent,  
                                       (void **)&pBatEvent)))  
   {  
      // Release the result of the QI.  
      pBatEvent->Release();  
      // Check thread message for notification to continue.  
      if (PostThreadMessage(GetCurrentThreadId(),  
                            WM_CONTINUE_SYNC_EVENT,  
                            0,  
                            0))  
      {    
         hr = S_OK;  
      }  
      else  
      {  
         hr = HRESULT_FROM_WIN32(GetLastError());  
      }  
   }  
   else  
   {  
      hr = E_INVALIDARG;  
   }  
   return hr;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)