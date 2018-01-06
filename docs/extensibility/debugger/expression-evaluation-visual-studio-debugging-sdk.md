---
title: "식 계산 (Visual Studio 디버깅 SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: 5044ced5-c18c-4534-b0bf-cc3e50cd57ac
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ed0e494cc0efd48ea3c22d9fd881aafec42a984b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="expression-evaluation-visual-studio-debugging-sdk"></a>식 계산 (Visual Studio 디버깅 SDK)
중단 모드에서는 IDE 프로그램의 여러 변수가 포함 된 간단한 식을 계산할 수 있어야 합니다. 이를 위해 디버그 엔진 (DE) 구문 분석 하 고 IDE의 창 중 하나에 입력 된 식을 계산할 수 있어야 합니다.  
  
 식을 사용 하 여 만들어집니다는 [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 메서드에 결과 나타내는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 인터페이스입니다.  
  
 **IDebugExpression2** DE 및 호출 인터페이스를 구현 해당 **EvalAsync** 반환 하는 메서드는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스를 표시 하기 위해 IDE에는 IDE에서 식 평가의 결과입니다. [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 조사식 창 또는 지역 창에는 식의 값을 배치 하기 위해 사용할 수 있는 구조를 반환 합니다.  
  
 디버그 세션 또는 패키지 디버그 관리자 (SDM) 호출 하면 중지 [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 또는 [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 가져오려는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 나타내는 인터페이스 평가의 결과입니다. `IDebugProperty2`에 이름, 형식 및 식의 값을 반환 하는 메서드가 있습니다. 이 정보는 다양 한 디버거 창에 표시 됩니다.  
  
## <a name="using-expression-evaluation"></a>식 계산을 사용 하 여  
 식 계산을 사용 하려면 구현 해야 하는 [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 메서드 및 모든의 메서드는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 인터페이스는 다음 표에 나와 있는 것 처럼 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)|비동기적으로 식을 계산합니다.|  
|[중단](../../extensibility/debugger/reference/idebugexpression2-abort.md)|비동기 식 계산을 끝냅니다.|  
|[EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)|동기적으로 식을 계산합니다.|  
  
 동기 및 비동기 평가 구현이 필요는 [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 메서드. 비동기 식 계산의 구현이 필요 [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)