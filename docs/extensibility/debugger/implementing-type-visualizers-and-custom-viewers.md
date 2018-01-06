---
title: "시각화 도우미 형식 및 사용자 지정 뷰어를 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: abef18c0-8272-4451-b82a-b4624edaba7d
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 301c0311b8398ae14b36fedca5653d607b3274c0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-type-visualizers-and-custom-viewers"></a>시각화 도우미 형식 및 사용자 지정 뷰어를 구현합니다.
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 시각화 도우미 형식 및 사용자 지정 뷰어를 사용 숫자의 간단한 16 진수 덤프 보다 의미 있는 방식으로 특정 형식의 데이터를 볼 수 있습니다. 식 계산기 (EE)에서는 사용자 지정 뷰어를 특정 유형의 변수 또는 데이터에 연결할 수 있습니다. 이러한 사용자 지정 뷰어는 EE에서 구현 됩니다. EE 다른 공급 업체 또는 최종 사용자도 수행할 수 있는 외부 형식 시각화 도우미도 지원할 수 있습니다.  
  
## <a name="discussion"></a>토론  
  
### <a name="type-visualizers"></a>형식 시각화 도우미  
 Visual Studio는 조사식 창에 표시 되는 형식 시각화 도우미 및 모든 개체에 대 한 사용자 지정 뷰어 목록에 대 한 요청입니다. 그러한 목록은 해당 형식 시각화 도우미 및 사용자 지정 뷰어를 지원 하도록 하려는 모든 형식에 대 한 식 계산기 (EE)을 제공 합니다. 에 대 한 호출이 [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) 및 [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 형식 시각화 도우미 및 사용자 지정 뷰어에 액세스 하는 전체 프로세스를 시작 (참조 [Visualizing 및 데이터 보기](../../extensibility/debugger/visualizing-and-viewing-data.md)호출 시퀀스에 대 한 자세한 내용은).  
  
### <a name="custom-viewers"></a>사용자 지정 뷰어  
 사용자 지정 뷰어는 특정 데이터 형식에 대 한 EE에서 구현 되 고으로 표시 됩니다는 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) 인터페이스입니다. 해당 특정 사용자 지정 뷰어를 구현 하는 EE 실행 하는 경우에 사용할 수는 사용자 지정 뷰어는 유연 하 게 형식 시각화 도우미, 하지 않습니다. 사용자 지정 뷰어를 구현 하는 것이 형식 시각화 도우미에 대 한 지원을 구현 하는 보다 간단 합니다. 그러나 형식 시각화 도우미를 지 원하는 가장 유연성 최종 사용자에 게 자신의 데이터 시각화에 대 한 합니다. 이 설명의 나머지 부분에서는 형식 시각화 도우미만 관련 됩니다.  
  
## <a name="interfaces"></a>인터페이스  
 EE Visual Studio에서 사용할 수 있도록 형식 시각화 도우미를 지원 하기 위해 다음과 같은 인터페이스를 구현 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [시각화 및 데이터 보기](../../extensibility/debugger/visualizing-and-viewing-data.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)