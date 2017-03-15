---
title: "IPropertyProxyEESide | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IPropertyProxyEESide"
helpviewer_keywords: 
  - "IPropertyProxyEESide 인터페이스"
ms.assetid: cf227cf8-39d9-4758-8f7e-a697aebb1926
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IPropertyProxyEESide
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 관련된 개체에 데이터를 볼 수는.  이 인터페이스는 형식 시각화 도우미에 대 한 지원의 일부입니다.  
  
## 구문  
  
```  
IPropertyProxyEESide : IUnknown  
```  
  
## 구현자 참고 사항  
 식 계산기는 형식을 시각화를 지원 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) 이 인터페이스를 가져올 수 있습니다.  호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 인터페이스를 얻을 수 있는 [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md) 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 다음 메서드는이 인터페이스에 의해 구현 됩니다.  
  
|메서드|설명|  
|---------|--------|  
|[InitSourceDataProvider](../../../extensibility/debugger/reference/ipropertyproxyeeside-initsourcedataprovider.md)|개체의 데이터에 액세스할 수 있도록 데이터 원본 공급자를 초기화 합니다.|  
|[GetManagedViewerCreationData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata.md)|개체의 어셈블리에 대 한 정보를 검색합니다.|  
|[GetInitialData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getinitialdata.md)|초기 데이터를 개체를 가져옵니다.|  
|[CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)|가 기존 데이터 저장소의 복사본을 만듭니다.|  
|[InPlaceUpdateObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md)|가 기존 데이터 저장소에 대 한 참조를 만듭니다.|  
|[ResolveAssemblyRef](../../../extensibility/debugger/reference/ipropertyproxyeeside-resolveassemblyref.md)|이 개체를 포함 하는 어셈블리의 컨텍스트에서 특정 어셈블리에 대 한 정보를 검색 합니다.|  
  
## 설명  
 형식을 시각화 도우미가이 인터페이스에 속하는 개체와 연관 된 값에 액세스 하려면이 인터페이스를 사용 합니다.  데이터를 통해 액세스할 수 있는 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 데이터의 읽기 전용 뷰를 제공 하는 인터페이스.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)