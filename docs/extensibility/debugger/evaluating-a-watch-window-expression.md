---
title: "조사식 창 식 평가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Watch window expressions
- Watch window, expressions
- expression evaluation, Watch window expressions
ms.assetid: b07e72c7-60d3-4b30-8e3f-6db83454c348
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 03a74bf73f457009a6f17f8e7bdda8e4e7b9e35f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="evaluating-a-watch-window-expression"></a>조사식 창 식 평가
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 실행이 일시 중지 하는 경우 Visual Studio 디버그 엔진 (DE) 조사식 목록에 각 식의 현재 값을 결정 하려면를 호출 합니다. DE (EE)는 식 계산기를 사용 하 여 각 식은 평가 하 고 Visual Studio에서 해당 값이 표시 됩니다는 **조사식** 창.  
  
 조사식 목록 식이 계산 되는 방법의 개요는 다음과 같습니다.  
  
1.  Visual Studio 호출 하는 DE [GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) 식을 평가 하는 데 사용할 수 있는 식 컨텍스트를 합니다.  
  
2.  Visual Studio에서 호출 조사 목록에 각 식, [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 식 텍스트 구문 분석 된 식으로 변환할 수 있습니다.  
  
3.  `IDebugExpressionContext2::ParseText`호출 [구문 분석](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 생성와 텍스트를 구문 분석의 실제 작업을 수행 하는 [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) 개체입니다.  
  
4.  `IDebugExpressionContext2::ParseText`만듭니다는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 개체 및 설정의 `IDebugParsedExpression` 개체입니다. 이 I`DebugExpression2` 개체 Visual Studio에 반환 됩니다.  
  
5.  Visual Studio 호출 [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 구문 분석 된 식을 계산할 수 있습니다.  
  
6.  `IDebugExpression2::EvaluateSync`에 대 한 호출을 전달 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) 실제 평가 수행 하 고 생성 하는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) Visual Studio로 반환 되는 개체입니다.  
  
7.  Visual Studio 호출 [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 다음 조사 목록에 표시 되는 식의 값을 가져옵니다.  
  
## <a name="parse-then-evaluate"></a>구문 분석 한 다음 평가  
 복잡 한 식을 구문 분석 하는 평가 하는 것 보다 훨씬 더 오래 걸릴 수 있습니다, 때문 식을 계산 하는 과정은 나뉘어져 두 단계: 1) 식의 구문 분석 하 고 2) 구문 분석된 된 식을 평가 합니다. 이러한 방식으로 평가 여러 번 나타날 수 있지만 식을 한 번만 구문 분석 해야 합니다. 중간 구문 분석 된 식에는 EE에서 반환 되는 [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) 차례로 캡슐화 되 고으로 DE에서 반환 되는 개체는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 개체입니다. `IDebugExpression` 에 모든 평가 지연 하는 개체는 `IDebugParsedExpression` 개체입니다.  
  
> [!NOTE]
>  Visual Studio에서는이; 가정 하는 경우에이 2 단계 프로세스에 맞게 EE 필요 하지 않습니다. EE 구문 분석 하 고 동일한 단계에서 평가할 수 있습니다 때 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) 호출 됩니다 (이 예를 들어 MyCEE 샘플이 작동 방법). 해당 언어 복잡 한 식을 형성 되는 경우에 평가 단계에서 구문 분석 단계를 구분 하는 것이 좋습니다. 이렇게 여러 식을 조사할 때 Visual Studio 디버거에서 성능이 향상 표시 됩니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [식 계산의 샘플 구현](../../extensibility/debugger/sample-implementation-of-expression-evaluation.md)  
 식 계산 과정을 단계별로 실행 되도록 MyCEE 샘플을 사용 합니다.  
  
 [조사식 창 계산](../../extensibility/debugger/evaluating-a-watch-expression.md)  
 식이 성공적으로 구문 분석 한 후 수행 되는 작업에 대해 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [평가 컨텍스트](../../extensibility/debugger/evaluation-context.md)  
 식 계산기 (EE)를 호출 하는 디버그 엔진 (DE) 때 전달 되는 인수를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)