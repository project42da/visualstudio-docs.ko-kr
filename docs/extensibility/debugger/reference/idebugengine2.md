---
title: IDebugEngine2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine2
helpviewer_keywords:
- IDebugEngine2 interface
ms.assetid: 1f0e9ac0-6dfb-461a-976c-888d82144cdb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e2cfe7e2f54b45ecfe8fdb34943b87818a13feab
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugengine2"></a>IDebugEngine2
이 인터페이스는 디버그 엔진을 (DE)를 나타냅니다. 중단점을 설정 하 고 예외를 지우기 만들지는 디버깅 세션의 다양 한 측면을 관리 하는 데 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugEngine2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스는 사용자 지정 DE 프로그램의 디버깅을 관리 하 여 구현 됩니다. 이 인터페이스는 DE 하 여 구현 되어야 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스는 세션 디버그 관리자 (SDM) 예외 관리 중단점을 만들고는 DE에서 전송 된 동기 이벤트에 응답을 포함 하 여 디버깅 세션을 관리 하에서 호출 됩니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugEngine2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)|DE로 디버깅 중인 모든 프로그램에 대 한 열거자를 만듭니다.|  
|[Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)|DE 프로그램에 연결합니다.|  
|[CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)|DE에 보류 중인 중단점을 만듭니다.|  
|[SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)|DE 주어진된 예외를 처리 하는 방법을 지정 합니다.|  
|[RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)|지정된 된 예외를 제거 하 여 디버그 엔진에서 더 이상 처리 합니다.|  
|[RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md)|예외는 IDE가 특정 런타임 아키텍처 나 언어에 대 한 설정 목록을 제거 합니다.|  
|[GetEngineID](../../../extensibility/debugger/reference/idebugengine2-getengineid.md)|DE의 GUID를 가져옵니다.|  
|[DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)|지정 된 프로그램 예외적인 종료 하 고는 DE 프로그램에 대 한 모든 참조를 정리 하 고 프로그램 보내기 해야 하는 DE 삭제 이벤트를 알립니다.|  
|[ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)|DE SDM, 이전에 보낸 동기 디버그 이벤트를 수신 되어 처리를 나타내기 위해 SDM에서 호출 됩니다.|  
|[SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)|DE 로캘을 설정합니다.|  
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugengine2-setregistryroot.md)|현재 사용 하는 DE 레지스트리 루트를 설정합니다.|  
|[SetMetric](../../../extensibility/debugger/reference/idebugengine2-setmetric.md)|메트릭을 설정합니다.|  
|[CauseBreak](../../../extensibility/debugger/reference/idebugengine2-causebreak.md)|요청을이 DE로 디버깅 중인 모든 프로그램의 스레드 중 하나를 실행 하려고 시도 다음에 실행을 중지 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [GetEngine](../../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)