---
title: IEnumDebugAddresses | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumDebugAddresses
helpviewer_keywords:
- IEnumDebugAddresses interface
ms.assetid: 5f6f6751-e6d8-4c5a-8e81-414b6e5d8cc5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bfed705253a03ec550e7533f7e2ab323b7ead62a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ienumdebugaddresses"></a>IEnumDebugAddresses
이 인터페이스를 구현 하는 개체의 컬렉션을 나타냅니다는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEnumDebugAdresses : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스를 구현 하는 개체의 집합을 제공할 기호 공급자에 의해 구현 됩니다는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다. 이 하지 있어 표준 COM 열거형은 [GetCount](../../../extensibility/debugger/reference/ienumdebugaddresses-getcount.md) 메서드.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스에서 반환 된 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md) 및 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugaddresses-next.md)|다음 검색 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 열거에 있는 개체입니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugaddresses-skip.md)|지정 된 항목 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugaddresses-reset.md)|열거형의 첫 번째 항목을 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugaddresses-clone.md)|현재 열거형의 복사본을 검색 합니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugaddresses-getcount.md)|열거형에 있는 항목의 수를 검색 합니다.|  
  
## <a name="remarks"></a>설명  
 식 계산기에 제공 하는 적절 한 주소를 확인 하려면이 인터페이스는 일반적으로 디버그 엔진에 의해 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)