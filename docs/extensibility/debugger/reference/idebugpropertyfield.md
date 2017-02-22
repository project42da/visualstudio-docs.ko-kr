---
title: "IDebugPropertyField | Microsoft Docs"
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
  - "IDebugPropertyField"
helpviewer_keywords: 
  - "IDebugPropertyField 인터페이스"
ms.assetid: b50edb2c-fb8d-4def-993d-17d23d2027c1
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugPropertyField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 속성을 설정 하는 함수를 제공 합니다.  
  
## 구문  
  
```  
IDebugPropertyField : IDebugContainerField  
```  
  
## 구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스는 구현에서 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md).  이 인터페이스는 클래스에 속성의 개념을 지 원하는 특수화입니다.  
  
## 호출자에 대 한 참고 사항  
 사용 [QueryInterface](/visual-cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수 있는 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 경우 인터페이스는 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 메서드가 반환 `FIELD_KIND_PROP`.  
  
## 메서드에서 Vtable 순서  
 메서드 외에 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 및 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md)|이 속성을 가져오는 메서드를 가져옵니다.|  
|[GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md)|속성을 설정 하는 메서드를 가져옵니다.|  
  
## 설명  
 관리 되는 코드 개념은 속성과 변수로 처리 하는 메서드를 나타냅니다.  등록 정보는 관리 되지 않는 c \+ \+에서는 존재 하지 않습니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)