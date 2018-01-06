---
title: "식 계산기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expressions [Debugging SDK]
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: f9381b2f-99aa-426c-aea0-d9c15f3c859b
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 55aaa595c49d0c50cff5f874d1b322c3adbb9729
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="expression-evaluator"></a>식 계산기
식 계산기 (EE) IDE가 중단 모드에 있을 때 사용자가 볼 수 있도록 하는 언어를 구문 분석 하 고 실행할 때 변수 및 식 평가의 구문을 검사 합니다.  
  
## <a name="using-expression-evaluators"></a>식 계산기를 사용 하 여  
 식을 사용 하 여 만들어집니다는 [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 다음과 같이 메서드:  
  
1.  디버그 엔진 (DE)를 구현 하는 [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다.  
  
2.  디버그 패키지가 가져옵니다는 `IDebugExpressionContext2` 에서 개체는 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) 인터페이스 및 호출은 `IDebugStackFrame2::ParseText` 메서드를 가져올 수는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 개체입니다.  
  
3.  호출 하 여 디버그 패키지는 [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 메서드 또는 [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 식의 값을 가져오는 방법입니다. `IDebugExpression2::EvaluateAsync`명령/직접 실행 창에서 호출 됩니다. 다른 모든 UI 구성 요소 호출 `IDebugExpression2::EvaluateSync`합니다.  
  
4.  식 계산의 결과는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 이름, 형식 및 식 평가의 결과 값을 포함 하는 개체입니다.  
  
 식 평가 중 EE 기호 공급자 구성 요소 정보가 필요 합니다. 기호 공급자를 식별 하 고 이해 구문 분석된 된 식에 사용 되는 기호 정보를 제공 합니다.  
  
 비동기 식 계산이 완료 되 면 식 평가 완료 되었음을 IDE에 알리기 위해 비동기 이벤트 세션 디버그 관리자 (SDM)를 통해 DE로 전송 됩니다. 동기 식 계산이 완료 되 면 평가의 결과에 대 한 호출에서 반환 됩니다는 `IDebugExpression2::EvaluateSync` 메서드.  
  
## <a name="implementation-notes"></a>구현 참고 사항  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버그 엔진에서 공용 언어 런타임 (CLR) 인터페이스를 사용 하 여 식 계산기에 게 문의 해야 합니다. 결과적으로, 식 계산기는 함께 작동 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버그 엔진에서 CLR를 지원 해야 합니다 (모든 CLR 디버깅 인터페이스의 전체 목록은 일부인 debugref.doc에 있습니다의 [!INCLUDE[winsdklong](../../deployment/includes/winsdklong_md.md)]).  
  
## <a name="see-also"></a>참고 항목  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)