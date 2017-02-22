---
title: "IPropertyProxyProvider | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IPropertyProxyProvider"
helpviewer_keywords: 
  - "IPropertyProxyProvider 인터페이스"
ms.assetid: 52e9f7fc-6fe0-4d23-890b-5673dca8c3cb
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IPropertyProxyProvider
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 보기 및 개체의 데이터를 변경 하는 프록시 인터페이스를 제공 합니다.  
  
## 구문  
  
```  
IPropertyProxyProvider : IUnknown  
```  
  
## 구현자 참고 사항  
 식 계산기 \(EE\)이이 인터페이스를 구현 하는 동일한 개체에서 구현에서 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 인터페이스는 EE 지원 형식 시각화 도우미의 일환으로.  
  
## 호출자에 대 한 참고 사항  
 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugProperty3` 이 인터페이스를 가져올 수 있는 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 `IPropertyProxyProvider` 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)|개체의 데이터를 볼 수 있는 속성 프록시 인터페이스를 검색 합니다.|  
  
## 설명  
 이 인터페이스의 구현을 EE 구현 되지만 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) 일반적으로 처리 하 고 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md).  참조 하십시오 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md) IEEVisualizerService 인터페이스를 얻기 위한 자세한 내용은.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)   
 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)   
 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)