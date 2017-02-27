---
title: "IEnumDebugFields | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugFields"
helpviewer_keywords: 
  - "IEnumDebugFields 인터페이스"
ms.assetid: 403c2a51-3ba5-431f-a1dd-2f3b2046c00c
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IEnumDebugFields
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스를 구현 하는 개체의 컬렉션을 나타냅니다는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스입니다.  
  
## 구문  
  
```  
IEnumDebugFields : IUnknown  
```  
  
## 구현자 참고 사항  
 구현 하는 개체 집합을 제공 하는 기호 공급자가이 인터페이스를 구현할 수 있는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스입니다.  표준 COM 열거형의 존재 때문에 않음을 유의 [GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md) 메서드가 있습니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스가 반환 하는 [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md) 및 [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md).  
  
## 메서드에서 Vtable 순서  
 이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugfields-next.md)|다음 검색 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 열거형에서 개체입니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugfields-skip.md)|지정 된 개수의 항목을 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugfields-reset.md)|열거형의 첫 번째 항목으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugfields-clone.md)|현재 열거형의 복사본을 검색합니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)|열거형의 항목 수를 검색합니다.|  
  
## 설명  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)   
 [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)