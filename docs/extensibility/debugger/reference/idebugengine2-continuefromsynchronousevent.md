---
title: "IDebugEngine2::ContinueFromSynchronousEvent | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngine2::ContinueFromSynchronousEvent"
helpviewer_keywords: 
  - "IDebugEngine2::ContinueFromSynchronousEvent"
ms.assetid: 9a57dfcd-df8e-4be5-b1fe-bd853e3c6bb2
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEngine2::ContinueFromSynchronousEvent
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

세션 디버그 관리자 \(이전에 SDM을 \(DE\)는 디버그 엔진에서 보낸 동기 디버그 이벤트를 받은 처리 되었음을 나타내는 경우 SDM\)가 호출 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT ContinueFromSynchronousEvent(   
   IDebugEvent2* pEvent  
);  
```  
  
```c#  
HRESULT ContinueFromSynchronousEvent(   
   IDebugEvent2 pEvent  
);  
```  
  
#### 매개 변수  
 `pEvent`  
 \[in\] [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 을 디버거 합니다 지금 계속 이전에 보낸된 동기 이벤트를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 표시 되는 이벤트의 소스는 않았습니다 DE를 확인 해야 합니다는 `pEvent` 매개 변수.  
  
## 예제  
 다음 예제에서는 단순에이 메서드를 구현 하는 방법을 보여 줍니다. `CEngine` 를 구현 하는 개체는 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 인터페이스입니다.  
  
```cpp#  
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
  
## 참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)