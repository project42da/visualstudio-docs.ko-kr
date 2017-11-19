---
title: "중단 모드에 있는 식 계산 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- break mode, expression evaluation
- debugging [Debugging SDK], expression evaluation
- expression evaluation, break mode
ms.assetid: 34fe5b58-15d5-4387-a266-72120f90a4b6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 766f00475971da1ca009737f9360952422177814
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="expression-evaluation-in-break-mode"></a>중단 모드에 있는 식 계산
다음 디버거가 중단 모드에 있는 식 평가 수행 해야 하는 경우 발생 하는 프로세스를 설명 합니다.  
  
## <a name="expression-evaluation-process"></a>식 평가 프로세스  
 다음은 식을 평가 하 여 위한 기본 단계입니다.  
  
1.  세션 디버그 관리자 (SDM) 호출 하면 중지 [IDebugStackFrame2::GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) 식 컨텍스트 인터페이스를 가져오지 [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md)합니다.  
  
2.  다음은 SDM를 호출 [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 구문 분석할 문자열을 사용 합니다.  
  
3.  ParseText S_OK를 반환 하지 않으면 오류 이유로 반환 됩니다.  
  
     -그렇지 않은 경우-  
  
     ParseText에서 S_OK를 반환 하는 경우는 SDM 다음 호출 [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 또는 [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 최종 값을 구문 분석 된 식에서 가져올 수 있습니다.  
  
    -   사용 하는 경우 `IDebugExpression2::EvaluateSync`, 지정 된 콜백 인터페이스 평가 하는 지속적인 프로세스를 통신에 사용 됩니다. 최종 값이 반환 되는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스입니다.  
  
    -   사용 하는 경우 `IDebugExpression2::EvaluateAsync`, 지정 된 콜백 인터페이스 평가 하는 지속적인 프로세스를 통신에 사용 됩니다. 평가가 완료 되 면 EvaluateAsync 보냅니다는 [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) 콜백을 통해 인터페이스입니다. 이 이벤트 인터페이스와 최종 값 수를 얻을 수 [GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)