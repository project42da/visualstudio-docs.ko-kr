---
title: IDebugBinder | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBinder
helpviewer_keywords: IDebugBinder interface
ms.assetid: d1f31e5b-c6e2-4e02-8959-b3e86041b29c
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 614133a72e05f8bd412216d466bbfc90a197ff07
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugbinder"></a>IDebugBinder
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스는 일반적으로 메모리 내 컨텍스트에 또는 기호의 현재 값이 포함 된 개체에 기호 공급자에 의해 반환 되는 기호 필드를 바인딩합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugBinder : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스는 식 계산을 지원 하며 디버그 엔진 (DE)에 의해 구현 되어야 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스는 식 계산 프로세스에 사용 하며의 구현에서 일반적으로 사용 됩니다 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 및 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugBinder`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[바인딩](../../../extensibility/debugger/reference/idebugbinder-bind.md)|메모리 내 컨텍스트에 또는 기호의 현재 값이 포함 된 개체를 가져옵니다.|  
|[ResolveRuntimeType](../../../extensibility/debugger/reference/idebugbinder-resolveruntimetype.md)|개체의 런타임 형식을 결정합니다.|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugbinder-getmemorycontext.md)|메모리 내 컨텍스트에를 개체 위치 또는 메모리 주소를 변환합니다.|  
|[GetFunctionObject](../../../extensibility/debugger/reference/idebugbinder-getfunctionobject.md)|가져옵니다는 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 개체를 함수 매개 변수를 만드는 데 사용 합니다.|  
|[ResolveDynamicType](../../../extensibility/debugger/reference/idebugbinder-resolvedynamictype.md)|변수에 대 한 정확한 형식을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스에는 식 계산기가 사용 되는 개체 트리를 구문 분석을 반환 합니다. 식 계산기의 인스턴스를 식에서 기호를 변환 하려면 기호 공급자를 사용 하 여 식을 구문 분석 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)는 소스 코드의 위치를 기준으로 각 기호에 설명 합니다. [바인딩할](../../../extensibility/debugger/reference/idebugbinder-bind.md) 메서드 변환 `IDebugField` 개체를 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 메모리에서 실제 값으로 연결 하거나 기호를 바인딩하는 개체를 입력 합니다. 이러한 `IDebugObject` 개체 그러면 이후 평가 대 한 구문 분석 트리에 저장 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)