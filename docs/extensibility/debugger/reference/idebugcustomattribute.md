---
title: "IDebugCustomAttribute | Microsoft Docs"
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
  - "IDebugCustomAttribute"
helpviewer_keywords: 
  - "IDebugCustomAttribute 인터페이스"
ms.assetid: c5ae41e9-00b9-4cca-871d-b8de9ef390d1
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCustomAttribute
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 사용자 지정 특성을 나타내는 및 이름, 부모 및 특성의 클래스 형식을 제공할 수 있습니다.  
  
## 구문  
  
```  
IDebugCustomAttribute : IUnknown  
```  
  
## 구현자 참고 사항  
 기호 공급자는 심볼과 연관 된 사용자 지정 특성을 지원 하기 위해이 인터페이스를 구현 합니다.  이 자체 개체에서 일반적으로 구현 됩니다.  
  
## 호출자에 대 한 참고 사항  
 호출을 [다음](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md) 이 인터페이스를 반환 합니다.  호출 하는 [EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md) 메서드가 반환의 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugCustomAttribute`.  
  
|메서드|설명|  
|---------|--------|  
|[GetParentField](../../../extensibility/debugger/reference/idebugcustomattribute-getparentfield.md)|현재 특성에 연결 된 필드를 가져옵니다.|  
|[GetAttributeTypeField](../../../extensibility/debugger/reference/idebugcustomattribute-getattributetypefield.md)|사용자 지정 특성 클래스 형식을 가져옵니다.|  
|[GetName](../../../extensibility/debugger/reference/idebugcustomattribute-getname.md)|사용자 지정 특성의 이름을 가져옵니다.|  
|[GetAttributeBytes](../../../extensibility/debugger/reference/idebugcustomattribute-getattributebytes.md)|특성 정보를 blob 바이트 수를 가져옵니다.|  
  
## 설명  
 사용자 지정 특성의 구조를 C\# 특정 클래스 또는 메서드에 연결 된 사용자 지정 메타 데이터를 제공 하는 것입니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)