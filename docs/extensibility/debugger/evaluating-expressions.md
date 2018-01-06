---
title: "식 계산 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expressions [Debugging SDK], evaluating
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: 5ccfcc80-dea5-48a1-8bae-6a26f8d3bc56
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 24cc20166bad875dcaebbd5492a7fe8317539d47
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="evaluating-expressions"></a>식 계산
식은 자동, 조사식, 간략 한 조사식, 또는 직접 실행 창에서 전달 되는 문자열에서 만들어집니다. 식이 계산 되는 이름 및 유형의 변수 또는 인수 및 값을 포함 하는 인쇄 가능한 문자열을 생성 됩니다. 이 문자열은 해당 IDE 창에 표시 됩니다.  
  
## <a name="implementation"></a>구현  
 식은은 프로그램이 중단점에서 중지 될 때 평가 됩니다. 식 자체로 표시 됩니다는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 인터페이스에 바인딩 및 특정된 식 평가 컨텍스트 내에서 평가 대 한 사용할 준비가 되어 구문 분석 된 식을 나타냅니다. 디버그 엔진 (DE)를 구현 하 여 제공 하는 식 계산 컨텍스트를 결정 하는 스택 프레임의 [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다.  
  
 사용자 문자열 및 [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스 디버그 엔진 (DE) 가져올 수는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 사용자 문자열을 전달 하 여 인터페이스는 [ IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 메서드. 반환 된 IDebugExpression2 인터페이스 구문 분석된 된 식 평가 위한 준비를 포함 합니다.  
  
 와 `IDebugExpression2` 인터페이스는 DE 동기 또는 비동기 식 평가 통해 식의 값을 얻을 수를 사용 하 여 [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 또는 [IDebugExpression2:: EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)합니다. 이름 및 유형의 변수 또는 인수를 함께이 값 표시에 대 한 IDE에 전송 됩니다. 값, 이름 및 형식으로 표시 됩니다는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스입니다.  
  
 식 계산을 사용 하도록 설정 하는 DE 구현 해야 합니다는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 및 [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다. 동기 및 비동기 평가 구현이 필요는 [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [스택 프레임](../../extensibility/debugger/stack-frames.md)   
 [식 계산 컨텍스트](../../extensibility/debugger/expression-evaluation-context.md)   
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)