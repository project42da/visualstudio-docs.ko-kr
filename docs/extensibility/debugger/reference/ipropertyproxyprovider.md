---
title: IPropertyProxyProvider | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IPropertyProxyProvider
helpviewer_keywords:
- IPropertyProxyProvider interface
ms.assetid: 52e9f7fc-6fe0-4d23-890b-5673dca8c3cb
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 73a1a1a189e4922d662081a92738b1c35c6bb291
ms.contentlocale: ko-kr
ms.lasthandoff: 04/05/2017

---
# <a name="ipropertyproxyprovider"></a>IPropertyProxyProvider
이 인터페이스에서 보고 한 개체의 데이터를 변경 하는 프록시 인터페이스를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IPropertyProxyProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 식 계산기 (EE) 구현 하는 동일한 개체에서이 인터페이스를 구현 하는 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 형식 시각화 도우미는 EE 지원의 일부로 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [QueryInterface](/cpp/atl/queryinterface) 에 `IDebugProperty3` 인터페이스가이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 `IPropertyProxyProvider` 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)|개체에 데이터를 볼 수 있는 속성 프록시 인터페이스를 검색 합니다.|  
  
## <a name="remarks"></a>주의  
 EE 구현이 인터페이스를 구현 하지만 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) 에서 일반적으로 처리는 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)합니다. 참조 [Visualizing 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md) IEEVisualizerService 인터페이스를 얻는 방법에 대 한 세부 정보에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)   
 [사용자 지정 뷰어와 형식 시각화 도우미](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)   
 [데이터 시각화 및 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)
