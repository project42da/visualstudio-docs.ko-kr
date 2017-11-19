---
title: DEBUG_PROPERTY_INFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEBUG_PROPERTY_INFO
helpviewer_keywords: DEBUG_PROPERTY_INFO structure
ms.assetid: 5a085d18-62c6-4740-b9e9-3f5db6bfdf7f
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9d75a5d9aabd923d9cf3ea4e8e0a1403182b1106
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="debugpropertyinfo"></a>DEBUG_PROPERTY_INFO
디버그 속성에 대 한 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
```csharp  
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
  
## <a name="members"></a>멤버  
 dwValidFields  
 플래그의 조합 된 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) 어떤 필드 입력을 지정 하는 열거형입니다.  
  
 bstrFullName  
 속성의 전체 이름입니다.  
  
 bstrName  
 컨텍스트 내에서 속성 이름입니다.  
  
 bstrType  
 서식이 지정 된 문자열 속성 형식입니다.  
  
 bstrValue  
 서식이 지정 된 문자열 속성 값입니다.  
  
 속성  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 이 구조에서 설명 하는 개체입니다.  
  
 dwAttrib  
 플래그의 조합 된 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) 이 속성의 특성을 설명 하는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 속성은 개체 이름, 형식 및 값을 가진 계층적 특성입니다. 예를 들어 지역 변수, 매개 변수, 조사식 변수 및 식과 레지스터 속성 설명 수 있습니다.  
  
 이 구조에 전달 되는 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 으로 채워지면 메서드. 이 구조에서이 구조의 목록의 일부로 반환 됩니다는 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) 차례로 호출에서 반환 되는 인터페이스는 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 및 [ EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)