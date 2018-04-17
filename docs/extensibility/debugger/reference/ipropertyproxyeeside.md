---
title: IPropertyProxyEESide | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IPropertyProxyEESide
helpviewer_keywords:
- IPropertyProxyEESide interface
ms.assetid: cf227cf8-39d9-4758-8f7e-a697aebb1926
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0f1dea4c3124cd532177618d84e2302a32e8bc4a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ipropertyproxyeeside"></a>IPropertyProxyEESide
이 인터페이스는 연결된 된 개체에 데이터를 보려는 메서드를 제공 합니다. 이 인터페이스는 형식 시각화 도우미에 대 한 지원의 일부입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IPropertyProxyEESide : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 식 계산기는 형식 시각화 도우미를 지원 하기 위해이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) 이 인터페이스를 가져올 수 있습니다. 호출 [QueryInterface](/cpp/atl/queryinterface) 에 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 가져오는 인터페이스를는 [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md) 인터페이스입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 메서드는이 인터페이스에서 구현 됩니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[InitSourceDataProvider](../../../extensibility/debugger/reference/ipropertyproxyeeside-initsourcedataprovider.md)|개체의 데이터에 액세스할 수 있도록 데이터 원본 공급자를 초기화 합니다.|  
|[GetManagedViewerCreationData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata.md)|개체의 어셈블리에 대 한 정보를 검색합니다.|  
|[GetInitialData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getinitialdata.md)|개체에 대 한 초기 데이터를 가져옵니다.|  
|[CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)|기존 데이터 저장소의 복사본을 만듭니다.|  
|[InPlaceUpdateObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md)|기존 데이터 저장소에 대 한 참조를 만듭니다.|  
|[ResolveAssemblyRef](../../../extensibility/debugger/reference/ipropertyproxyeeside-resolveassemblyref.md)|이 개체를 포함 하는 어셈블리의 컨텍스트에서 특정 어셈블리에 대 한 정보를 검색 합니다.|  
  
## <a name="remarks"></a>설명  
 형식 시각화 도우미는이 인터페이스의 일부인 개체와 관련 된 값에 액세스 하려면이 인터페이스를 사용 합니다. 통해 데이터 액세스는 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 데이터의 읽기 전용 보기를 제공 하는 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [사용자 지정 뷰어와 형식 시각화 도우미](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)