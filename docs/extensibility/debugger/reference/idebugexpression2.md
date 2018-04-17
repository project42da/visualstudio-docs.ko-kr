---
title: IDebugExpression2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugExpression2
helpviewer_keywords:
- IDebugExpression2 interface
ms.assetid: f5e4b124-1e30-47c8-a511-80084a02dba5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8cd5dcce6f81e8f61f13cc09dffb460449b0deae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugexpression2"></a>IDebugExpression2
이 인터페이스는 바인딩 및 평가 대 한 구문 분석 된 식 준비를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugExpression2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE)은 평가 준비가 된 구문 분석 된 식 나타내기 위해이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 호출 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 이 인터페이스를 반환 합니다. [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) 반환 된 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다. 이러한 인터페이스는 디버깅 중인 프로그램 일시 중지 된 스택 프레임은 사용할 수 있는 경우에 액세스할 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugExpression2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)|이 식을 비동기적으로 평가합니다.|  
|[중단](../../../extensibility/debugger/reference/idebugexpression2-abort.md)|비동기 식 계산을 끝냅니다.|  
|[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)|이 식을 동기적으로 평가합니다.|  
  
## <a name="remarks"></a>설명  
 프로그램이 중지 세션 디버그 관리자 (SDM) 스택 프레임에서에서 얻습니다을 호출 하 여 DE [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)합니다. 다음은 SDM를 호출 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) 가져오려는 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다. 호출 하 여 다음 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 만들려는 `IDebugExpression2` 구문 분석된 된 식 평가 준비가 나타내는 인터페이스입니다.  
  
 SDM 호출 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 또는 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 실제로 식을 평가 하는 값을 생성 합니다.  
  
 구현에서 `IDebugExpressionContext2::ParseText`는 DE COM의를 사용 하 여 `CoCreateInstance` 함수는 식 계산기를 인스턴스화하고 가져오기는 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md) 인터페이스 (의 예제를 참조는 `IDebugExpressionEvaluator` 인터페이스). 그런 다음 호출 하는 DE [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 얻으려고는 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) 인터페이스입니다. 이 인터페이스의 구현에 사용 된 `IDebugExpression2::EvaluateSync` 및 `IDebugExpression2::EvaluateAsync` 평가를 수행 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetExpression](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md)