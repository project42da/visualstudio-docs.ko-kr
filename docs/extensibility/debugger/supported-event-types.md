---
title: "지원 되는 이벤트 유형 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 이벤트를 지원"
ms.assetid: a3c0386d-551e-4734-9a0c-368d1c2e6671
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 지원 되는 이벤트 유형
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

현재 Visual Studio 디버깅 다음과 같은 이벤트 유형을 지원합니다.  
  
-   비동기 이벤트  
  
     세션 디버그 매니저 \(SDM\)에 게 알리는 및 디버깅 되는 응용 프로그램의 상태를 변경 하 고 IDE.  이러한 이벤트는 SDM 및 IDE의 레저에 처리 됩니다.  이벤트를 처리 하면 디버그 엔진 \(DE\)에 응답이 보내집니다.  [IDebugOutputStringEvent2](../../extensibility/debugger/reference/idebugoutputstringevent2.md) 및 [IDebugMessageEvent2](../../extensibility/debugger/reference/idebugmessageevent2.md) 인터페이스 비동기 이벤트의 예입니다.  
  
-   동기화 이벤트  
  
     SDM와 디버깅 되는 응용 프로그램의 상태를 변경 하 고 IDE에 알립니다.  응답으로 전송 됩니다 이러한 이벤트와 비동기 이벤트 간의 유일한 차이점 되는 [ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) 메서드.  
  
     동기화 이벤트를 보내는 계속 IDE 받고 이벤트를 처리 한 후 처리 하 여 DE 해야 하는 경우에 유용 합니다.  
  
-   동기적 이벤트를 중지 하거나 이벤트 중지  
  
     디버깅 되는 응용 프로그램 코드 실행을 중지 한 것은 SDM 및 IDE를 알립니다.  해당 메서드를 사용 하 여 중지 이벤트를 보낼 때 [이벤트](../../extensibility/debugger/reference/idebugeventcallback2-event.md), the [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) 매개 변수는 필수입니다.  중지 이벤트를 호출 하 여 다음 방법 중 하나 계속 됩니다.  
  
    -   [실행](../../extensibility/debugger/reference/idebugprogram2-execute.md)  
  
    -   [단계](../../extensibility/debugger/reference/idebugprogram2-step.md)  
  
    -   [계속](../../extensibility/debugger/reference/idebugprogram2-continue.md)  
  
     인터페이스 [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) 및 [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) 중지 이벤트의 예입니다.  
  
    > [!NOTE]
    >  비동기 중단 이벤트가 지원 되지 않습니다.  비동기 중지 이벤트를 보낼 수 없습니다.  
  
## 토론  
 이벤트의 실제 구현에 DE의 디자인에 따라 달라 집니다.  보낸 각 이벤트 유형의 DE를 디자인 하는 설정의 특성에 따라 결정 됩니다.  예를 들어, 하나의 DE를 보낼 수 있습니다는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 다른 중지 이벤트로 보낼 수도 있습니다 하는 동안 비동기 이벤트로.  
  
 다음 표에서 어떤 프로그램 및 스레드 매개 변수 필요한 어떤 이벤트에 대 한 이벤트 형식이 기본으로 지정 합니다.  이벤트 동기화 될 수 있습니다.  없음 이벤트 동기 수 있어야 합니다.  
  
> [!NOTE]
>  [IDebugEngine2](../../extensibility/debugger/reference/idebugengine2.md) 모든 이벤트에 대 한 인터페이스가 필요 합니다.  
  
|Event|IDebugProgram2|IDebugThread2|이벤트 중지|  
|-----------|--------------------|-------------------|------------|  
|[IDebugActivateDocumentEvent2](../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|아니요|  
|[IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md)|필수|필수|예|  
|[IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|아니요|  
|[IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|아니요|  
|[IDebugBreakpointUnboundEvent2](../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|아니요|  
|[IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md)|필수|필수|예|  
|[IDebugCanStopEvent2](../../extensibility/debugger/reference/idebugcanstopevent2.md)|필수|필수|아니요|  
|[IDebugDocumentTextEvents2](../../extensibility/debugger/reference/idebugdocumenttextevents2.md)|허용되지 않음|허용되지 않음|아니요|  
|[IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md)|허용되지 않음|허용되지 않음|아니요|  
|[IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md)|필수|필수|예|  
|[IDebugErrorEvent2](../../extensibility/debugger/reference/idebugerrorevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|이 될 수 있습니다.|  
|[IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md)|필수|필수|예|  
|[IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|이 될 수 있습니다.|  
|[IDebugInterceptExceptionCompleteEvent2](../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)|필수|필수|예|  
|[IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md)|필수|필수|예|  
|[IDebugMessageEvent2](../../extensibility/debugger/reference/idebugmessageevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|이 될 수 있습니다.|  
|[IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md)|필수|허용, 필요 하지 않음|아니요|  
|[IDebugOutputStringEvent2](../../extensibility/debugger/reference/idebugoutputstringevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|아니요|  
|[IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)|필수|허용, 필요 하지 않음|아니요|  
|[IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)|필수|허용, 필요 하지 않음|아니요|  
|[IDebugPropertyCreateEvent2](../../extensibility/debugger/reference/idebugpropertycreateevent2.md)|필수|허용, 필요 하지 않음|아니요|  
|[IDebugPropertyDestroyEvent2](../../extensibility/debugger/reference/idebugpropertydestroyevent2.md)|필수|허용, 필요 하지 않음|아니요|  
|[IDebugReturnValueEvent2](../../extensibility/debugger/reference/idebugreturnvalueevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|아니요|  
|IDebugStopCompleteEvent2|필수|필수|예|  
|[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md)|필수|필수|예|  
|[IDebugSymbolSearchEvent2](../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|아니요|  
|[IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md)|필수|필수|아니요|  
|[IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)|필수|필수|아니요|  
|[IDebugThreadNameChangedEvent2](../../extensibility/debugger/reference/idebugthreadnamechangedevent2.md)|허용, 필요 하지 않음|허용, 필요 하지 않음|아니요|  
  
## 참고 항목  
 [이벤트 전송](../../extensibility/debugger/sending-events.md)