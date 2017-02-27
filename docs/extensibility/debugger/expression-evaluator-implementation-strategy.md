---
title: "식 계산기 구현 전략 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "식 계산, 구현 전략"
  - "디버그 엔진을 구현 전략"
ms.assetid: 1bccaeb3-8109-4128-ae79-16fd8fbbaaa2
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 식 계산기 구현 전략
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 식 계산기 \(EE\)를 신속 하 게 만드는 한 가지 방법은 먼저 지역 변수를 표시 하는 데 필요한 최소 코드를 구현 하는 것은 **지역** 창입니다. 하는 것이 유용의 각 줄은 **지역** 창 이름, 형식 및 지역 변수의 값을 표시 하 고 세 가지 모두로 표현 되는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 개체입니다. 이름, 형식 및 지역 변수의 값에서 가져올 수 있습니다는 `IDebugProperty2` 개체를 호출 하 여 해당 [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 메서드. 지역 변수를 표시 하는 방법에 대 한 자세한 내용은 **지역** 창 참조 [지역 변수를 표시합니다.](../../extensibility/debugger/displaying-locals.md)합니다.  
  
## 토론  
 구현 하는 가능한 구현 시퀀스 시작 [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)합니다.[구문 분석](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 및 [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) 메서드 지역 변수를 표시 하려면 구현 해야 합니다. 호출 `IDebugExpressionEvaluator::GetMethodProperty` 반환는 `IDebugProperty2` 메서드를 나타내는 개체입니다: 즉,는 [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) 개체. 메서드 자체에 표시 되지 않는 **지역** 창입니다.  
  
 [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 다음 메서드를 구현 해야 합니다. 전달 하 여 지역 변수 및 인수 목록을 가져오려면이 메서드를 호출 하는 디버그 엔진 \(DE\) `IDebugProperty2::EnumChildren` 는 `guidFilter` 인수의 `guidFilterLocalsPlusArgs`합니다.`IDebugProperty2::EnumChildren` 호출 [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) 및 [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md), 단일 열거에 결과 결합 합니다. 자세한 내용은 [지역 변수를 표시합니다.](../../extensibility/debugger/displaying-locals.md)을 참조하세요.  
  
## 참고 항목  
 [식 계산기를 구현합니다.](../../extensibility/debugger/implementing-an-expression-evaluator.md)   
 [지역 변수를 표시합니다.](../../extensibility/debugger/displaying-locals.md)