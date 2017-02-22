---
title: "BPREQI_FIELDS | Microsoft Docs"
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
  - "BPREQI_FIELDS"
helpviewer_keywords: 
  - "BPREQI_FIELDS 열거형"
ms.assetid: 679e771e-4a79-484e-af37-f962ef4aa245
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# BPREQI_FIELDS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

중단점 요청에 대 한 검색 해야 하는 정보를 지정 합니다.  
  
## 구문  
  
```cpp  
enum enum_BPREQI_FIELDS {   
   BPREQI_BPLOCATION   = 0x0001,  
   BPREQI_LANGUAGE     = 0x0002,  
   BPREQI_PROGRAM      = 0x0004,  
   BPREQI_PROGRAMNAME  = 0x0008,  
   BPREQI_THREAD       = 0x0010,  
   BPREQI_THREADNAME   = 0x0020,  
   BPREQI_PASSCOUNT    = 0x0040,  
   BPREQI_CONDITION    = 0x0080,  
   BPREQI_FLAGS        = 0x0100,  
   BPREQI_ALLOLDFIELDS = 0x01ff  
   BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only  
   BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only  
   BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only  
   BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only  
};  
typedef DWORD BPREQI_FIELDS;  
```  
  
```c#  
public enum enum_BPREQI_FIELDS {   
   BPREQI_BPLOCATION   = 0x0001,  
   BPREQI_LANGUAGE     = 0x0002,  
   BPREQI_PROGRAM      = 0x0004,  
   BPREQI_PROGRAMNAME  = 0x0008,  
   BPREQI_THREAD       = 0x0010,  
   BPREQI_THREADNAME   = 0x0020,  
   BPREQI_PASSCOUNT    = 0x0040,  
   BPREQI_CONDITION    = 0x0080,  
   BPREQI_FLAGS        = 0x0100,  
   BPREQI_ALLOLDFIELDS = 0x01ff  
   BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only  
   BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only  
   BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only  
   BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only  
};  
```  
  
## Members  
 BPREQI\_BPLOCATION  
 초기화\/사용의 `bpLocation` \(중단점 위치\) 필드는 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 또는 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조.  
  
 BPREQI\_LANGUAGE  
 초기화\/사용의 `guidLanguage` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI\_PROGRAM  
 초기화\/사용의 `pProgram` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI\_PROGRAMNAME  
 초기화\/사용의 `bstrProgramName` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI\_THREAD  
 초기화\/사용의 `pThread` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI\_THREADNAME  
 초기화\/사용의 `bstrThreadName` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI\_PASSCOUNT  
 초기화\/사용의 `bpPassCount` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI\_CONDITION  
 초기화\/사용의 `bpCondition` \(중단점 조건\) 필드에는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조.  
  
 BPREQI\_FLAGS  
 초기화\/사용의 `dwFlags` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI\_ALLOLDFIELDS  
 모든 필드에 대 한 기본 초기화 사용의의 `BP_REQUEST_INFO` 구조입니다.  
  
 BPREQI\_VENDOR  
 초기화\/사용의 `guidVendor` 필드의 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI\_CONSTRAINT  
 초기화\/사용의 `bstrConstraint` 필드의 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI\_TRACEPOINT  
 초기화\/사용의 `bstrTracepoint` 필드의 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI\_ALLFIELDS  
 모든 필드에 대해 지정은 `BP_REQUEST_INFO2` 구조체입니다.  
  
## 설명  
 인수로 전달 되는 [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md) 및 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 의 필드를 지정 하는 방법의 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 및 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조인 초기화.  
  
 이러한 플래그 필드를 나타내는 데도 사용 됩니다 있는 `BP_REQUEST_INFO` 및 `BP_REQUEST_INFO2` 구조는 사용 되는 및 유효한 각 구조가 반환 될 때.  
  
 이 값이 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)   
 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)