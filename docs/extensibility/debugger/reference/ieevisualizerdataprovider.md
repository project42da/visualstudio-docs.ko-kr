---
title: IEEVisualizerDataProvider | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IEEVisualizerDataProvider
helpviewer_keywords:
- IEEVisualizerDataProvider interface
ms.assetid: 5fdfe6e3-b94e-4edb-acc5-41d8773d8ca5
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: edf2cfe689caa58e1c0402a91fa31237cb2c7215
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ieevisualizerdataprovider"></a>IEEVisualizerDataProvider
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스는 형식 시각화 도우미를 통해 개체의 값을 변경 하는 기능을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEEVisualizerDataProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 식 계산기는 형식 시각화 도우미를 통해 속성 개체에서 데이터 수정을 지원 하도록이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스는 만드는 데 사용 되는 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) 호출을 통해 개체 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)합니다. 참조 [Visualizing 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md) 내용을 확인 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CanSetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-cansetobjectforvisualizer.md)|개체 (및 그 후 해당 값)을 업데이트할 수 인지 여부를 확인 하는이 시각화 도우미를 나타내는입니다.|  
|[GetNewObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-getnewobjectforvisualizer.md)|이 시각화 도우미에 대 한 개체의 다시 검사를 강제로 수행합니다.|  
|[GetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-getobjectforvisualizer.md)|이 시각화 도우미 (평가 수행)에 대 한 기존 개체를 가져옵니다.|  
|[SetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-setobjectforvisualizer.md)|시각화 도우미를 표시 하는 값 변경 하 여이 시각화 도우미에 대 한 개체를 업데이트 합니다.|  
  
## <a name="remarks"></a>설명  
 시각화 도우미 서비스 (로 표현 되는 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) 인터페이스를 반환한 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)) 구현 하는 개체에 대 한 참조 유지는 `IEEVisualizerDataProvider` 인터페이스 . 결과적으로 `IEEVisualizerDataProvider` 인터페이스를 구현 하는 동일한 개체에서 구현 하지 않아야는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 해당 개체에 대 한 참조를 유지 하는 경우는 `IEEVisualizerService` 개체: 순환 참조가 결과 교착 상태는 개체가 소멸 되 면 발생 합니다. 구현 하는 것이 좋습니다 `IEEVisualizerDataProvider` 를 별도 개체에는 `IDebugProperty2` 호출 하지 않고 대리자 개체 `IUnknown::AddRef` 에 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [데이터 시각화 및 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)