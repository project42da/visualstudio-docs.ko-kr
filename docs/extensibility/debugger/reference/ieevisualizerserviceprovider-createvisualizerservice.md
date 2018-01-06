---
title: IEEVisualizerServiceProvider::CreateVisualizerService | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEEVisualizerServiceProvider::CreateVisualizerService
helpviewer_keywords: IEEVisualizerServiceProvider::CreateVisualizerService method
ms.assetid: f366f7c9-358d-46c8-993f-32ff86539833
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b9c34f5b11aed9ed51ca10f662ea161d792e54b6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ieevisualizerserviceprovidercreatevisualizerservice"></a>IEEVisualizerServiceProvider::CreateVisualizerService
이 메서드는 시각화 도우미 서비스를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateVisualizerService(  
   IDebugBinder*              binder,  
   IDebugSymbolProvider*      pSymProv,  
   IDebugAddress*             pAddress,  
   IEEVisualizerDataProvider* dataProvider,  
   IEEVisualizerService**     ppService  
);  
```  
  
```csharp  
int CreateVisualizerService(  
   IDebugBinder binder,  
   IDebugSymbolProvider      pSymProv,  
   IDebugAddress             pAddress,  
   IEEVisualizerDataProvider dataProvider,  
   out IEEVisualizerService  ppService  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `binder`  
 [in] [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 에 전달 된 개체 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)합니다.  
  
 `pSymProv`  
 [in] [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) 에 전달 된 개체 `IDebugParsedExpression::EvaluateSync`합니다.  
  
 `pAddress`  
 [in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 에 전달 된 개체 `IDebugParsedExression::EvaluateSync`합니다.  
  
 `dataProvider`  
 [in] 구현 하는 개체는 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) 인터페이스 (식 계산기가 제공).  
  
 `ppService`  
 [out] 생성된 된 서비스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 `binder`, `pSymProv`, 및 `pAddress` 매개 변수 모두에 전달 된는 `IDebugParsedExpression::EvaluateSync` 메서드. `CreateVisualizerService`에서만 호출할 `IDebugParsedExpression::EvaluateSync` 형식 시각화 도우미에 대 한 식 계산기의 지원의 일환으로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)