---
title: "IEnumDebugAddresses | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugAddresses"
helpviewer_keywords: 
  - "IEnumDebugAddresses 인터페이스"
ms.assetid: 5f6f6751-e6d8-4c5a-8e81-414b6e5d8cc5
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugAddresses
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스를 구현 하는 개체의 컬렉션을 나타냅니다는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
## 구문  
  
```  
IEnumDebugAdresses : IUnknown  
```  
  
## 구현자 참고 사항  
 구현 하는 개체 집합을 제공 하는 기호 공급자가이 인터페이스를 구현할 수 있는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  표준 COM 열거형의 존재 때문에 않음을 유의 [GetCount](../../../extensibility/debugger/reference/ienumdebugaddresses-getcount.md) 메서드가 있습니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스가 반환 하는 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md) 및 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md).  
  
## 메서드에서 Vtable 순서  
 이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugaddresses-next.md)|다음 검색 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 열거형에서 개체입니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugaddresses-skip.md)|지정 된 개수의 항목을 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugaddresses-reset.md)|열거형의 첫 번째 항목으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugaddresses-clone.md)|현재 열거형의 복사본을 검색합니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugaddresses-getcount.md)|열거형의 항목 수를 검색합니다.|  
  
## 설명  
 이 인터페이스는 일반적으로 식 계산기에 제공 하는 적절 한 주소를 확인 하는 데 도움이 되는 디버그 엔진에서 사용 됩니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)