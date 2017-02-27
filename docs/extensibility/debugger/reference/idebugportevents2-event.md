---
title: "IDebugPortEvents2::Event | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortEvents2::Event"
helpviewer_keywords: 
  - "IDebugPortEvents2::Event"
ms.assetid: 5cc813f7-04a1-4462-9ea7-fbddcf0e0143
caps.latest.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 18
---
# IDebugPortEvents2::Event
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 생성 및 폐기 하는 프로세스 및 프로그램에서 포트를 지정 하는 이벤트를 보냅니다.  
  
## 구문  
  
```cpp#  
HRESULT Event(  
   IDebugCoreServer2* pServer,  
   IDebugPort2*       pPort,  
   IDebugProcess2*    pProcess,  
   IDebugProgram2*    pProgram,  
   IDebugEvent2*      pEvent,  
   REFIID             riidEvent  
);  
```  
  
```c#  
int Event(  
   IDebugCoreServer2 pServer,   
   IDebugPort2       pPort,   
   IDebugProcess2    pProcess,   
   IDebugProgram2    pProgram,   
   IDebugEvent2      pEvent,   
   ref Guid          riidEvent  
);  
```  
  
#### 매개 변수  
 `pMachine`  
 \[in\] [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) 디버그 서버를 나타내는 개체 \(의 모든 인스턴스에 대해 하나의 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]\)에 이벤트가 발생 합니다.  
  
 `pPort`  
 \[in\] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 는 이벤트가 발생 하는 포트를 나타내는 개체입니다.  
  
 `pProcess`  
 \[in\] [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 에서 이벤트가 발생 한 프로세스를 나타내는 개체입니다.  
  
 `pProgram`  
 \[in\] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 에서 이벤트가 발생 하는 프로그램을 나타내는 개체입니다.  
  
 `pEvent`  
 \[in\] [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 는 이벤트를 식별 하는 개체입니다.  발생할 수 있는 이벤트는 다음과 같습니다.  
  
-   [IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)  
  
-   [IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)  
  
-   [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
  
-   [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)  
  
 `riidEvent`  
 \[in\] 이벤트의 GUID입니다.  이벤트에 캐스팅 되어 있기 때문에 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 메서드를 호출 하기 전에이 식별자는 이벤트를 보낸 확인 하기 쉽습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)