---
title: "식 계산기 아키텍처 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "아키텍처, 식 계산기"
  - "식 계산기, 아키텍처"
  - "디버깅 [디버깅 SDK], 식 계산기"
ms.assetid: aad7c4c6-1dc1-4d32-b975-f1fdf76bdeda
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 식 계산기 아키텍처
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 Visual Studio 디버그 패키지에는 자체 언어 통합은 필요한 식 계산기 \(EE\) 인터페이스를 구현 하 고 공용 언어 런타임 기호 공급자 \(SP\) 및 바인더 인터페이스 호출 의미 합니다. SP 및 바인더 개체의 현재 실행 주소와 함께 식이 계산 되는 컨텍스트입니다. 이러한 인터페이스 생성 하 고 사용 하는 정보는 EE의 아키텍처의 주요 개념을 나타냅니다.  
  
## 개요  
  
### 식 구문 분석  
 프로그램을 디버깅 하는 경우 여러 가지 이유가 있지만 항상 디버깅 중인 프로그램 \(사용자가 배치 중단점 또는 예외로 인해 발생 한\) 중단점에서 중지 되었습니다 때 식이 계산 됩니다. 에 표시 된 대로 Visual Studio 스택 프레임을 가져오는 하는 경우이 시점에는 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) 인터페이스에서 디버그 엔진 \(DE\). Visual Studio에서 다음 호출 [GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) 얻으려고는 [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다. 이 인터페이스는 식을 계산할 수 있습니다; 컨텍스트를 나타냅니다. [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 는 진입점을 사용 하 여 평가 프로세스입니다. 이 시점까지 모든 인터페이스는 DE 여 구현 됩니다.  
  
 때 `IDebugExpressionContext2::ParseText` 은 호출는 DE 중단점이 발생 한 소스 파일의 언어와 관련 된 EE 인스턴스화합니다 \(은 DE도 인스턴스화합니다는 s H이 시점에서\). EE 나타내는 [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md) 인터페이스입니다. 다음 호출 하는 DE [구문 분석](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) \(텍스트 형태로\) 식 구문 분석 된 식으로 변환 하려면 평가 위해 준비 합니다. 이 구문 분석 된 식으로 표현 됩니다는 [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) 인터페이스입니다. 참고 식이 일반적으로 구문 분석 되 고이 시점에서 평가 되지 않습니다.  
  
 DE 구현 하는 개체를 만듭니다는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 인터페이스를 넣습니다는 `IDebugParsedExpression` 개체는 `IDebugExpression2` 개체를 반환 하 고는 `IDebugExpression2` 에서 개체 `IDebugExpressionContext2::ParseText`합니다.  
  
### 식을 계산  
 Visual Studio에서 호출 하거나 [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 또는 [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 구문 분석된 된 식을 평가 합니다. 이러한 메서드는 둘 다 호출 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) \(`IDebugExpression2::EvaluateSync` 메서드를 호출 하는 동안 즉시 `IDebugExpression2::EvaluateAsync` 백그라운드 스레드를 통해 메서드를 호출\) 구문 분석된 된 식을 평가 하 고 반환는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 구문 분석 된 식의 종류와 값을 나타내는 인터페이스입니다.`IDebugParsedExpression::EvaluateSync` 제공 된 SH, 주소 및 바인더를 사용 하 여 구문 분석 된 식을 나타내는 실제 값으로 변환 하는 `IDebugProperty2` 인터페이스입니다.  
  
### 예를 들어  
 중단점이 적중 되는 실행 중인 프로그램에서 한 후에 변수를 보려면 사용자를 선택 된 **간략 한 조사식** 대화 상자입니다. 이 대화 상자에서는 변수 이름, 해당 값 및 형식을 보여 줍니다. 일반적으로 사용자 값을 변경할 수 있습니다.  
  
 경우는 **간략 한 조사식** 대화 상자가 표시 되어, 검사 되 고 변수의 이름을 텍스트로 보내집니다 [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)합니다. 반환 합니다.는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 변수,이 경우 구문 분석된 된 식을 나타내는 개체입니다.[EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 다음 호출을 생성 한 `IDebugProperty2` 이름 뿐만 아니라 변수의 값 형식을 나타내는 개체입니다. 표시 되는이 정보입니다.  
  
 사용자는 변수의 값을 변경 하면 [SetValueAsString](../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md) 않으므로 프로그램 다시 시작 될 때 사용 됩니다. 메모리에 변수의 값을 변경 하는 새 값으로 호출 되 실행 합니다.  
  
 참조 [지역 변수를 표시합니다.](../../extensibility/debugger/displaying-locals.md) 변수 값을 표시 하는이 프로세스에 대 한 자세한 내용은 합니다. 참조 [로컬 값을 변경](../../extensibility/debugger/changing-the-value-of-a-local.md) 변수의 값이 변경 하는 방법에 대 한 자세한 내용은 합니다.  
  
## 단원 내용  
 [평가 컨텍스트](../../extensibility/debugger/evaluation-context.md)  
 DE EE를 호출할 때 전달 되는 인수를 제공 합니다.  
  
 [키 식 계산기 인터페이스](../../extensibility/debugger/key-expression-evaluator-interfaces.md)  
 평가 컨텍스트에 함께 EE를 작성할 때 필요한 중요 한 인터페이스에 설명 합니다.  
  
## 참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [지역 변수를 표시합니다.](../../extensibility/debugger/displaying-locals.md)   
 [로컬 값을 변경](../../extensibility/debugger/changing-the-value-of-a-local.md)