---
title: "IEEVisualizerServiceProvider::CreateVisualizerService | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEEVisualizerServiceProvider::CreateVisualizerService"
helpviewer_keywords: 
  - "IEEVisualizerServiceProvider::CreateVisualizerService 메서드"
ms.assetid: f366f7c9-358d-46c8-993f-32ff86539833
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IEEVisualizerServiceProvider::CreateVisualizerService
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 시각화 도우미 서비스를 만듭니다.  
  
## 구문  
  
```cpp  
HRESULT CreateVisualizerService(  
   IDebugBinder*              binder,  
   IDebugSymbolProvider*      pSymProv,  
   IDebugAddress*             pAddress,  
   IEEVisualizerDataProvider* dataProvider,  
   IEEVisualizerService**     ppService  
);  
```  
  
```c#  
int CreateVisualizerService(  
   IDebugBinder binder,  
   IDebugSymbolProvider      pSymProv,  
   IDebugAddress             pAddress,  
   IEEVisualizerDataProvider dataProvider,  
   out IEEVisualizerService  ppService  
);  
```  
  
#### 매개 변수  
 `binder`  
 \[in\] [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 개체를 전달 합니다 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md).  
  
 `pSymProv`  
 \[in\] [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) 개체를 전달 합니다 `IDebugParsedExpression::EvaluateSync`.  
  
 `pAddress`  
 \[in\] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 개체를 전달 합니다 `IDebugParsedExression::EvaluateSync`.  
  
 `dataProvider`  
 \[in\] 구현 하는 개체는 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) 인터페이스 \(식 계산기에서 제공 됨\).  
  
 `ppService`  
 \[out\] 만들어진된 서비스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 `binder`, `pSymProv`, 및 `pAddress` 매개 변수가 한 모두 전달 하는 `IDebugParsedExpression::EvaluateSync` 메서드.  `CreateVisualizerService`호출 하는 `IDebugParsedExpression::EvaluateSync` 형식 시각화 도우미에 대 한 식 계산기의 지원의 일환으로 합니다.  
  
## 참고 항목  
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)