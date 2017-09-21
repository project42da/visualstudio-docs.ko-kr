---
title: "IDebugProgramNode2::Attach_V7 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramNode2::Attach"
helpviewer_keywords: 
  - "IDebugProgramNode2::Attach_V7"
  - "IDebugProgramNode2::Attach"
ms.assetid: b5ffc736-efc7-4ca8-964d-5536ff891b0e
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugProgramNode2::Attach_V7
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용 되지 않습니다.  사용 하지 않습니다.  
  
## 구문  
  
```cpp#  
HRESULT Attach_V7 (   
   IDebugProgram2*       pMDMProgram,  
   IDebugEventCallback2* pCallback,  
   DWORD                 dwReason  
);  
```  
  
```c#  
int Attach_V7 (   
   IDebugProgram2       pMDMProgram,  
   IDebugEventCallback2 pCallback,  
   uint                 dwReason  
);  
```  
  
#### 매개 변수  
 `pMDMProgram`  
 \[in\] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 프로그램 연결을 나타내는 인터페이스입니다.  
  
 `pCallback`  
 \[in\] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 인터페이스는 SDM을 디버그 이벤트를 보내는 데 사용할 수 있습니다.  
  
 `dwReason`  
 \[in\] 값은 [ATTACH\_REASON](../../../extensibility/debugger/reference/attach-reason.md) 연결 하는 이유를 지정 하는 열거형입니다.  
  
## 반환 값  
 구현은 항상 반환 해야 `E_NOTIMPL`.  
  
## 설명  
  
> [!WARNING]
>  로 [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)]에서이 메서드는 더 이상 사용 되며 항상 반환 해야 `E_NOTIMPL`.  참조는 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md) 프로그램 노드는 첨부할 수 없습니다 수 표시 되어야 하거나 프로그램 노드 프로그램 간단 하 게 설정 하는 것에 대 한 대안은 인터페이스 `GUID`. 그렇지 않으면, 구현에서 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드.  
  
## 이전에 Visual Studio 2005  
 이 메서드는만 DE는 디버깅 중인 프로그램의 주소 공간에서 실행 하는 경우에 구현 해야 합니다.  그렇지 않은 경우이 메서드를 반환 합니다 `S_FALSE`.  
  
 이 메서드를 호출 하는 경우는 DE 보내야 합니다는 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md) 이 이미의이 인스턴스에 대 한 전송 되지 않았습니다 경우 이벤트 객체는 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 인터페이스를으로 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 및 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 이벤트 개체입니다.  [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) 이벤트 개체 다음 전송 하는 경우는 `dwReason` 매개 변수가 `ATTACH_REASON_LAUNCH`.  
  
 DE를 호출 해야는 [GetProgramId](../../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) 메서드를는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 가 제공 하는 개체는 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 이벤트 개체 및 해당 프로그램의 GUID의 인스턴스 데이터를 저장 해야는 `IDebugProgram2` DE에서 구현 하는 개체입니다.  
  
## 참고 항목  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)   
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)   
 [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)   
 [ATTACH\_REASON](../../../extensibility/debugger/reference/attach-reason.md)