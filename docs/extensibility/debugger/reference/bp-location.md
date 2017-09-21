---
title: "BP_LOCATION | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_LOCATION"
helpviewer_keywords: 
  - "BP_LOCATION 공용 구조체"
ms.assetid: ed1e874c-f289-4c31-8b6c-04dde03ad0f5
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# BP_LOCATION
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

중단점의 위치를 설명 하는 구조를 지정 합니다.  
  
## 구문  
  
```cpp#  
typedef struct _BP_LOCATION {  
   BP_LOCATION_TYPE bpLocationType;  
   union {  
      BP_LOCATION_CODE_FILE_LINE   bplocCodeFileLine;  
      BP_LOCATION_CODE_FUNC_OFFSET bplocCodeFuncOffset;  
      BP_LOCATION_CODE_CONTEXT     bplocCodeContext;  
      BP_LOCATION_CODE_STRING      bplocCodeString;  
      BP_LOCATION_CODE_ADDRESS     bplocCodeAddress;  
      BP_LOCATION_DATA_STRING      bplocDataString;  
      BP_LOCATION_RESOLUTION       bplocResolution;  
      DWORD                        unused;  
   } bpLocation;  
} BP_LOCATION;  
```  
  
```c#  
public struct BP_LOCATION {  
   public uint   bpLocationType;  
   public IntPtr unionmember1;  
   public IntPtr unionmember2;  
   public IntPtr unionmember3;  
   public IntPtr unionmember4;  
};  
```  
  
## Members  
 `bpLocationType`  
 값에서의 [BP\_LOCATION\_TYPE](../../../extensibility/debugger/reference/bp-location-type.md) 해석 하는 데 사용 되는 열거형의 `bpLocation` union 나는 `unionmemberX` 멤버.  
  
 `bpLocation`.`bplocCodeFileLine`  
 \[C \+ \+에만\] Contains the [BP\_LOCATION\_CODE\_FILE\_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) structure if `bpLocationType` \= `BPLT_CODE_FILE_LINE`.  
  
 `bpLocation.bplocCodeFuncOffset`  
 \[C \+ \+에만\] Contains the [BP\_LOCATION\_CODE\_FUNC\_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) structure if `bpLocationType` \= `BPLT_CODE_FUNC_OFFSET`.  
  
 `bpLocation.bplocCodeContext`  
 \[C \+ \+에만\] Contains the [BP\_LOCATION\_CODE\_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md) structure if `bpLocationType` \= `BPLT_CODE_CONTEXT`.  
  
 `bpLocation.bplocCodeString`  
 \[C \+ \+에만\] Contains the [BP\_LOCATION\_CODE\_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md) structure if `bpLocationType` \= `BPLT_CODE_STRING`.  
  
 `bpLocation.bplocCodeAddress`  
 \[C \+ \+에만\] Contains the [BP\_LOCATION\_CODE\_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md) structure if `bpLocationType` \= `BPLT_CODE_ADDRESS`.  
  
 `bpLocation.bplocDataString`  
 \[C \+ \+에만\] Contains the [BP\_LOCATION\_DATA\_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md) structure if `bpLocationType` \= `BPLT_DATA_STRING`.  
  
 `bpLocation.bplocResolution`  
 \[C \+ \+에만\] Contains the [BP\_LOCATION\_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md) structure if `bpLocationType` \= `BPLT_RESOLUTION`.  
  
 `unionmember1`  
 \[C\#만\] 해석 하는 방법에 대 한 설명 부분을 참조 하십시오.  
  
 `unionmember2`  
 \[C\#만\] 해석 하는 방법에 대 한 설명 부분을 참조 하십시오.  
  
 `unionmember3`  
 \[C\#만\] 해석 하는 방법에 대 한 설명 부분을 참조 하십시오.  
  
 `unionmember4`  
 \[C\#만\] 해석 하는 방법에 대 한 설명 부분을 참조 하십시오.  
  
## 설명  
 이 구조체의 멤버인는 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 및 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조체입니다.  
  
 \[C\#만\] `unionmemberX` 멤버는 다음 테이블에 따라 해석 됩니다.  아래로 왼쪽된 된 열에 대 한 조회는 `bpLocationType` 값 다음 무엇 인지 확인 하려면 다른 열에서 확인 `unionmemberX` 및 marshal 멤버가 나타냅니다의 `unionmemberX` 적절 하 게.  이 구조에서 C\# 부분을 해석 하는 방법에 대 한 예제를 참조 하십시오.  
  
|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|  
|----------------------|--------------------|--------------------|--------------------|--------------------|  
|`BPLT_CODE_FILE_LINE`|`string`\(컨텍스트\)|[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)|\-|\-|  
|`BPLT_CODE_FUNC_OFFSET`|`string`\(컨텍스트\)|[IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)|\-|\-|  
|`BPLT_CODE_CONTEXT`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|\-|\-|\-|  
|`BPLT_CODE_STRING`|`string`\(컨텍스트\)|`string`\(조건부 식\)|\-|\-|  
|`BPLT_CODE_ADDRESS`|`string`\(컨텍스트\)|`string`\(모듈 URL\)|`string`함수 이름|`string`\(주소\)|  
|`BPLT_DATA_STRING`|[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)|`string`\(컨텍스트\)|`string`\(데이터 식\)|`uint`\(요소 수\)|  
|`BPLT_RESOLUTION`|[IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)|\-|\-|\-|  
  
## 예제  
 해석 하는 방법을 보여 주는이 예제는 `BP_LOCATION` 구조에서 C\#를 `BPLT_DATA_STRING` 형식.  이 특정 형식을 네 해석 하는 방법을 보여 줍니다. `unionmemberX` 구성원의 모든 가능한 형식 \(개체, 문자열 및 숫자\).  
  
```c#  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(BP_LOCATION bp)  
        {  
            if (bp.bpLocationType == (uint)enum_BP_LOCATION_TYPE.BPLT_DATA_STRING)  
            {  
                 IDebugThread2 pThread = (IDebugThread2)Marshal.GetObjectForIUnknown(bp.unionmember1);  
                 string context = Marshal.PtrToStringBSTR(bp.unionmember2);  
                 string dataExpression = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 uint numElements = (uint)Marshal.ReadInt32(bp.unionmember4);  
            }  
        }  
    }  
}  
```  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP\_LOCATION\_CODE\_FILE\_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)   
 [BP\_LOCATION\_CODE\_FUNC\_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP\_LOCATION\_CODE\_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md)   
 [BP\_LOCATION\_CODE\_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md)   
 [BP\_LOCATION\_CODE\_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md)   
 [BP\_LOCATION\_DATA\_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md)   
 [BP\_LOCATION\_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md)