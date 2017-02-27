---
title: "IEEVisualizerServiceProvider | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEEVisualizerServiceProvider"
helpviewer_keywords: 
  - "IEEVisualizerServiceProvider 인터페이스"
ms.assetid: 859d1a51-1c65-4c8b-ae74-3b74b181ebcd
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# IEEVisualizerServiceProvider
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스는 IDE에 대 한 형식 시각화 도우미 작업을 처리 하는 데 사용 되는 시각화 도우미 서비스를 만들 수 있는 메서드에 액세스할 수 있습니다.  
  
## 구문  
  
```  
IEEVisualizerServiceProvider : IUnknown  
```  
  
## 구현자를 위한 정보  
 그러면 클래스 Id를 제공 하는 데 사용 되는 시각화 도우미 서비스 개체를 만들려면이 인터페이스를 구현 하는 visual Studio \(`CLSID`s\) Visual Studio IDE에 시각화 도우미 형식입니다.  
  
## 호출자에 대 한 참고 사항  
 식 계산기 \(EE\) 호출 [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md) 이 인터페이스를 가져올 수 있습니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)|시각화 도우미 서비스를 만듭니다.|  
  
## 설명  
 `IEEVisualizerServiceProvider` 인터페이스의 구현 중에 가져온 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)합니다. 시각화 도우미가이 인터페이스를 만드는 서비스를는 기능을 제공 하는 데 사용 되는 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) EE 구현 담당 하는 인터페이스입니다. EE 구현을 담당 이기도 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) 보고 속성의 값을 수정 하는 형식 시각화 도우미를 수 있는 인터페이스입니다.  
  
 참조 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md) 이러한 인터페이스 작용 하는 방법에 대 한 내용은 합니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)