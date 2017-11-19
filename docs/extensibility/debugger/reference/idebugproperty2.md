---
title: IDebugProperty2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty2
helpviewer_keywords: IDebugProperty2 interface
ms.assetid: a7d5c70f-a1a5-4120-9f70-184e01c25bff
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 45ad3a6c0d250136d0ab3e1becb088ea140b42e8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugproperty2"></a>IDebugProperty2
이 인터페이스는 스택 프레임 속성, 프로그램 문서 속성 또는 일부 다른 속성을 나타냅니다. 속성 식 평가의 결과 일반적으로 합니다.  
  
> [!NOTE]
>  하지만 이러한 "property"를 사용이 하는 클래스의 멤버 변수 해당 의미와 혼동 해서는 안는 `IDebugProperty2` 이 엔터티를 나타낼 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProperty2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 특정 유형의 값을 나타내기 위해이 인터페이스를 구현 합니다. 예를 들어, 값에는 식 계산, 메모리 또는 레지스터와 해당 값의 목록 표시에 사용 되는 메모리 내 컨텍스트에 결과로 숫자 값을 수 있습니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 또는 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 평가의 결과 나타내는이 인터페이스를 가져올 수 있습니다. `IDebugExpression2::EvaluateAsync`전송 하 여이 인터페이스를 반환 합니다.는 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) 인터페이스를 호출 하 여 SDM [GetResult](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) 속성을 검색 합니다.  
  
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugpropertycreateevent2-getdebugproperty.md) 관련된 스크립트 문서를 제공 하려면이 인터페이스를 반환 합니다.  
  
 [GetReturnValue](../../../extensibility/debugger/reference/idebugreturnvalueevent2-getreturnvalue.md) 함수의 반환 값을 나타내기 위해이 인터페이스를 반환 합니다.  
  
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugprogram2-getdebugproperty.md) 이 인터페이스는 이름 또는 메모리 내 컨텍스트에 같은 프로그램의 다양 한 속성을 나타내는를 반환 합니다.  
  
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) 지역 변수와 같은 스택 프레임의 다양 한 속성을 나타내기 위해이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugProperty2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)|채웁니다는 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 속성을 설명 하는 구조입니다.|  
|[SetValueAsString](../../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md)|문자열에서 속성의 값을 설정합니다.|  
|[SetValueAsReference](../../../extensibility/debugger/reference/idebugproperty2-setvalueasreference.md)|지정한 참조의 값에서 속성의 값을 설정합니다.|  
|[EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)|속성의 자식을 열거합니다.|  
|[GetParent](../../../extensibility/debugger/reference/idebugproperty2-getparent.md)|속성의 부모를 반환 합니다.|  
|[GetDerivedMostProperty](../../../extensibility/debugger/reference/idebugproperty2-getderivedmostproperty.md)|속성의 가장 많이 파생 된 속성을 설명 하는 속성을 반환 합니다.|  
|[GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md)|속성의 값을 구성 하는 메모리 바이트 수를 반환 합니다.|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)|속성 값에 대 한 메모리 컨텍스트를 반환합니다.|  
|[GetSize](../../../extensibility/debugger/reference/idebugproperty2-getsize.md)|속성 값의 바이트 단위로 크기를 반환 합니다.|  
|[GetReference](../../../extensibility/debugger/reference/idebugproperty2-getreference.md)|이 속성의이 값에 대 한 참조를 반환합니다.|  
|[GetExtendedInfo](../../../extensibility/debugger/reference/idebugproperty2-getextendedinfo.md)|속성의 확장된 정보를 반환합니다.|  
  
## <a name="remarks"></a>설명  
 속성을로 표현 되는 `IDebugProperty2` 인터페이스를 이름, 형식 및 주소를 사용 하 여 값으로 생각할 수 있습니다. 보다 일반적인 용어로 `IDebugProperty2` 부모 및 자식 노드 계층 구조에 있는 모든 나타낼 수 있습니다.  
  
 속성은 일반적으로 일시적인 지속 되는 범위 내 에서만 현재 스택 프레임을 예. 반면, 참조로 표현 되는 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 인터페이스를 유지 되는 기간 값 메모리에 남아 있는 기간과 같습니다.  
  
 IDE에서 사용할 수는 `IDebugProperty2` 인터페이스를 사용자가 찾아 실행 시 속성을 수정할 수 있도록 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)