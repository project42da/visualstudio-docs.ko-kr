---
title: "MODULE_INFO_FIELDS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MODULE_INFO_FIELDS"
helpviewer_keywords: 
  - "MODULE_INFO_FIELDS 열거형"
ms.assetid: 8bed85f4-235f-4192-b58f-5fad7a4d7a78
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# MODULE_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 모듈 정보에 대 한 플래그를 지정합니다.  
  
## 구문  
  
```cpp#  
enum enum_MODULE_INFO_FIELDS {   
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
  
```c#  
public enum enum_MODULE_INFO_FIELDS {   
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
  
## Members  
 MIF\_NONE  
 기본 초기화 필드 구조에서에 사용 합니다.  
  
 MIF\_NAME  
 초기화\/사용의 `m_bstrName` 필드에 [MODULE\_INFO](../../../extensibility/debugger/reference/module-info.md) 구조입니다.  
  
 MIF\_URL  
 초기화\/사용의 `m_bstrUrl` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF\_VERSION  
 초기화\/사용의 `m_bstrVersion` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF\_DEBUGMESSAGE  
 초기화\/사용의 `m_bstrDebugMessage` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF\_LOADADDRESS  
 초기화\/사용의 `m_addrLoadAddress` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF\_PREFFEREDADDRESS  
 초기화\/사용의 `m_addrPreferredLoadAddress` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF\_SIZE  
 초기화\/사용의 `m_dwSize` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF\_LOADORDER  
 초기화\/사용의 `m_dwLoadOrder` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF\_TIMESTAMP  
 초기화\/사용의 `m_TimeStamp` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF\_URLSYMBOLLOCATION  
 초기화\/사용의 `m_bstrUrlSymbolLocation` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF\_FLAGS  
 초기화\/사용의 `m_dwModuleFlags` 필드에 `MODULE_INFO` 구조입니다.  
  
 MIF\_ALLFIELDS  
 기본 초기화 필드의 사용은 `MODULE_INFO` 구조.  
  
## 설명  
 이러한 값을 인수로 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) 필드의 나타내도록 메서드는 [MODULE\_INFO](../../../extensibility/debugger/reference/module-info.md) 구조에 있는 초기화.  
  
 이러한 값에도 사용 됩니다에서 `MODULE_INFO` 구조 필드 사용 되는 및 잘못 된 것을 나타냅니다.  
  
 이러한 플래그의 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MODULE\_INFO](../../../extensibility/debugger/reference/module-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)