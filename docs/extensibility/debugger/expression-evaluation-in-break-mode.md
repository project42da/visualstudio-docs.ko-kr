---
title: "중단 모드에 있는 식 계산 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "중단 모드에서는 식 계산"
  - "디버깅 [디버깅 SDK], 식 계산"
  - "식 계산, 중단 모드"
ms.assetid: 34fe5b58-15d5-4387-a266-72120f90a4b6
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 중단 모드에 있는 식 계산
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 디버거가 중단 모드에 있는 및 식 평가 수행 해야 하는 경우에 발생 하는 프로세스를 설명 합니다.  
  
## 식 평가 과정  
 다음 표현식을 평가에 관련 된 기본 단계입니다.  
  
1.  호출 세션이 디버그 매니저 \(SDM\)  [IDebugStackFrame2::GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) 식 컨텍스트 인터페이스를 얻을 수 [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md).  
  
2.  SDM은 다음 호출  [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 과 구문 분석할 문자열입니다.  
  
3.  ParseText S\_OK를 반환 하지 않는 경우에 오류의 원인을 반환 됩니다.  
  
     \-그렇지 않은 경우\-  
  
     ParseText S\_OK를 반환 하지 않으면 해당 SDM 다음 하나 호출할 수 있습니다  [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 또는  [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 최종 값의 구문 분석 된 식을 얻을 수 있습니다.  
  
    -   사용 하 여 경우에 `IDebugExpression2::EvaluateSync`, 지정 된 콜백 인터페이스 평가 진행 중인 프로세스를 통신에 사용 됩니다.  마지막 값이 반환 되는  [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스입니다.  
  
    -   사용 하 여 경우에 `IDebugExpression2::EvaluateAsync`, 지정 된 콜백 인터페이스 평가 진행 중인 프로세스를 통신에 사용 됩니다.  Evaluateasync는 실행이 완료 되 면 보내는  [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) 통해 콜백 인터페이스입니다.  이 이벤트가 인터페이스와 함께 최종 값 얻을 수 있습니다 [GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md).  
  
## 참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)