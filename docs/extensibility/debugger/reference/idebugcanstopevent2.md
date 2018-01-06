---
title: IDebugCanStopEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCanStopEvent2
helpviewer_keywords: IDebugBreakpointRequest2 interface
ms.assetid: 784bd5b1-4a3f-4455-b313-c4c9a82555a5
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 59e601e828fd3dad1487925c649972efc7b019a9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcanstopevent2"></a>IDebugCanStopEvent2
이 인터페이스는 세션 디버그 관리자 (SDM) 현재 코드 위치에서 중지를 요청 하 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugCanStopEvent2 : IUknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 소스 코드를 단계별로이 인터페이스를 구현 합니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다 (은 SDM 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 액세스로는 `IDebugEvent2` 인터페이스).  
  
 이 인터페이스의 구현을의 SDM의 전화 통신 해야 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) 디버그 엔진에 있습니다. 예를 들어 스레드를 처리 하는 디버그 엔진의 메시지에 게시 된 메시지와 함께이 작업을 수행할 수 있습니다 또는이 인터페이스를 구현 하는 개체의 디버그 엔진에 대 한 참조을로 전달 된 플래그로 디버그 엔진으로 다시 호출할 수 `IDebugCanStopEvent2::CanStop`합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 메서드는 DE는 DE 및 실행을 계속 하도록 요청 될 때마다가 코드를 단계별로 DE 보낼 수 있습니다. 이 이벤트를 사용 하 여 보냅니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 은 SDM 디버깅 중인 프로그램에는 연결 된 경우 제공한 콜백 함수입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugCanStopEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)|이 이벤트에 대 한 이유를 가져옵니다.|  
|[CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)|디버깅 중인 프로그램이 이벤트 (및 송신 중지에 대 한 이유를 설명 하는 이벤트)의 위치에서 중지 하거나 계속 실행 해야 하는지 여부를 지정 합니다.|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)|이 이벤트의 위치를 설명 하는 문서 컨텍스트를 가져옵니다.|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)|이 이벤트의 위치를 설명 하는 코드 컨텍스트를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 DE 함수와 DE에 사용자 단계 찾습니다 디버깅 정보가 없는 또는 디버그 정보가 있지만 DE 모르는 소스 코드가 해당 위치에 대해 표시 될 수 있습니다 하는 경우이 인터페이스를 전송 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStepCompleteEvent2](../../../extensibility/debugger/reference/idebugstepcompleteevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)