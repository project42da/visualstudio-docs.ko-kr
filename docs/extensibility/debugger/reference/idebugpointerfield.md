---
title: "IDebugPointerField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPointerField"
helpviewer_keywords: 
  - "IDebugPointerField 인터페이스"
ms.assetid: d51bd5b2-f18e-4e27-b4fb-e6f652fbf635
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugPointerField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 포인터 형식을 나타냅니다.  
  
## 구문  
  
```  
IDebugPointerField : IDebugContainerField  
```  
  
## 구현자 참고 사항  
 이 인터페이스에 대 한 포인터를 나타내는 기호 공급자를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 사용 [QueryInterface](/visual-cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수 있는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 경우 인터페이스 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 반환 `FIELD_TYPE_POINTER`.  
  
## 메서드에서 Vtable 순서  
 메서드 외에 `IDebugField` 및 `IDebugContainerField` 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetDereferencedField](../../../extensibility/debugger/reference/idebugpointerfield-getdereferencedfield.md)|반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 포인터의 대상을 설명 하는.|  
  
## 설명  
 배열 표기법을 사용 하는 경우 C\/c \+ \+의 컨테이너에 대 한 포인터를 수 있습니다.  예를 들어, `char *pString`, `pString` 에 대 한 포인터 형식이 있는 `char`.  `pString[3]`형식에 대 한 포인터를 포함 하는 컨테이너의 `char` 는 해당 컨테이너의 네 번째 요소를 참조 합니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)