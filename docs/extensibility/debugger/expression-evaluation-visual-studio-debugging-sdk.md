---
title: "식 계산 (Visual Studio 디버깅 SDK) | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK], 식 계산"
  - "식 계산"
ms.assetid: 5044ced5-c18c-4534-b0bf-cc3e50cd57ac
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# 식 계산 (Visual Studio 디버깅 SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

IDE 중단 모드에서 프로그램을 여러 개의 변수가 포함 된 단순한 식을 평가할 수 있어야 합니다.  이 작업을 수행 하려면 디버그 엔진 \(DE\) 구문 분석 하 고 IDE 창을 한 개에 입력 되는 식을 계산할 수 있어야 합니다.  
  
 식을 사용 하 여 만들는  [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 메서드는 표현으로 그 결과  [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 인터페이스입니다.  
  
 **IDebugExpression2** DE 및 호출에서 인터페이스가 구현 되는  **EvalAsync** 반환 하는 메서드는  [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) IDE에서 식 계산의 결과 표시 하려면 ide 인터페이스.  [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 조사식 창, 지역 창에 식의 값을 저장 하는 데 사용 하는 구조를 반환 합니다.  
  
 디버그 세션 또는 패키지 디버그 관리자 \(SDM\)를 호출  [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 또는  [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 얻을 수 있는  [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 평가의 결과 나타내는 인터페이스입니다.  `IDebugProperty2`이름, 형식 및 식의 값을 반환 하는 메서드가 있습니다.  이 정보는 다양 한 디버거 창에 표시 됩니다.  
  
## 식 계산을 사용 하 여  
 식 계산을 사용 하 여 구현 해야는  [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 메서드 및 메서드를 모두의  [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 인터페이스에 다음 표에 나와 있는 것 처럼.  
  
|메서드|설명|  
|---------|--------|  
|[EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)|식이 비동기적으로 계산 될 수 있습니다.|  
|[Abort](../../extensibility/debugger/reference/idebugexpression2-abort.md)|비동기 식 계산이 종료 됩니다.|  
|[EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)|식이 동기적으로 계산 될 수 있습니다.|  
  
 동기 및 비동기 계산의 구현이 필요는  [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 방법입니다.  비동기 식 계산의 구현에 필요한  [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md).  
  
## 참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)