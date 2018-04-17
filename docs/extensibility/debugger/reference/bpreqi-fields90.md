---
title: BPREQI_FIELDS90 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- BPREQI_FIELDS90 enumeration
ms.assetid: bf6f7efc-39f2-46a2-906d-c3647bf89995
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ef4363b210fff059a88f80bd7377d91971ef2bce
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="bpreqifields90"></a>BPREQI_FIELDS90
중단점 요청에 대 한 정보를 검색할 수를 지정 하는 유효한 값을 열거 합니다. 이 열거형 확장는 [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
```csharp  
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
  
#### <a name="parameters"></a>매개 변수  
 BPREQI90_BPLOCATION  
 배열을 초기화 하거나 사용 하 여는 `bpLocation` 의 (중단점 위치) 필드는 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 또는 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조입니다.  
  
 BPREQI90_LANGUAGE  
 배열을 초기화 하거나 사용 하 여는 `guidLanguage` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_PROGRAM  
 배열을 초기화 하거나 사용 하 여는 `pProgram` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_PROGRAMNAME  
 배열을 초기화 하거나 사용 하 여는 `bstrProgramName` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_THREAD  
 배열을 초기화 하거나 사용 하 여는 `pThread` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_THREADNAME  
 배열을 초기화 하거나 사용 하 여는 `bstrThreadName` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_PASSCOUNT  
 배열을 초기화 하거나 사용 하 여는 `bpPassCount` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_CONDITION  
 배열을 초기화 하거나 사용 하 여는 `bpCondition` 의 (중단점 조건) 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_FLAGS  
 배열을 초기화 하거나 사용 하 여는 `dwFlags` 필드는 `BP_REQUEST_INFO` 또는 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_ALLOLDFIELDS  
 배열을 초기화 하거나에 대 한 모든 필드를 사용 하는의 `BP_REQUEST_INFO` 구조입니다.  
  
 BPREQI90_VENDOR  
 배열을 초기화 하거나 사용 하 여는 `guidVendor` 필드 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_CONSTRAINT  
 배열을 초기화 하거나 사용 하 여는 `bstrConstraint` 필드 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_TRACEPOINT  
 배열을 초기화 하거나 사용 하 여는 `bstrTracepoint` 필드 `BP_REQUEST_INFO2` 구조입니다.  
  
 BPREQI90_MACROTRACEPOINT  
 배열을 초기화 하거나 사용 하 여는 `bstrMacroTracepoint` 필드 `BP_REQUEST_INFO2` 구조입니다. BPREQI_ALLFIELDS이이 필드를 포함 하지 않습니다.  
  
 BPREQI90_ALLFIELDS  
 모든 필드에 대 한 지정 된 `BP_REQUEST_INFO2` 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)