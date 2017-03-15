---
title: "시각화 도우미 형식 및 사용자 지정 뷰어를 구현합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 사용자 지정 뷰어"
  - "디버깅 [디버깅 SDK] 형식 시각화 도우미"
ms.assetid: abef18c0-8272-4451-b82a-b4624edaba7d
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 시각화 도우미 형식 및 사용자 지정 뷰어를 구현합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 형식 시각화 도우미 및 사용자 지정 뷰어 숫자의 16 진수 덤프 간단한 보다 의미 있는 방식으로 특정 형식의 데이터를 볼 수 없도록 합니다. 식 계산기 \(EE\)에서는 사용자 지정 뷰어를 특정 유형의 변수 또는 데이터에 연결할 수 있습니다. 이러한 사용자 지정 뷰어는 EE에서 구현 됩니다. EE도 다른 공급 업체 또는 최종 사용자도 수행할 수 있는 외부 형식 시각화 도우미를 지원할 수 있습니다.  
  
## 토론  
  
### 형식 시각화 도우미  
 Visual Studio 시각화 도우미 형식 및 모든 개체에 대 한 사용자 지정 뷰어 조사식 창에 표시 되는 목록을 요구 합니다. 시각화 도우미 형식 및 사용자 지정 뷰어를 지원 하려는 모든 형식에 대 한 이러한 목록을 제공 하는 식 계산기 \(EE\). 에 대 한 호출이 [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) 및 [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 형식 시각화 도우미 및 사용자 지정 뷰어를 액세스 하는 전체 과정을 시작 \(참조 [시각화 및 데이터 보기](../../extensibility/debugger/visualizing-and-viewing-data.md) 호출 시퀀스에 대 한 내용은\).  
  
### 사용자 지정 뷰어  
 사용자 지정 뷰어는 특정 데이터 형식에 대 한 EE에서 구현 되 고 표시 됩니다는 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) 인터페이스입니다. 사용자 지정 뷰어는 시각화 도우미를 형식으로 융통성 EE 해당 특정 사용자 지정 뷰어를 구현 하는 실행 되는 경우에 사용할 수 있기 때문입니다. 사용자 지정 뷰어를 구현 하는 것은 형식 시각화 도우미에 대 한 지원을 구현 하는 보다 간단 합니다. 그러나 형식 시각화 도우미를 지 원하는 유연 하 게 최대 최종 사용자에 게 자신의 데이터를 시각화 하기 위해. 이 기사의 나머지 부분에서는 형식 시각화 도우미만 문제가 발생합니다.  
  
## 인터페이스  
 EE 형식 시각화 도우미를 Visual Studio에서 사용할 수 있도록 지원 하기 위해 다음과 같은 인터페이스를 구현 합니다.  
  
-   [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)  
  
-   [IPropertyProxyEESide](../../extensibility/debugger/reference/ipropertyproxyeeside.md)  
  
-   [IPropertyProxyProvider](../../extensibility/debugger/reference/ipropertyproxyprovider.md)  
  
-   [IEEDataStorage](../../extensibility/debugger/reference/ieedatastorage.md)  
  
-   [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md)  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
 EE 형식 시각화 도우미를 지원 하기 위해 다음 인터페이스를 사용 합니다.  
  
-   [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)  
  
-   [IEEVisualizerServiceProvider](../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)  
  
-   [IDebugBinder3](../../extensibility/debugger/reference/idebugbinder3.md)  
  
## 참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [시각화 및 데이터 보기](../../extensibility/debugger/visualizing-and-viewing-data.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)