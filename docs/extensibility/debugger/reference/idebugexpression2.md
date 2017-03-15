---
title: "IDebugExpression2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpression2"
helpviewer_keywords: 
  - "IDebugExpression2 인터페이스"
ms.assetid: f5e4b124-1e30-47c8-a511-80084a02dba5
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# IDebugExpression2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 바인딩 및 평가 대 한 구문 분석 된 식을 준비를 나타냅니다.  
  
## 구문  
  
```  
IDebugExpression2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 계산 될 준비가 된 구문 분석 된 식을 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출을 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 이 인터페이스를 반환 합니다.  [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)반환은 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다.  이러한 인터페이스는 디버깅 중인 프로그램의 일시 중지 된 스택 프레임을 사용할 때에 액세스할 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugExpression2`.  
  
|메서드|설명|  
|---------|--------|  
|[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)|이 식은 비동기적으로 계산 됩니다.|  
|[중단](../../../extensibility/debugger/reference/idebugexpression2-abort.md)|비동기 식 계산이 종료 됩니다.|  
|[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)|이 식은 동기적으로 계산 됩니다.|  
  
## 설명  
 프로그램이 중단 된 경우 세션 디버그 매니저 \(SDM\) 스택 프레임에서 DE를 얻습니다 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md).  SDM은 다음 호출 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) 얻을 수 있는 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스.  이 호출 하 여 다음에 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 만들 수 있는 `IDebugExpression2` 평가 준비는 구문 분석 된 식을 나타내는 인터페이스를 합니다.  
  
 중 하나를 호출 하는 SDM [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 또는 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 실제로 식을 계산 하 고 값을 생성 합니다.  
  
 구현에 `IDebugExpressionContext2::ParseText`, DE는 COM의 사용 `CoCreateInstance` 함수 식 계산기를 인스턴스화하고 표시 하는 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md) 인터페이스 \(예제를 참조 하십시오은 `IDebugExpressionEvaluator` 인터페이스\).  다음 호출 하는 DE [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 얻을 수 있는 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) 인터페이스입니다.  이 인터페이스의 구현에 사용 됩니다 `IDebugExpression2::EvaluateSync` 및 `IDebugExpression2::EvaluateAsync` 는 평가 수행 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetExpression](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md)