---
title: "BPREQI_FIELDS90 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "BPREQI_FIELDS90 열거형"
ms.assetid: bf6f7efc-39f2-46a2-906d-c3647bf89995
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# BPREQI_FIELDS90
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

검색할 중단점 요청에 대 한 정보를 지정 하는 유효한 값을 열거 합니다.  이 열거형에 확장 되는 [BPREQI\_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) 열거형입니다.  
  
## 구문  
  
```cpp#  
enum enum_BPREQI_FIELDS90  
{  
   // VS 8.0 values  
   BPREQI90_BPLOCATION                = 0x0001,  
   BPREQI90_LANGUAGE                  = 0x0002,  
   BPREQI90_PROGRAM                   = 0x0004,  
   BPREQI90_PROGRAMNAME               = 0x0008,  
   BPREQI90_THREAD                    = 0x0010,  
   BPREQI90_THREADNAME                = 0x0020,  
   BPREQI90_PASSCOUNT                 = 0x0040,  
   BPREQI90_CONDITION                 = 0x0080,  
   BPREQI90_FLAGS                     = 0x0100,  
   BPREQI90_ALLOLDFIELDS              = 0x01ff,  
   BPREQI90_VENDOR                    = 0x0200,  
   BPREQI90_CONSTRAINT                = 0x0400,  
   BPREQI90_TRACEPOINT                = 0x0800,  
  
   // Values added in VS 9.0  
   BPREQI90_MACROTRACEPOINT           = 0x1000,  
  
   BPREQI90_ALLFIELDS                 = 0xffff  
};  
typedef DWORD BPREQI_FIELDS90;  
```  
  
```c#  
public enum enum_BPREQI_FIELDS90  
{  
    // VS 8.0 values  
    BPREQI90_BPLOCATION                = 0x0001,  
    BPREQI90_LANGUAGE                  = 0x0002,  
    BPREQI90_PROGRAM                   = 0x0004,  
    BPREQI90_PROGRAMNAME               = 0x0008,  
    BPREQI90_THREAD                    = 0x0010,  
    BPREQI90_THREADNAME                = 0x0020,  
    BPREQI90_PASSCOUNT                 = 0x0040,  
    BPREQI90_CONDITION                 = 0x0080,  
    BPREQI90_FLAGS                     = 0x0100,  
    BPREQI90_ALLOLDFIELDS              = 0x01ff,  
    BPREQI90_VENDOR                    = 0x0200,  
    BPREQI90_CONSTRAINT                = 0x0400,  
    BPREQI90_TRACEPOINT                = 0x0800,  
  
    // Values added in VS 9.0  
    BPREQI90_MACROTRACEPOINT           = 0x1000,  
  
    BPREQI90_ALLFIELDS                 = 0xffff  
};  
```  
  
#### 매개 변수  
 BPREQI90\_BPLOCATION  
 초기화 하거나 사용 하는 `bpLocation` \(중단점 위치\) 필드의의 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 또는 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조입니다.  
  
 BPREQI90\_LANGUAGE  
 초기화 하거나 사용 하는 `guidLanguage` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90\_PROGRAM  
 초기화 하거나 사용 하는 `pProgram` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90\_PROGRAMNAME  
 초기화 하거나 사용 하는 `bstrProgramName` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90\_THREAD  
 초기화 하거나 사용 하는 `pThread` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90\_THREADNAME  
 초기화 하거나 사용 하는 `bstrThreadName` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90\_PASSCOUNT  
 초기화 하거나 사용 하는 `bpPassCount` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90\_CONDITION  
 초기화 하거나 사용 하는 `bpCondition` \(중단점 조건\) 필드에는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조.  
  
 BPREQI90\_FLAGS  
 초기화 하거나 사용 하는 `dwFlags` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90\_ALLOLDFIELDS  
 초기화 또는 모든 필드에 대해 사용 하는의 `BP_REQUEST_INFO` 구조.  
  
 BPREQI90\_VENDOR  
 초기화 하거나 사용 하는 `guidVendor` 필드의 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90\_CONSTRAINT  
 초기화 하거나 사용 하는 `bstrConstraint` 필드의 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90\_TRACEPOINT  
 초기화 하거나 사용 하는 `bstrTracepoint` 필드의 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90\_MACROTRACEPOINT  
 초기화 하거나 사용 하는 `bstrMacroTracepoint` 필드의 `BP_REQUEST_INFO2` 구조입니다.  이 필드는 BPREQI\_ALLFIELDS 포함 되지 않습니다.  
  
 BPREQI90\_ALLFIELDS  
 모든 필드에 대해 지정은 `BP_REQUEST_INFO2` 구조체입니다.  
  
## 요구 사항  
 헤더: Msdbg90.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)