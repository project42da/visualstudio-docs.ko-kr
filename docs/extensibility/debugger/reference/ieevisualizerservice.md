---
title: "IEEVisualizerService | Microsoft Docs"
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
  - "IEEVisualizerService"
helpviewer_keywords: 
  - "IEEVisualizerService 인터페이스"
ms.assetid: 3bdb124b-c582-47ba-b465-13c6a1cdb702
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# IEEVisualizerService
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스를 구현 하는 기능을 제공 하는 주요 메서드는 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 및 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스입니다.  
  
## 구문  
  
```  
IEEVisualizerService : IUnknown  
```  
  
## 구현자를 위한 정보  
 Visual Studio \(EE\) 형식 시각화 도우미를 지원 하기 위해 식 계산기를 허용 하도록이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 EE 호출 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md) 형식 시각화 도우미에 대 한 지원의 일환으로이 인터페이스를 가져올 수 있습니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[GetCustomViewerCount](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md)|이 서비스에 대 한 인식 하는 사용자 지정 뷰어의 수를 검색 합니다.|  
|[GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)|사용자 지정 뷰어 목록을 검색합니다.|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)|속성에 대 한 프록시 개체를 반환합니다.|  
|[GetValueDisplayStringCount](../../../extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount.md)|지정 된 속성 또는 필드에 대해 표시할 값 문자열의 수를 검색 합니다.|  
  
## 설명  
 IDE를 사용 하 여는 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 모든 사용자 지정 뷰어가 되는지 확인 하는 인터페이스 또는 속성에 대 한 시각화 도우미를 입력 합니다. 시각화 도우미 서비스를 만들어 \(으로 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)\), EE 하는 기능을 제공할 수는 `IDebugProperty3` 및 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스를 만들고 형식 시각화 도우미를 지원 하므로 \(및 지 원하는 보기 속성의 값 변경\).  
  
 그 자체가 구현, EE를 추가할 수는 EE에 사용자 지정 뷰어는 `CLSID`에서 반환 된 목록 끝에 이러한 사용자 지정 뷰어 중 s [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)합니다. 따라서 시각화 도우미 형식 및 고유한 사용자 지정 뷰어를 모두 지원 하도록는 EE 수 있습니다. 방금 수 있도록 [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) 더하기 모든 사용자 지정 뷰어를 반영 합니다.  
  
 참조 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md) 에 대 한 설명은 한 시각화 도우미와 뷰어 차이입니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)   
 [시각화 도우미 형식 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)