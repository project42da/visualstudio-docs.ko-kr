---
title: "컨트롤 이벤트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK] 이벤트"
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# 컨트롤 이벤트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

제어 프로그램 실행 중에 이벤트를 보내야 합니다.  이벤트를 모두 사용 하 여 보낸는  [IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md) 인터페이스와 구현 해야 하는 특성을 갖는  [IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md) 메서드.  
  
## 추가 방법  
 일부 이벤트가 구현 하는 추가 메서드는 다음과 같이 필요합니다.  
  
-   보내기는  [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) \(DE\) 디버그 엔진을 초기화 하면 인터페이스 요구를 구현 하는  [IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md) 메서드.  
  
-   실행 제어 필요와 같은 컨트롤 이벤트가 구현에서  [IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md) 및[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 인터페이스입니다.  **IDebugBreakEvent2** 위한 비동기 분리 해야 합니다.  
  
-   함수를 한 단계씩 실행의 구현에 필요한의  [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 인터페이스와 해당 메서드.  
  
 중단점에서 파생 되는 이벤트의 구현이 필요로  [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md),  [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), 및  [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) 인터페이스,으로  [IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) 및  [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) 방법입니다.  
  
 비동기 식 계산이 필요한 구현 하는  [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) 인터페이스 및 해당  [IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md)[및 GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) 방법.  
  
 동기 이벤트 요구 구현 하는  [IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) 메서드.  
  
 스타일 문자열 출력을 쓰는 데에 엔진을 구현 해야는  [IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md) 메서드가 있습니다.  
  
## 참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)