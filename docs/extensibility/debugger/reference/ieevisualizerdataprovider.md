---
title: "IEEVisualizerDataProvider | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEEVisualizerDataProvider"
helpviewer_keywords: 
  - "IEEVisualizerDataProvider 인터페이스"
ms.assetid: 5fdfe6e3-b94e-4edb-acc5-41d8773d8ca5
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# IEEVisualizerDataProvider
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스는 형식 시각화 도우미를 통해 개체의 값을 변경 하는 기능을 제공 합니다.  
  
## 구문  
  
```  
IEEVisualizerDataProvider : IUnknown  
```  
  
## 구현자를 위한 정보  
 식 계산기는 형식 시각화 도우미를 통해 속성 개체에 수정 하 고 데이터를 지원 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스는 만드는 데 사용 되는 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) 개체에 대 한 호출을 통해 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)합니다. 자세한 내용은 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)을 참조하세요.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[CanSetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-cansetobjectforvisualizer.md)|개체 \(및 그 이후에, 해당 값\)을 업데이트할 수 인지 여부를 확인 하는이 시각화 도우미를 나타내는입니다.|  
|[GetNewObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-getnewobjectforvisualizer.md)|이 시각화 도우미에 대 한 개체의 재평가 강제로 수행 합니다.|  
|[GetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-getobjectforvisualizer.md)|이 시각화 도우미 \(계산은 필요 하지 않은 수행\)에 대 한 기존 개체를 가져옵니다.|  
|[SetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-setobjectforvisualizer.md)|이 시각화 도우미를 변경 하 여 시각화 도우미를 표시 하는 값에 대 한 개체를 업데이트 합니다.|  
  
## 설명  
 시각화 도우미 서비스 \(여는 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) 인터페이스를 반환한 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)\) 구현 하는 개체에 대 한 참조를 유지는 `IEEVisualizerDataProvider` 인터페이스입니다. 결과적으로 `IEEVisualizerDataProvider` 인터페이스를 구현 하는 동일한 개체에서 구현 하지 않아야는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 해당 개체에 대 한 참조를 유지 하는 경우는 `IEEVisualizerService` 개체: 순환 참조가 발생 하 고 교착 상태가 발생 하는 개체가 소멸 됩니다. 구현 하는 것이 좋습니다 `IEEVisualizerDataProvider` 를 별도 개체에는 `IDebugProperty2` 호출 하지 않고 대리자 개체 `IUnknown::AddRef` 에 있습니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)