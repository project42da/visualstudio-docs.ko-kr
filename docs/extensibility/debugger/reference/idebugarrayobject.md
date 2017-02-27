---
title: "IDebugArrayObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugArrayObject"
helpviewer_keywords: 
  - "IDebugArrayObject 메서드"
ms.assetid: a1c8e77e-dee1-4748-a516-6ab032a8f54f
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugArrayObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스는 배열 개체를 나타냅니다.  
  
## 구문  
  
```  
IDebugArrayObject : IDebugObject  
```  
  
## 구현자를 위한 정보  
 식 계산기를 나타내는 배열을이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스를 사용 하 여이 인터페이스를 가져올 수 [QueryInterface](/visual-cpp/atl/queryinterface) 개체가 나타내는 배열입니다.  
  
## Vtable 순서의 메서드  
 메서드 외에도 `IDebugObject` 인터페이스, 다음 방법에서 구현 되는 `IDebugArrayObject` 인터페이스입니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md)|배열의 요소 수를 가져옵니다.|  
|[GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)|배열의 요소를 가져옵니다.|  
|[GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)|배열의 모든 요소를 가져옵니다.|  
|[GetRank](../../../extensibility/debugger/reference/idebugarrayobject-getrank.md)|배열의 차수를 가져옵니다.|  
|[GetDimensions](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md)|배열의 크기를 가져옵니다.|  
  
## 설명  
 식 계산기는이 인터페이스를 사용 하 여 배열은 구문 분석 트리를 나타냅니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)