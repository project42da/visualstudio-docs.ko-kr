---
title: "IDebugArrayField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugArrayField"
helpviewer_keywords: 
  - "IDebugArrayField 인터페이스"
ms.assetid: 9667b0a5-4295-46cc-9388-b75c1350be15
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugArrayField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 배열 기호 또는 형식에 설명합니다.  
  
## 구문  
  
```  
IDebugArrayField : IDebugContainerField  
```  
  
## 구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스는 구현에서 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스입니다.  이 인터페이스는 array 개체를 나타내는 특수화입니다.  
  
## 호출자에 대 한 참고 사항  
 사용 [QueryInterface](/visual-cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수 있는 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 경우 인터페이스 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 플래그를 반환 합니다. `FIELD_TYPE_ARRAY`.  
  
## 메서드에서 Vtable 순서  
 메서드 외에 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 및 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스,이 인터페이스는 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetNumberOfElements](../../../extensibility/debugger/reference/idebugarrayfield-getnumberofelements.md)|배열에서 요소의 개수를 가져옵니다.|  
|[GetElementType](../../../extensibility/debugger/reference/idebugarrayfield-getelementtype.md)|요소 형식을에 배열에 가져옵니다.|  
|[GetRank](../../../extensibility/debugger/reference/idebugarrayfield-getrank.md)|배열의 차수를 가져옵니다.|  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)