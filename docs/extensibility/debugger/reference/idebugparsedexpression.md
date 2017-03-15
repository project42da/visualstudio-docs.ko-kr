---
title: "IDebugParsedExpression | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugParsedExpression"
helpviewer_keywords: 
  - "IDebugParsedExpression 인터페이스"
ms.assetid: be6486ed-b070-4898-95b1-58581bcb4447
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugParsedExpression
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스는 구문 분석 된 식을 평가 나타냅니다.  
  
## 구문  
  
```  
IDebugParsedExpression : IUnknown  
```  
  
## 구현자를 위한 정보  
 식 계산기는 평가 위한 준비 되는 구문 분석 된 식을 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 에 대 한 호출 [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 이 인터페이스를 반환 합니다.  
  
## Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugParsedExpression`합니다.  
  
|메서드|설명|  
|---------|--------|  
|[EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)|구문 분석 된 식을 평가합니다.|  
  
## 설명  
 호출자에 게 식을 계산할 준비 되 면 호출 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) 반환 하는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 평가의 결과 포함 하는 합니다. 평가, 평가, 구문 분석 된 식을 여러 번 계산 될 수 있습니다. 그런 다음 구문 분석, 식 구문 분석 하는 시간이 많이 걸리는 과정을 무시 하려면이 두 부분으로 구성 방법입니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)