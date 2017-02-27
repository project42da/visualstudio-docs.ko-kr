---
title: "IDebugClassField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugClassField"
helpviewer_keywords: 
  - "IDebugClassField 인터페이스"
ms.assetid: 49358cbc-8973-4862-9dcc-79b1248e6712
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugClassField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 클래스를 형식으로 나타냅니다.  
  
## 구문  
  
```  
IDebugClassField : IDebugContainerField  
```  
  
## 구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스는 구현에서 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스입니다.  이 인터페이스에는 클래스 형식을 나타내는 특수화입니다.  
  
## 호출자에 대 한 참고 사항  
 인터페이스의 수 있는 인터페이스를 포함 하 여이 반환할 수 있는 방법을 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md), [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md), 및 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md).  또한 사용할 수 있습니다 [QueryInterface](/visual-cpp/atl/queryinterface) 이 인터페이스에서 얻을 수 있는 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 경우 인터페이스는 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 메서드에서 반환 된 플래그 `FIELD_TYPE_CLASS`.  
  
## 메서드에서 Vtable 순서  
 메서드 외에 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 및 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스,이 인터페이스는 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[EnumBaseClasses](../../../extensibility/debugger/reference/idebugclassfield-enumbaseclasses.md)|이 클래스의 기본 클래스에 대 한 열거자를 만듭니다.|  
|[DoesInterfaceExist](../../../extensibility/debugger/reference/idebugclassfield-doesinterfaceexist.md)|특정 인터페이스는 클래스에 정의 되어 있는지 확인 합니다.|  
|[EnumNestedClasses](../../../extensibility/debugger/reference/idebugclassfield-enumnestedclasses.md)|이 클래스의 중첩된 클래스에 대 한 열거자를 만듭니다.|  
|[GetEnclosingClass](../../../extensibility/debugger/reference/idebugclassfield-getenclosingclass.md)|이 클래스를 포함 하는 클래스를 가져옵니다.|  
|[EnumInterfacesImplemented](../../../extensibility/debugger/reference/idebugclassfield-enuminterfacesimplemented.md)|이 클래스에 의해 구현 된 인터페이스에 대 한 열거자를 만듭니다.|  
|[EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md)|이 클래스의 생성자에 대 한 열거자를 만듭니다.|  
|[GetDefaultIndexer](../../../extensibility/debugger/reference/idebugclassfield-getdefaultindexer.md)|기본 인덱서 이름을 가져옵니다.|  
|[EnumNestedEnums](../../../extensibility/debugger/reference/idebugclassfield-enumnestedenums.md)|이 클래스의 중첩 된 열거자에 대 한 열거자를 만듭니다.|  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)