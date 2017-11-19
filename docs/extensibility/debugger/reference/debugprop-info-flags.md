---
title: DEBUGPROP_INFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEBUGPROP_INFO_FLAGS
helpviewer_keywords: DBGPROP_INFO_FLAGS enumeration
ms.assetid: 1c7fe777-615e-4929-9ed4-970d9fe0eb81
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 24b0208cdfd49ef07ba85803d03a1e2c4aa91553
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="debugpropinfoflags"></a>DEBUGPROP_INFO_FLAGS
검색할 디버그 속성 개체에 대 한 정보를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_DEBUGPROP_INFO_FLAGS {   
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
  
```csharp  
public enum enum_DEBUGPROP_INFO_FLAGS {   
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
  
## <a name="members"></a>멤버  
 DEBUGPROP_INFO_FULLNAME  
 초기화/사용 된 `bstrFullName` 필드입니다.  
  
 DEBUGPROP_INFO_NAME  
 초기화/사용 된 `bstrName` 필드입니다.  
  
 DEBUGPROP_INFO_TYPE  
 초기화/사용 된 `bstrType` 필드입니다.  
  
 DEBUGPROP_INFO_VALUE  
 초기화/사용 된 `bstrValue` 필드입니다.  
  
 DEBUGPROP_INFO_ATTRIB  
 초기화/사용 된 `dwAttrib` 필드입니다.  
  
 DEBUGPROP_INFO_PROP,  
 초기화/사용 된 `pProperty` 포함 된 필드는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스입니다.  
  
 DEBUGPROP_INFO_VALUE_AUTOEXPAND  
 값 필드는이 형식의 개체에 대 한 사용 가능한 경우 자동 확장 값이 포함 되어야 지정 합니다.  
  
 DEBUGPROP_INFO_VALUE_NOFUNCEVAL  
 더 이상 사용되지 않습니다.  
  
 DEBUGPROP_INFO_VALUE_RAW  
 모든 beautified 값 또는 멤버를 반환 하지 않습니다 (즉, 포맷 안 함 값).  
  
 DEBUGPROP_INFO_VALUE_NO_TOSTRING  
 특별 한 합성 된 값을 반환 하지 않습니다 (예를 들어 호출 하지 마십시오 `ToString()` 하 여 값 개체에).  
  
 DEBUGPROP_INFO_NONE  
 플래그가 설정 되어 있는지를 지정 합니다.  
  
 DEBUGPROP_INFO_STANDARD  
 초기화/사용 된 `dwAttrib`, `bstrName`, `bstrType`, 및 `bstrValue` 필드입니다.  
  
 DEBUGPROP_INFO_All  
 모든 플래그의 마스크를 나타냅니다.  
  
## <a name="remarks"></a>설명  
 이러한 값에 전달 되는 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md), [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md), 및 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) 를 초기화할 수 있는 필드를 나타내는 방법은 [ DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조입니다.  
  
 이러한 값에도 사용 됩니다는 `dwFields` 의 멤버는 `DEBUG_PROPERTY_INFO` 구조에는 구조체의 필드는 사용 되지 않으며 유효한 구조를 반환 하는 경우.  
  
 이러한 값에 비트와 함께 사용할 수 있습니다 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)