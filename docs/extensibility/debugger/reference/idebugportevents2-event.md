---
title: IDebugPortEvents2::Event | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortEvents2::Event
helpviewer_keywords: IDebugPortEvents2::Event
ms.assetid: 5cc813f7-04a1-4462-9ea7-fbddcf0e0143
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6713e8a85f9d4078a920be023438307146cbafdb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportevents2event"></a>IDebugPortEvents2::Event
이 메서드는 생성 및 소멸 프로세스 및 포트에서 프로그램의 발생을 나타내는 이벤트를 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Event(  
   IDebugCoreServer2* pServer,  
   IDebugPort2*       pPort,  
   IDebugProcess2*    pProcess,  
   IDebugProgram2*    pProgram,  
   IDebugEvent2*      pEvent,  
   REFIID             riidEvent  
);  
```  
  
```csharp  
int Event(  
   IDebugCoreServer2 pServer,   
   IDebugPort2       pPort,   
   IDebugProcess2    pProcess,   
   IDebugProgram2    pProgram,   
   IDebugEvent2      pEvent,   
   ref Guid          riidEvent  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pMachine`  
 [in] [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) 디버그 서버를 나타내는 개체 (의 모든 인스턴스에 대해 하나씩 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)])에서 이벤트가 발생 합니다.  
  
 `pPort`  
 [in] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 이벤트가 발생 한 포트를 나타내는 개체입니다.  
  
 `pProcess`  
 [in] [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 이벤트가 발생 한 프로세스를 나타내는 개체입니다.  
  
 `pProgram`  
 [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 이벤트가 발생 한 프로그램을 나타내는 개체입니다.  
  
 `pEvent`  
 [in] [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이벤트를 식별 하는 개체입니다. 가능한 이벤트는 다음과 같습니다.  
  
-   [IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)  
  
-   [IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)  
  
-   [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
  
-   [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)  
  
 `riidEvent`  
 [in] 이벤트의 GUID입니다. 이벤트로 캐스팅 하기 때문에 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 메서드를 호출 하기 전에이 식별자를 사용 하면 더 쉽게 전송 되는 이벤트를 확인할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)