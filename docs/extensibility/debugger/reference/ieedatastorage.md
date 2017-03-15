---
title: "IEEDataStorage | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEEDataStorage"
helpviewer_keywords: 
  - "IEEDataStorage 인터페이스"
ms.assetid: 704e932d-2325-410e-89c4-ce88c6ec19da
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IEEDataStorage
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 바이트 배열을 나타냅니다.  
  
## 구문  
  
```  
IEEDataStorage : IUnknown  
```  
  
## 구현자 참고 사항  
 식 계산기 \(EE\) 바이트 배열을 나타내는 데이 인터페이스를 구현 합니다. \(형식을 시각화 도우미로 검색을 통해 데이터를 변경 하는 데 사용 되는 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스\)입니다.  EE 일반적으로 외부 형식 시각화를 지원 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 메서드는 `IPropertyProxyEESide` 인터페이스로 모든이 인터페이스를 반환 합니다.  호출 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) 얻을 수 있는 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스입니다.  호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 인터페이스를 얻을 수 있는 [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md) 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 `IEEDataStorage` 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)|지정 된 제공 된 버퍼에 데이터 바이트 수를 검색합니다.|  
|[GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)|사용할 수 있는 데이터 바이트 수를 검색합니다.|  
  
## 설명  
 이 인터페이스 형식을 시각화 도우미에서 특정 개체에서 보유 하는 데이터 액세스에 사용 됩니다.  데이터 형식 시각화 도우미 방식으로 사용자에 게 제공 하는 데 필요한 것에서 조작할 수 있도록 바이트 배열로 처리 됩니다.  
  
 보다 일반적으로, 사용자 지정 뷰어는 사용자 지정 인터페이스를 사용 합니다 있지만 사용자 지정 뷰어도이 인터페이스를 원하는 경우 사용할 수 있습니다 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md) 또는 [GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md) \(string 지향 데이터에 대 한\).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)