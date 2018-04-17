---
title: IDebugAlias | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugAlias
helpviewer_keywords:
- IDebugAlias interface
ms.assetid: 3cc4c9a4-7805-4239-b00e-eb4a024f3c55
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f77e62b2dc36bb03b2145361cdea7dd9e65b2d32
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugalias"></a>IDebugAlias
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 변수에 대 한 숫자 별칭을 나타냅니다. 별칭은 다른 변수 이름을 단순히 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugAlias : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 식 계산기 (EE) 변수에 대 한 숫자 별칭을 지원 하기 위해이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) 특정 개체에 대 한 별칭을 만듭니다. 별칭을 검색 하려면 사용 하 여 [FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md) 또는 [GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md)합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 에 정의 된 다음 메서드는 `IDebugAlias` 인터페이스입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md)|이 별칭을 참조 하는 개체를 가져옵니다.|  
|[GetName](../../../extensibility/debugger/reference/idebugalias-getname.md)|별칭 이름을 가져옵니다.|  
|[GetICorDebugValue](../../../extensibility/debugger/reference/idebugalias-geticordebugvalue.md)|검색 한 `ICorDebugValue` 인터페이스에 대 한 액세스를 제공 하는 관리 되는이 개체 (관리 코드에만 해당)에 대 한 코드 정보입니다.|  
|[Dispose](../../../extensibility/debugger/reference/idebugalias-dispose.md)|더 이상으로 별칭 사용이 표시 됩니다.|  
  
## <a name="remarks"></a>설명  
 별칭은 예를 들어 1001 # # 문자로 이어지는 문자열 양식에서 10 진수입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md)   
 [FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md)   
 [GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md)