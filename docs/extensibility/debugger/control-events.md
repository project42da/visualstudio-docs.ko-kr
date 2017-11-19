---
title: "이벤트를 제어할 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], events
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3220e3c6ef1a20b8a434fbfab13b419beb331032
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="control-events"></a>컨트롤 이벤트
프로그램의 제어 된 실행 하는 동안 이벤트를 전송 해야 합니다. 사용 하 여 전송 된 모든 이벤트는 [IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md) 인터페이스를 구현 해야 하는 특성이 [IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md) 메서드.  
  
## <a name="additional-methods"></a>추가 방법  
 일부 이벤트는 다음과 같은 추가 메서드의 구현이 필요합니다.  
  
-   보내기는 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 인터페이스 (DE) 디버그 엔진을 초기화 하는 경우 구현 해야는 [IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md) 메서드.  
  
-   실행 제어 등의 컨트롤 이벤트의 구현이 필요는 [IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md) 및[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 인터페이스입니다. **IDebugBreakEvent2** 비동기 나누기에만 필요 합니다.  
  
-   구현 해야 함수를 한 단계씩는 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 인터페이스 및 해당 메서드.  
  
 중단점에서 파생 된 이벤트의 구현이 필요로 [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md), [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), 및 [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) 인터페이스와 [IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) 및 [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) 메서드.  
  
 비동기 식 평가 구현 해야는 [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) 인터페이스 및 해당 [IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md) [및 GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) 메서드.  
  
 동기 이벤트 구현 되어야는 [IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) 메서드.  
  
 문자열 형식의 출력을 쓰기 위해 엔진에 대 한 구현 해야 합니다는 [IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)