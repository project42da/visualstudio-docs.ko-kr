---
title: "IDebugEventCallback2::Event | Microsoft Docs"
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
  - "IDebugEventCallback2::Event"
helpviewer_keywords: 
  - "IDebugEventCallback2::Event"
ms.assetid: e5a3345b-d460-4e40-8f5b-3111c56a2ed9
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEventCallback2::Event
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 이벤트 알림을 보냅니다.  
  
## 구문  
  
```cpp#  
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
  
```c#  
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
  
#### 매개 변수  
 `pEngine`  
 \[in\] [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 는이 이벤트를 보낼 디버그 엔진 \(DE\)을 나타내는 개체입니다.  이 매개 변수를 채우는 데는 DE 필요 합니다.  
  
 `pProcess`  
 \[in\] [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 에서 이벤트가 발생 하는 프로세스를 나타내는 개체입니다.  이 매개 변수는 세션 디버그 매니저 \(SDM\)에 의해 입력 됩니다.  DE은 항상이 매개 변수에 null 값을 전달합니다.  
  
 `pProgram`  
 \[in\] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 는이 이벤트를 발생 하는 프로그램을 나타내는 개체입니다.  대부분의 이벤트에 대 한이 매개 변수는 null 값입니다.  
  
 `pThread`  
 \[in\] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 는이 이벤트를 발생 하는 스레드를 나타내는 개체입니다.  스택 프레임에이 매개 변수에서 받은 이벤트를 중지에 대 한이 매개 변수는 null 값 수 없습니다.  
  
 `pEvent`  
 \[in\] [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 디버그 이벤트를 나타내는 개체입니다.  
  
 `riidEvent`  
 \[in\] 얻을 수 있는 이벤트 인터페이스를 식별 하는 GUID는 `pEvent` 매개 변수.  
  
 `dwAttrib`  
 \[in\] 플래그의 조합에서 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md) 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드를 호출할 때의 `dwAttrib` 매개 변수에서 반환 된 값을 일치 해야 합니다는 [GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md) 이벤트 개체에서 호출 되는 메서드에 전달 된에 `pEvent` 매개 변수.  
  
 모든 디버그 이벤트는 이벤트 비동기 인지 여부에 관계 없이 비동기적으로 게시 됩니다.  DE는이 메서드를 호출할 때만 이벤트를 받았는지 여부 반환 값 이벤트 처리 여부를 나타내지 않습니다.  사실, 대부분의 경우, 이벤트가이 메서드가 반환 될 때 처리 되지 않았습니다.  
  
## 참고 항목  
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)