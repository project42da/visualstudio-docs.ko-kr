---
title: "DEBUGPROP_INFO_FLAGS | Microsoft Docs"
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
  - "DEBUGPROP_INFO_FLAGS"
helpviewer_keywords: 
  - "DBGPROP_INFO_FLAGS 열거형"
ms.assetid: 1c7fe777-615e-4929-9ed4-970d9fe0eb81
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# DEBUGPROP_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 속성 개체에 대 한 검색할 정보를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_DEBUGPROP_INFO_FLAGS {   
   DEBUGPROP_INFO_FULLNAME          = 0x00000001,  
   DEBUGPROP_INFO_NAME              = 0x00000002,  
   DEBUGPROP_INFO_TYPE              = 0x00000004,  
   DEBUGPROP_INFO_VALUE             = 0x00000008,  
   DEBUGPROP_INFO_ATTRIB            = 0x00000010,  
   DEBUGPROP_INFO_PROP              = 0x00000020,  
   DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,  
   DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,  
   DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,  
   DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000  
   DEBUGPROP_INFO_NONE              = 0x00000000,  
   DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |  
                                      DEBUGPROP_INFO_NAME |  
                                      DEBUGPROP_INFO_TYPE |  
                                      DEBUGPROP_INFO_VALUE,  
   DEBUGPROP_INFO_ALL               = 0xffffffff  
};  
typedef DWORD DEBUGPROP_INFO_FLAGS;  
```  
  
```c#  
public enum enum_DEBUGPROP_INFO_FLAGS {   
   DEBUGPROP_INFO_FULLNAME          = 0x00000001,  
   DEBUGPROP_INFO_NAME              = 0x00000002,  
   DEBUGPROP_INFO_TYPE              = 0x00000004,  
   DEBUGPROP_INFO_VALUE             = 0x00000008,  
   DEBUGPROP_INFO_ATTRIB            = 0x00000010,  
   DEBUGPROP_INFO_PROP              = 0x00000020,  
   DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,  
   DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,  
   DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,  
   DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000  
   DEBUGPROP_INFO_NONE              = 0x00000000,  
   DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |  
                                      DEBUGPROP_INFO_NAME |  
                                      DEBUGPROP_INFO_TYPE |  
                                      DEBUGPROP_INFO_VALUE,  
   DEBUGPROP_INFO_ALL               = 0xffffffff  
};  
```  
  
## Members  
 DEBUGPROP\_INFO\_FULLNAME  
 초기화\/사용의 `bstrFullName` 필드입니다.  
  
 DEBUGPROP\_INFO\_NAME  
 초기화\/사용의 `bstrName` 필드입니다.  
  
 DEBUGPROP\_INFO\_TYPE  
 초기화\/사용의 `bstrType` 필드입니다.  
  
 DEBUGPROP\_INFO\_VALUE  
 초기화\/사용의 `bstrValue` 필드입니다.  
  
 DEBUGPROP\_INFO\_ATTRIB  
 초기화\/사용의 `dwAttrib` 필드입니다.  
  
 DEBUGPROP\_INFO\_PROP,  
 초기화\/사용의 `pProperty` 필드는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스입니다.  
  
 DEBUGPROP\_INFO\_VALUE\_AUTOEXPAND  
 값 필드 사용할 수 있는 경우이 형식의 개체에 대 한 자동 확장 된 값을 포함 하도록 지정 합니다.  
  
 DEBUGPROP\_INFO\_VALUE\_NOFUNCEVAL  
 사용되지 않습니다.  
  
 DEBUGPROP\_INFO\_VALUE\_RAW  
 모든 beautified 값 또는 멤버를 반환 하지 않습니다 \(즉, 값을 포맷 하지 않음\).  
  
 DEBUGPROP\_INFO\_VALUE\_NO\_TOSTRING  
 특수 합성 된 값을 반환 하지 않습니다 \(예를 들어, 호출 하지 `ToString()` 값을 만들기 위해 개체에\).  
  
 DEBUGPROP\_INFO\_NONE  
 플래그가 설정 되어 있는지를 지정 합니다.  
  
 DEBUGPROP\_INFO\_STANDARD  
 Initialize\/use the `dwAttrib`, `bstrName`, `bstrType`, and `bstrValue` fields.  
  
 DEBUGPROP\_INFO\_All  
 마스크는 모든 플래그를 나타냅니다.  
  
## 설명  
 이러한 값이 전달 되는 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md), [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md), 및 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) 필드 초기화를 나타내기 위해 메서드는 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조입니다.  
  
 이러한 값에도 사용 되는 `dwFields` 소속은 `DEBUG_PROPERTY_INFO` 구조 구조가 반환 될 때 필드 구조를 사용 하는 및 잘못 된 것을 나타냅니다.  
  
 이 값이 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)   
 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md)