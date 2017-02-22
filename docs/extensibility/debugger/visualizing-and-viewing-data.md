---
title: "시각화 및 데이터 보기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 데이터 보기"
  - "디버깅 [디버깅 SDK], 데이터 시각화"
ms.assetid: 699dd0f5-7569-40b3-ade6-d0fe53e832bc
caps.latest.revision: 20
caps.handback.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
---
# 시각화 및 데이터 보기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

형식 시각화 하 고 신속 하 게 개발자에 게 의미 있는 방식으로 사용자 지정 뷰어에서 데이터를 표시 합니다.  식 계산기 \(EE\) 수 있습니다 타사 형식 시각화 도우미를 지원으로 자체 사용자 지정 뷰어를 제공 합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]형식 시각화와 사용자 지정 뷰어를 호출 하 여 개체의 형식에 관련 된 결정은 [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) 메서드.  사용할 수 있을 경우 하나 이상의 형식 시각화 또는 사용자 지정 뷰어를 Visual Studio 호출 하는 [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 의 시각화와 보는 사람 목록을 검색 하는 메서드 \(실제로, `CLSID`시각화 및 뷰어를 구현 하는 s\) 다음 사용자에 게 표시 합니다.  
  
## 형식을 시각화 도우미를 지원합니다.  
 EE 형식을 시각화를 지원 하기 위해 구현 해야 하는 인터페이스에는 여러 가지가 있습니다.  이러한 인터페이스는 두 개의 광범위 한 범주로 나눌 수 합니다: 형식 시각화 및 속성 데이터에 액세스 하는 것입니다.  
  
### 형식을 시각화 도우미를 나열합니다.  
 EE를 지 원하는 목록 형식을 시각화 구현에 `IDebugProperty3::GetCustomViewerCount` 및 `IDebugProperty3::GetCustomViewerList`.  이러한 메서드를 해당 메서드를 호출 전달 [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) 및 [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md).  
  
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) 를 호출 하 여 가져온 [CreateVisualizerService](../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md).  이 방법을 사용 해야는 [IDebugBinder3](../../extensibility/debugger/reference/idebugbinder3.md) 에서 가져온 인터페이스는 [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) 인터페이스를 전달 합니다 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md).  `IEEVisualizerServiceProvider::CreateVisualizerService`또한 필요에 [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) 및 [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) 인터페이스에 전달 된 `IDebugParsedExpression::EvaluateSync`.  마지막 인터페이스를 만드는 데 필요한는 `IEEVisualizerService` 인터페이스는 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md) EE를 구현 하는 인터페이스.  이 인터페이스는 시각화 되 고 있는 속성을 변경할 수 있습니다.  모든 속성 데이터가 캡슐화 되는 [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) 는 EE에서 구현 되는 인터페이스입니다.  
  
### 속성 데이터에 액세스  
 속성 데이터 액세스를 통해 수행 되는 [IPropertyProxyEESide](../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스입니다.  이 인터페이스를 구하려면 Visual Studio 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 가져올 속성 개체에는 [IPropertyProxyProvider](../../extensibility/debugger/reference/ipropertyproxyprovider.md) 인터페이스 \(구현 하는 동일한 개체에서 구현 되는 [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) 인터페이스\) 호출의 [GetPropertyProxy](../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) 얻을 수 있는 방법을 `IPropertyProxyEESide` 인터페이스.  
  
 내부 및 외부로 전달 되는 모든 데이터는 `IPropertyProxyEESide` 인터페이스에 캡슐화 되는 [IEEDataStorage](../../extensibility/debugger/reference/ieedatastorage.md) 인터페이스입니다.  이 인터페이스는 바이트 배열을 나타내는 및 Visual Studio 및 EE 구현 합니다.  속성의 데이터가 변경 된 경우 Visual Studio 만듭니다는 `IEEDataStorage` 새 데이터 및 호출을 포함 하는 개체 [CreateReplacementObject](../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) 새 얻기 위해 해당 데이터 개체와 `IEEDataStorage` 결과적으로 전달 된 개체 [InPlaceUpdateObject](../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md) 속성의 데이터를 업데이트할 수 있습니다.  `IPropertyProxyEESide::CreateReplacementObject`EE 구현 클래스 자체를 인스턴스화할 수 있습니다 해당 `IEEDataStorage` 인터페이스입니다.  
  
## 사용자 지정 뷰어를 지원합니다.  
 플래그 `DBG_ATTRIB_VALUE_CUSTOM_VIEWER` 설정 되어 있는 `dwAttrib` 필드는 [DEBUG\_PROPERTY\_INFO](../../extensibility/debugger/reference/debug-property-info.md) 구조 \(호출에 의해 반환 [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)\) 개체에 연결 된 사용자 지정 뷰어 있음을 나타내기 위해.  이 플래그가 설정 되 면 Visual Studio 가져옵니다는 [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) 의 인터페이스는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스를 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface).  
  
 사용자 지정 뷰어는 사용자가 선택 하는 경우 사용자 지정 뷰어는 뷰어를 사용 하 여 Visual Studio 인스턴스화합니다 `CLSID` 에서 제공 되는 `IDebugProperty3::GetCustomViewerList` 메서드.  Visual Studio 호출 하 고 [DisplayValue](../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md) 사용자에 게 값을 표시 합니다.  
  
 일반적으로, `IDebugCustomViewer::DisplayValue` 데이터의 읽기 전용 뷰를 표시 합니다.  데이터 변경 내용을 허용 하려면 EE 속성 개체에 변경 되는 데이터를 지 원하는 사용자 지정 인터페이스를 구현 해야 합니다.  `IDebugCustomViewer::DisplayValue` 메서드가이 사용자 지정 인터페이스를 사용 하 여 데이터를 변경할 수 있습니다.  메서드는 사용자 지정 인터페이스에 대 한 조회 `IDebugProperty2` 에서 인터페이스가 전달로 `pDebugProperty` 인수입니다.  
  
## 시각화 및 사용자 지정 뷰어 입력 모두 지원  
 형식 시각화와 사용자 지정 뷰어에 EE 지원할 수 있는 [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) 및 [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 메서드.  첫째, 반환 된 값을 수를 제공 하 여 사용자 지정 뷰어 EE를 추가 [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) 메서드가 있습니다.  둘째, EE 추가 `CLSID`s는 자체 사용자 지정 보기 권한자 목록에서 반환 하는 [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) 메서드.  
  
## 참고 항목  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)   
 [시각화 도우미 형식 및 사용자 지정 뷰어](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)