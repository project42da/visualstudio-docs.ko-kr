---
title: "IDebugMethodField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugMethodField"
helpviewer_keywords: 
  - "IDebugMethodField 인터페이스"
ms.assetid: a7dc9030-fc98-4cf1-b943-37a4003300b6
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugMethodField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 메서드를 설명합니다.  
  
## 구문  
  
```  
IDebugMethodField : IDebugContainerField  
```  
  
## 구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스는 구현에서 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스입니다.  이 인터페이스에는 메서드를 제공 하는 특수화입니다.  
  
## 호출자에 대 한 참고 사항  
 사용 [QueryInterface](/visual-cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수 있는 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 경우 인터페이스 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 반환 `FIELD_TYPE_METHOD`.  또한 메서드를 [GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md), [GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md), 및 [EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md), 모든 반환은 `IDebugMethodField` 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 메서드 외에 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 및 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)|메서드의 매개 변수에 대 한 열거자를 만듭니다.|  
|[GetThis](../../../extensibility/debugger/reference/idebugmethodfield-getthis.md)|"This"이 포인터를 메서드를 포함 하는 개체를 가져옵니다.|  
|[EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)|모든 지역 변수는 메서드의 대 한 열거자를 만듭니다.|  
|[EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)|선택한 지역 변수에 메서드는 열거자를 만듭니다.|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugmethodfield-iscustomattributedefined.md)|특정 사용자 지정 특성의 정의 여부를 결정 합니다.|  
|[EnumStaticLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumstaticlocals.md)|정적 지역 변수는 메서드에 대 한 열거자를 만듭니다.|  
|[GetGlobalContainer](../../../extensibility/debugger/reference/idebugmethodfield-getglobalcontainer.md)|전역 컨테이너를 메서드를 가져옵니다.|  
|[EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)|메서드를 호출 하는 데 필요한 각 인수의 형식에 대 한 열거자를 만듭니다.|  
  
## 설명  
 메서드 매개 변수는 지역 변수를 포함할 수 있습니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)