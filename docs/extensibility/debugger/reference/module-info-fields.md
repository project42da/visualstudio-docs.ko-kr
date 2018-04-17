---
title: MODULE_INFO_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- MODULE_INFO_FIELDS
helpviewer_keywords:
- MODULE_INFO_FIELDS enumeration
ms.assetid: 8bed85f4-235f-4192-b58f-5fad7a4d7a78
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fcc6bd76a4a9aecade72347613ed4f36968c65eb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="moduleinfofields"></a>MODULE_INFO_FIELDS
디버그 모듈 정보에 대 한 플래그를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_MODULE_INFO_FIELDS {   
   MIF_NONE              = 0x0000,  
   MIF_NAME              = 0x0001,  
   MIF_URL               = 0x0002,  
   MIF_VERSION           = 0x0004,  
   MIF_DEBUGMESSAGE      = 0x0008,  
   MIF_LOADADDRESS       = 0x0010,  
   MIF_PREFFEREDADDRESS  = 0x0020,  
   MIF_SIZE              = 0x0040,  
   MIF_LOADORDER         = 0x0080,  
   MIF_TIMESTAMP         = 0x0100,  
   MIF_URLSYMBOLLOCATION = 0x0200,  
   MIF_FLAGS             = 0x0400,  
   MIF_ALLFIELDS         = 0x07ff  
};  
typedef DWORD MODULE_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_MODULE_INFO_FIELDS {   
   MIF_NONE              = 0x0000,  
   MIF_NAME              = 0x0001,  
   MIF_URL               = 0x0002,  
   MIF_VERSION           = 0x0004,  
   MIF_DEBUGMESSAGE      = 0x0008,  
   MIF_LOADADDRESS       = 0x0010,  
   MIF_PREFFEREDADDRESS  = 0x0020,  
   MIF_SIZE              = 0x0040,  
   MIF_LOADORDER         = 0x0080,  
   MIF_TIMESTAMP         = 0x0100,  
   MIF_URLSYMBOLLOCATION = 0x0200,  
   MIF_FLAGS             = 0x0400,  
   MIF_ALLFIELDS         = 0x07ff  
};  
```  
  
## <a name="members"></a>멤버  
 MIF_NONE  
 구조에 필드를 초기화/사용 합니다.  
  
 MIF_NAME  
 초기화/사용 된 `m_bstrName` 필드에 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) 구조입니다.  
  
 MIF_URL  
 초기화/사용 된 `m_bstrUrl` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF_VERSION  
 초기화/사용 된 `m_bstrVersion` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF_DEBUGMESSAGE  
 초기화/사용 된 `m_bstrDebugMessage` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF_LOADADDRESS  
 초기화/사용 된 `m_addrLoadAddress` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF_PREFFEREDADDRESS  
 초기화/사용 된 `m_addrPreferredLoadAddress` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF_SIZE  
 초기화/사용 된 `m_dwSize` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF_LOADORDER  
 초기화/사용 된 `m_dwLoadOrder` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF_TIMESTAMP  
 초기화/사용 된 `m_TimeStamp` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF_URLSYMBOLLOCATION  
 초기화/사용 된 `m_bstrUrlSymbolLocation` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF_FLAGS  
 초기화/사용 된 `m_dwModuleFlags` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF_ALLFIELDS  
 초기화/사용의 모든 필드에는 `MODULE_INFO` 구조입니다.  
  
## <a name="remarks"></a>설명  
 이러한 값에 대 한 인수로 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) 의 필드를 나타내도록 메서드를는 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) 구조를 초기화할 수는 있습니다.  
  
 이러한 값에도 사용 되는 `MODULE_INFO` 구조에는 필드는 사용 되지 않으며 유효한 합니다.  
  
 이러한 플래그 비트와 함께 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)