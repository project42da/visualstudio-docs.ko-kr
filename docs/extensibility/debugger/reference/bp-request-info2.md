---
title: BP_REQUEST_INFO2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_REQUEST_INFO2
helpviewer_keywords:
- BP_REQUEST_INFO2 structure
ms.assetid: 008c87f7-a76e-43d3-8904-11b225d6a9a5
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0ea63abb64e0c770cb456cc79e78a7e5d08b5f06
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bprequestinfo2"></a>BP_REQUEST_INFO2
공급 업체 GUID, 제약 조건 및 추적점을 포함 하 여 중단점을 구현 하는 데 필요한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _BP_REQUEST_INFO2 {  
   BPREQI_FIELDS   dwFields;  
   GUID            guidLanguage;  
   BP_LOCATION     bpLocation;  
   IDebugProgram2* pProgram;  
   BSTR            bstrProgramName;  
   IDebugThread2*  pThread;  
   BSTR            bstrThreadName;  
   BP_CONDITION    bpCondition;  
   BP_PASSCOUNT    bpPassCount;  
   BP_FLAGS        dwFlags;  
   GUID            guidVendor;  
   BSTR            bstrConstraint;  
   BSTR            bstrTracepoint;  
} BP_REQUEST_INFO2;  
```  
  
```csharp  
public struct BP_REQUEST_INFO2 {  
   public uint           dwFields;  
   public Guid           guidLanguage;  
   public BP_LOCATION    bpLocation;  
   public IDebugProgram2 pProgram;  
   public string         bstrProgramName;  
   public IDebugThread2  pThread;  
   public string         bstrThreadName;  
   public BP_CONDITION   bpCondition;  
   public BP_PASSCOUNT   bpPassCount;  
   public uint           dwFlags;  
   public Guid           guidVendor;  
   public string         bstrConstraint;  
   public string         bstrTracepoint;  
};  
```  
  
## <a name="members"></a>멤버  
 `dwFields`  
 플래그의 조합 된 [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) 채워진 필드를 지정 하는 열거형입니다.  
  
 `guidLanguage`  
 언어 GUID입니다.  
  
 `bpLocation`  
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 중단점 위치 유형을 지정 하는 구조입니다.  
  
 `pProgram`  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 중단점이 발생 하는 응용 프로그램을 나타내는 개체입니다.  
  
 `bstrProgramName`  
 중단점이 발생 하는 응용 프로그램의 이름입니다.  
  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 중단점이 발생 하는 스레드를 나타내는 개체입니다.  
  
 `bstrThreadName`  
 중단점이 발생 하는 스레드의 이름입니다.  
  
 `bpCondition`  
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) 중단점은 발생 하는 조건을 설명 하는 구조입니다.  
  
 `bpPassCount`  
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) 중단점의 패스 개수 정보가 포함 된 구조체입니다.  
  
 `dwFlags`  
 플래그의 조합 된 [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) 요청한 중단점에 대 한 플래그를 지정 하는 열거형입니다.  
  
 `guidVendor`  
 공급 업체의 GUID입니다. Null 값이 될 수 있습니다.  
  
 `bstrConstraint`  
 중단점 제약 조건의 이름입니다. Null 값이 될 수 있습니다.  
  
 `bstrTracepoint`  
 추적 지점의 이름입니다. Null 값이 될 수 있습니다.  
  
## <a name="remarks"></a>설명  
 이 구조에서 반환 되는 [GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md)   
 [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md)