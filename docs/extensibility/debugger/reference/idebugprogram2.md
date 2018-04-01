---
title: IDebugProgram2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgram2
helpviewer_keywords:
- IDebugProgram2 interface
ms.assetid: 8d73df73-cfff-4b8b-b426-d6051edb1939
caps.latest.revision: 18
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7f02d099fe680006966219bb626e17bc7a7114b2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2"></a>IDebugProgram2
이 인터페이스는 프로세스에서 실행 되는 프로그램을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProgram2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 및 사용자 지정 포트 공급자는 프로세스에는 프로그램을 나타내며이 인터페이스를 구현 합니다. 세션 디버그 관리자 (SDM)도 정보를 제공 하려면이 인터페이스를 구현 [연결](../../../extensibility/debugger/reference/idebugprogram2-attach.md)합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 이벤트 새 프로그램에 대해이 인터페이스를 반환 합니다. 이 인터페이스는 여러 인터페이스에 있는 많은 메서드의 매개 변수도도 사용 됩니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugProgram2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)|이 프로그램에서 실행 되는 스레드를 열거 합니다.|  
|[GetName](../../../extensibility/debugger/reference/idebugprogram2-getname.md)|프로그램의 이름을 가져옵니다.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugprogram2-getprocess.md)|이 프로그램에서 실행 중인 프로세스를 가져옵니다.|  
|[종료](../../../extensibility/debugger/reference/idebugprogram2-terminate.md)|이 프로그램을 종료합니다.|  
|[Attach](../../../extensibility/debugger/reference/idebugprogram2-attach.md)|이 프로그램에 연결합니다.|  
|[CanDetach](../../../extensibility/debugger/reference/idebugprogram2-candetach.md)|디버그 엔진 (DE) 프로그램에서 분리 하는 경우를 결정 합니다.|  
|[Detach](../../../extensibility/debugger/reference/idebugprogram2-detach.md)|이 프로그램에서 디버거를 분리 합니다.|  
|[GetProgramId](../../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)|이 프로그램에 대 한 전역 고유 식별자를 가져옵니다.|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugprogram2-getdebugproperty.md)|가져옵니다 속성을 프로그래밍합니다.|  
|[실행](../../../extensibility/debugger/reference/idebugprogram2-execute.md)|중지 된 상태에서이 프로그램을 실행을 계속 합니다. 모든 이전 실행 상태가 지워집니다.|  
|[Continue](../../../extensibility/debugger/reference/idebugprogram2-continue.md)|중지 된 상태에서이 프로그램을 실행을 계속 합니다. 모든 이전 실행 상태로 유지 됩니다.|  
|[Step](../../../extensibility/debugger/reference/idebugprogram2-step.md)|단계를 수행합니다.|  
|[CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)|이 프로그램에서 다음 실행을 중지 하는 요청 시간 스레드 실행 코드 중 하나입니다.|  
|[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md)|이름 및이 프로그램을 실행 하는 디버그 엔진 (DE)의 식별자를 가져옵니다.|  
|[EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)|소스 파일에서 지정된 된 위치에 대 한 코드 컨텍스트를 열거합니다.|  
|[GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md)|이 프로그램에 대 한 메모리 바이트 수를 가져옵니다.|  
|[GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)|이 프로그램 또는이 프로그램의 일부에 대 한 디스어셈블리 스트림을 가져옵니다.|  
|[EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)|이 프로그램을 로드 하 고 실행 되는 모듈을 열거 합니다.|  
|[GetENCUpdate](../../../extensibility/debugger/reference/idebugprogram2-getencupdate.md)|이 프로그램에 대 한 편집 하며 계속 (ENC) 업데이트를 가져옵니다.<br /><br /> 사용자 지정 디버그 엔진이이 메서드를 구현 하지 않습니다 (항상 반환 해야 `E_NOTIMPL`).|  
|[EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)|이 프로그램의 코드 경로 열거합니다.|  
|[WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md)|덤프 파일에 씁니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="remarks"></a>설명  
 프로그램은 하나 이상의 프로그램 구성 된 프로세스 동안 사용 하는 특정 런타임 아키텍처에서 실행 중인 스레드 컨테이너.  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)   
 [다음](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)