---
title: "IDebugEngine2 | Microsoft Docs"
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
  - "IDebugEngine2"
helpviewer_keywords: 
  - "IDebugEngine2 인터페이스"
ms.assetid: 1f0e9ac0-6dfb-461a-976c-888d82144cdb
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEngine2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진을 \(DE\)를 나타냅니다.  중단점을 설정 하 고 예외를 지우는 만들기에서 디버깅 세션의 다양 한 측면을 관리할 수 있습니다.  
  
## 구문  
  
```  
IDebugEngine2 : IUnknown  
```  
  
## 구현자 참고 사항  
 이 인터페이스는 관리 프로그램을 디버깅 하는 사용자 지정 DE에서 구현 됩니다.  DE에서이 인터페이스를 구현 해야 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 세션 디버그 매니저 \(SDM\) 예외 관리, 중단점을 만들고 DE에서 보낸 동기 이벤트에 응답 하는 등 디버깅 세션을 관리 하 여.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugEngine2`.  
  
|메서드|설명|  
|---------|--------|  
|[EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)|DE로 디버깅 중인 모든 프로그램에 대 한 열거자를 만듭니다.|  
|[연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)|DE는 프로그램을 연결합니다.|  
|[CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)|DE에서 보류 중인 중단점을 만듭니다.|  
|[SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)|DE 지정한 예외 처리 하는 방법을 지정 합니다.|  
|[RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)|더 이상 디버그 엔진에서 처리 하므로 지정 된 예외를 제거 합니다.|  
|[RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md)|IDE에서 특정 런타임 아키텍처 또는 언어를 설정 하는 예외를 제거 합니다.|  
|[GetEngineID](../../../extensibility/debugger/reference/idebugengine2-getengineid.md)|DE의 GUID를 가져옵니다.|  
|[DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)|예외적인 지정한 프로그램이 종료 되었습니다 및 DE는 프로그램에 대 한 모든 참조를 제거 하 고 프로그램 보내기는 DE 삭제 이벤트를 알립니다.|  
|[ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)|이전에 SDM을 DE에서 보낸 동기 디버그 이벤트를 받은 처리 되었음을 나타내는 SDM에서 호출 됩니다.|  
|[SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)|DE의 로캘을 설정합니다.|  
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugengine2-setregistryroot.md)|레지스트리 루트는 현재 사용 하는 DE 설정합니다.|  
|[SetMetric](../../../extensibility/debugger/reference/idebugengine2-setmetric.md)|메트릭을 설정합니다.|  
|[CauseBreak](../../../extensibility/debugger/reference/idebugengine2-causebreak.md)|이 DE에서 디버깅 중인 프로그램을 모두 해당 스레드 중 하나를 실행 하려고 시도할 때 실행을 중지 하도록 요청 합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [GetEngine](../../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)