---
title: "식 계산 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "평가 식 [디버깅 SDK]"
  - "디버깅 [디버깅 SDK], 식 계산"
  - "식 계산"
ms.assetid: 5ccfcc80-dea5-48a1-8bae-6a26f8d3bc56
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 식 계산
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

자동, 조사식, 간략 한 조사식을 또는 즉시 windows에서 전달 되는 문자열 식이 작성 됩니다.  식이 계산 되는 경우 변수 또는 인수 및 해당 값의 종류와 이름 포함 된 인쇄 가능한 문자열을 생성 합니다.  이 문자열은 해당 IDE 창에 표시 됩니다.  
  
## 구현  
 프로그램이 중단점에서 중지 했을 때 식이 계산 됩니다.  식으로 표시 됩니다 있는  [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 바인딩 및 지정 된 식 계산 컨텍스트 내에서 계산에 대 한 준비가 된 구문 분석 된 식을 나타내는 인터페이스를 합니다.  디버그 엔진 \(DE\)를 구현 하 여 제공 식 평가 컨텍스트 스택 프레임을 결정에서  [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다.  
  
 사용자 문자열을 지정 하는  [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 디버그 엔진 \(DE\) 인터페이스를 얻을 수는  [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 인터페이스는 사용자가 문자열을 전달 하는  [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 메서드.  구문 분석 된 식을 평가 위한 준비 반환 되는 IDebugExpression2 인터페이스를 포함 합니다.  
  
 로 `IDebugExpression2` 인터페이스, 동기 또는 비동기 식 평가 식의 값은 DE에 얻을 수를 사용 하 여  [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 또는  [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md).  이 값은 이름 및 형식 변수 또는 인수를 디스플레이를 IDE로 전송 됩니다.  값, 이름 및 형식으로 표시 되는  [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스입니다.  
  
 식 계산을 활성화 하는 DE 구현 해야는  [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 및  [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다.  동기 및 비동기 계산의 구현이 필요는  [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 방법입니다.  
  
## 참고 항목  
 [스택 프레임](../../extensibility/debugger/stack-frames.md)   
 [식 평가 컨텍스트](../../extensibility/debugger/expression-evaluation-context.md)   
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)