---
title: "DEBUG_PROPERTY_INFO | Microsoft Docs"
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
  - "DEBUG_PROPERTY_INFO"
helpviewer_keywords: 
  - "DEBUG_PROPERTY_INFO 구조"
ms.assetid: 5a085d18-62c6-4740-b9e9-3f5db6bfdf7f
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# DEBUG_PROPERTY_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 속성에 대 한 정보가 포함 되어 있습니다.  
  
## 구문  
  
```cpp#  
typedef struct tagDEBUG_PROPERTY_INFO {   
   DEBUGPROP_INFO_FLAGS dwValidFields;  
   BSTR                 bstrFullName;  
   BSTR                 bstrName;  
   BSTR                 bstrType;  
   BSTR                 bstrValue;  
   IDebugProperty2*     pProperty;  
   DBG_ATTRIB_FLAGS     dwAttrib;  
} DEBUG_PROPERTY_INFO;  
```  
  
```c#  
public struct DEBUG_PROPERTY_INFO {   
   public uint            dwValidFields;  
   public string          bstrFullName;  
   public string          bstrName;  
   public string          bstrType;  
   public string          bstrValue;  
   public IDebugProperty2 pProperty;  
   public ulong           dwAttrib;  
};  
```  
  
## Members  
 dwValidFields  
 플래그의 조합에서 [DEBUGPROP\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) 필드에 채워져 지정 하는 열거형입니다.  
  
 bstrFullName  
 속성의 전체 이름입니다.  
  
 bstrName  
 컨텍스트 내의 속성 이름입니다.  
  
 bstrType  
 속성 형식으로 서식이 지정 된 문자열입니다.  
  
 bstrValue  
 서식이 지정 된 문자열 속성 값입니다.  
  
 콜론을 사용할  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 이 구조체에서 설명 하는 개체입니다.  
  
 dwAttrib  
 플래그의 조합에서 [DBG\_ATTRIB\_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) 이 속성의 특성을 설명 하는 열거형입니다.  
  
## 설명  
 속성의 이름, 유형 및 값을 갖는 특성을 계층적 개체입니다.  예를 들어, 속성이 레지스터, 조사식 변수 및 지역 변수, 식 및 매개 변수를 설명할 수 있습니다.  
  
 이 구조체에 전달 되는 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 메서드는 입력 위치에 있습니다.  이 구조에서이 구조체의 목록의 일부로 반환 됩니다는 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) ,에 대 한 호출에서 반환 되는 인터페이스는 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 및 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) 방법.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUGPROP\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [DBG\_ATTRIB\_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)