---
title: "시각화 및 데이터 보기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], viewing data
- debugging [Debugging SDK], visualizing data
ms.assetid: 699dd0f5-7569-40b3-ade6-d0fe53e832bc
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 14e5b641dc5bc51ac066f32332f3fdb2b01d1810
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="visualizing-and-viewing-data"></a>시각화 및 데이터 보기
신속 하 게 개발자에 게 의미 있는 방식으로 시각화 도우미 및 데이터를 표시 하는 사용자 지정 뷰어를 입력 합니다. 식 계산기 (EE) 수 제 3 자 형식 시각화 도우미를 지원 뿐만 아니라 자체 사용자 지정 뷰어를 제공 합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]형식 시각화 도우미와 사용자 지정 뷰어 수가 정해 집니다 개체의 형식과 호출 하 여는 [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) 메서드. Visual Studio를 호출 하는 하나 이상의 형식 시각화 도우미 또는 사용자 지정 뷰어에서 사용할 수는 [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 의 시각화 도우미와 뷰어 목록을 검색 하는 메서드입니다 (목록은 실제로 `CLSID`구현 하는 s는 시각화 도우미 및 뷰어가) 사용자에 게 표시 합니다.  
  
## <a name="supporting-type-visualizers"></a>지원 형식 시각화 도우미  
 인터페이스는 EE 형식 시각화 도우미를 지원 하기 위해 구현 해야 하는 여러 가지가 있습니다. 이러한 인터페이스 광범위 한 두 가지 범주로 구분할 수 있습니다: 나열 하는 형식 시각화 도우미 속성 데이터를 액세스 하는 것입니다.  
  
### <a name="listing-type-visualizers"></a>목록 형식 시각화 도우미  
 구현에서 형식 시각화 도우미를 나열는 EE 지원 `IDebugProperty3::GetCustomViewerCount` 및 `IDebugProperty3::GetCustomViewerList`합니다. 이러한 메서드는 해당 메서드를 호출 전달 [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) 및 [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)합니다.  
  
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) 호출 하 여 가져온 [CreateVisualizerService](../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)합니다. 이 방법을 사용 하려면는 [IDebugBinder3](../../extensibility/debugger/reference/idebugbinder3.md) 에서 가져온 인터페이스는 [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) 인터페이스에 전달 된 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)합니다. `IEEVisualizerServiceProvider::CreateVisualizerService`또한 필요는 [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) 및 [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) 인터페이스에 전달 된는 `IDebugParsedExpression::EvaluateSync`합니다. 만드는 데 필요한 최종 인터페이스는 `IEEVisualizerService` 인터페이스는는 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md) EE 구현 하는 인터페이스입니다. 이 인터페이스에서는 시각화 되는 속성을 변경할 수 있습니다. 모든 속성 데이터에 캡슐화 되어는 [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) 인터페이스에는 EE에서도 구현 됩니다.  
  
### <a name="accessing-property-data"></a>속성 데이터에 액세스  
 통해 이루어집니다 속성 데이터에 액세스 하는 [IPropertyProxyEESide](../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스입니다. 이 인터페이스를 가져오려면 Visual Studio 호출 [QueryInterface](/cpp/atl/queryinterface) 가져올 속성 개체에는 [IPropertyProxyProvider](../../extensibility/debugger/reference/ipropertyproxyprovider.md) 인터페이스 (구현 하는 동일한 개체에 구현 되는 [ IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) 인터페이스)를 호출 하는 [GetPropertyProxy](../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) 메서드는 `IPropertyProxyEESide` 인터페이스입니다.  
  
 내부 / 외부로 데이터를 모두 전달 되는 `IPropertyProxyEESide` 에 캡슐화 된 인터페이스는 [IEEDataStorage](../../extensibility/debugger/reference/ieedatastorage.md) 인터페이스입니다. 이 인터페이스는 바이트의 배열을 나타냅니다 하며 Visual Studio와 EE에 의해 구현 됩니다. 속성의 데이터를 변경할 때 Visual Studio 만듭니다는 `IEEDataStorage` 새 데이터 및 호출 보유 개체 [CreateReplacementObject](../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) 새를 얻기 위해 해당 데이터 개체와 함께 `IEEDataStorage` 개체를 사용 하는 차례로 에 전달 된 [InPlaceUpdateObject](../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md) 속성의 데이터를 업데이트 합니다. `IPropertyProxyEESide::CreateReplacementObject`구현 하는 자체 클래스를 인스턴스화하는 EE 허용는 `IEEDataStorage` 인터페이스입니다.  
  
## <a name="supporting-custom-viewers"></a>사용자 지정 뷰어를 지원합니다.  
 플래그 `DBG_ATTRIB_VALUE_CUSTOM_VIEWER` 에 설정 된는 `dwAttrib` 필드는 [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md) 구조 (에 대 한 호출에서 반환 된 [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)) 개체에 연결 하는 사용자 지정 뷰어 있음을 나타내기 위해 함께 합니다. 이 플래그가 설정 되 면 Visual Studio 가져옵니다는 [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) 에서 인터페이스는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스를 사용 하 여 [QueryInterface](/cpp/atl/queryinterface)합니다.  
  
 Visual Studio는 뷰어를 사용 하 여 사용자 지정 뷰어를 인스턴스화하는 사용자가 사용자 지정 뷰어를 선택 하는 경우 `CLSID` 제공한는 `IDebugProperty3::GetCustomViewerList` 메서드. Visual Studio에서 다음 호출 [DisplayValue](../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md) 사용자에 게 값을 표시 합니다.  
  
 일반적으로 `IDebugCustomViewer::DisplayValue` 데이터의 읽기 전용 보기를 표시 합니다. 데이터 변경에 있도록 EE 속성 개체에 변경 데이터를 지 원하는 사용자 지정 인터페이스를 구현 해야 합니다. `IDebugCustomViewer::DisplayValue` 메서드에서 사용자 지정이 인터페이스를 사용 하 여 데이터 변경을 지원 합니다. 사용자 지정 인터페이스에 대 한 메서드를 찾습니다는 `IDebugProperty2` 변수로 전달 된 인터페이스는 `pDebugProperty` 인수입니다.  
  
## <a name="supporting-both-type-visualizers-and-custom-viewers"></a>시각화 도우미와 사용자 지정 뷰어 입력 모두 지원  
 형식 시각화 도우미와 사용자 지정 뷰어에 EE 지원할 수는 [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) 및 [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 메서드. 첫째, EE가 제공 하 고 있는 사용자 지정 뷰어 중 수를에서 반환 된 값에 더하는 [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) 메서드. 둘째, EE 추가 `CLSID`에서 반환 된 목록에는 자체 사용자 지정 뷰어 중 s는 [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)   
 [형식 시각화 도우미 및 사용자 지정 뷰어](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)