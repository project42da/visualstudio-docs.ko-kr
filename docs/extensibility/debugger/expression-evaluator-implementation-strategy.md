---
title: 식 계산기 구현 전략 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, implementation strategy
- debug engines, implementation strategies
ms.assetid: 1bccaeb3-8109-4128-ae79-16fd8fbbaaa2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e67b2496c2e30428cd4cc830526e53cf0cc61fdd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="expression-evaluator-implementation-strategy"></a>식 계산기 구현 전략
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 식 계산기 (EE)를 신속 하 게 작성 하는 한 가지 방법은 먼저에서 지역 변수를 표시 하는 데 필요한 최소한의 코드를 구현 하는 것은 **지역** 창. 하는 것이 유용의 각 줄의 **지역** 창 이름, 형식 및 지역 변수의 값을 표시 하 고 세 개 모두가으로 표현 되는 프로그램 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 개체입니다. 이름, 형식 및 지역 변수 값에서 얻을 수 있습니다는 `IDebugProperty2` 개체를 호출 하 여 해당 [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 메서드. 지역 변수를 표시 하는 방법에 대 한 자세한 내용은 **지역** 창 참조 [표시 지역](../../extensibility/debugger/displaying-locals.md)합니다.  
  
## <a name="discussion"></a>토론  
 가능한 구현을 시퀀스 구현으로 시작 [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)합니다. [구문 분석](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 및 [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) 메서드 지역 변수를 표시 하려면 구현 해야 합니다. 호출 `IDebugExpressionEvaluator::GetMethodProperty` 반환는 `IDebugProperty2` 메서드를 나타내는 개체: 즉, 한 [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) 개체입니다. 메서드 자체에 표시 되지 않습니다는 **지역** 창.  
  
 [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 다음 메서드를 구현 해야 합니다. 지역 변수 및 인수 목록을 전달 하 여 가져오려면이 메서드를 호출 하는 디버그 엔진 (DE) `IDebugProperty2::EnumChildren` 는 `guidFilter` 의 인수 `guidFilterLocalsPlusArgs`합니다. `IDebugProperty2::EnumChildren` 호출 [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) 및 [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md), 단일 열거에 결과 결합 합니다. 참조 [표시 지역](../../extensibility/debugger/displaying-locals.md) 내용을 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [식 계산기 구현](../../extensibility/debugger/implementing-an-expression-evaluator.md)   
 [로컬 항목 표시](../../extensibility/debugger/displaying-locals.md)