---
title: IEEDataStorage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEEDataStorage
helpviewer_keywords:
- IEEDataStorage interface
ms.assetid: 704e932d-2325-410e-89c4-ce88c6ec19da
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aeb98c4c4d3b544616412b3cf5cf8a162fddbd6b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ieedatastorage"></a>IEEDataStorage
이 인터페이스는 바이트 배열을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEEDataStorage : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 식 계산기 (EE)를 나타내는 바이트 배열을이 인터페이스를 구현 합니다. (형식 시각화 도우미에서 사용 하 여 검색 한 데이터를 변경 하는 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스). 일반적으로 EE 외부 형식 시각화 도우미를 지원 하기 위해이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 메서드는 `IPropertyProxyEESide` 모든 인터페이스는이 인터페이스를 반환 합니다. 호출 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) 얻으려고는 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스입니다. 호출 [QueryInterface](/cpp/atl/queryinterface) 에 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 가져오는 인터페이스를는 [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md) 인터페이스입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 `IEEDataStorage` 인터페이스 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)|제공 된 버퍼에 데이터 바이트의 지정 된 수를 검색 합니다.|  
|[GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)|사용할 수 있는 데이터 바이트 수를 검색 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 특정 개체에서 보유 하는 데이터에 액세스 하는 형식 시각화 도우미에서 사용 됩니다. 데이터 형식 시각화 도우미 방식으로 사용자에 게 표시 하는 데 필요한으로 조작할 수 있도록 바이트 배열을로 처리 됩니다.  
  
 사용자 지정 뷰어 ´ ï ´이 인터페이스를 원하는 경우 사용자 지정 뷰어는 사용자 지정 인터페이스를 사용 하는 보다 일반적인 방법으로 있지만 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md) 또는 [GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md) (데이터에 대 한 문자열 지향).  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [형식 시각화 도우미 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)