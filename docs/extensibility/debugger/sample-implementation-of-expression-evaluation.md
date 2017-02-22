---
title: "식 계산의 샘플 구현 | Microsoft Docs"
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
  - "식 계산기"
  - "디버깅 [디버깅 SDK], 식 계산기"
  - "식 계산, 예제"
ms.assetid: 2a5f04b8-6c65-4232-bddd-9093653a22c4
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# 식 계산의 샘플 구현
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 에 대 한 한 **조사식** 창 식, Visual Studio 호출 [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 생성 하는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 개체입니다.`IDebugExpressionContext2::ParseText` 식 계산기 \(EE\) 및 호출을 인스턴스화하고 [구문 분석](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 얻을 수는 [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) 개체입니다.  
  
 이 구현 `IDebugExpressionEvaluator::Parse` 다음 작업을 수행 합니다.  
  
1.  \[C \+ \+ 전용\] 오류가 있는지 확인 하는 식을 구문 분석 합니다.  
  
2.  클래스를 인스턴스화합니다 \(라는 `CParsedExpression` 이 예에서\)를 구현 하는 `IDebugParsedExpression` 인터페이스를 구문 분석할 식을 클래스에 저장 합니다.  
  
3.  반환 된 `IDebugParsedExpression` 에서 인터페이스는 `CParsedExpression` 개체입니다.  
  
> [!NOTE]
>  이후에 나오는 예제 및 MyCEE 샘플 식 계산기는 평가에서 구문 분석 하는 분리 하지 않습니다.  
  
## 관리 코드  
 구현인이 `IDebugExpressionEvaluator::Parse` 관리 코드에서. 이 버전의 메서드를 구문 분석을 지연 참고 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) 구문 분석 하는 것에 대 한 코드는 또한 동시에 평가할 때 \(참조 [조사식 평가](../../extensibility/debugger/evaluating-a-watch-expression.md)\).  
  
```c#  
namespace EEMC { public class CParsedExpression : IDebugParsedExpression { public HRESULT Parse( string                 expression, uint                   parseFlags, uint                   radix, out string                 errorMessage, out uint                   errorPosition, out IDebugParsedExpression parsedExpression) { errorMessage = ""; errorPosition = 0; parsedExpression = new CParsedExpression(parseFlags, radix, expression); return COM.S_OK; } } }  
```  
  
## 관리 되지 않는 코드  
 구현인이 `IDebugExpressionEvaluator::Parse` 비관리 코드에서. 이 메서드는 도우미 함수를 호출 `Parse`, 식 및 오류에 대 한 검사 구문 분석 하려면이 메서드는 결과 값을 무시 하지만 합니다. 공식적인 평가 연기 되 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) 식을 평가 하는 동안 구문 분석 되어 위치 \(참조 [조사식 평가](../../extensibility/debugger/evaluating-a-watch-expression.md)\).  
  
```cpp#  
STDMETHODIMP CExpressionEvaluator::Parse( in    LPCOLESTR                 pszExpression, in    PARSEFLAGS                flags, in    UINT                      radix, out   BSTR                     *pbstrErrorMessages, inout UINT                     *perrorCount, out   IDebugParsedExpression  **ppparsedExpression ) { if (pbstrErrorMessages == NULL) return E_INVALIDARG; else *pbstrErrormessages = 0; if (pparsedExpression == NULL) return E_INVALIDARG; else *pparsedExpression = 0; if (perrorCount == NULL) return E_INVALIDARG; HRESULT hr; // Look for errors in the expression but ignore results hr = ::Parse( pszExpression, pbstrErrorMessages ); if (hr != S_OK) return hr; CParsedExpression* pparsedExpr = new CParsedExpression( radix, flags, pszExpression ); if (!pparsedExpr) return E_OUTOFMEMORY; hr = pparsedExpr->QueryInterface( IID_IDebugParsedExpression, reinterpret_cast<void**>(ppparsedExpression) ); pparsedExpr->Release(); return hr; }  
```  
  
## 참고 항목  
 [조사식 창 식 평가](../../extensibility/debugger/evaluating-a-watch-window-expression.md)   
 [조사식 평가](../../extensibility/debugger/evaluating-a-watch-expression.md)