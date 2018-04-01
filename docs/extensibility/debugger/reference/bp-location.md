---
title: BP_LOCATION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- BP_LOCATION
helpviewer_keywords:
- BP_LOCATION union
ms.assetid: ed1e874c-f289-4c31-8b6c-04dde03ad0f5
caps.latest.revision: 11
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6e268d809442b0101d5d520ca7bdd5f5c37fb62b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bplocation"></a>BP_LOCATION
중단점의 위치를 설명 하는 데 사용 하는 구조체의 형식을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
```csharp  
public struct BP_LOCATION {  
   public uint   bpLocationType;  
   public IntPtr unionmember1;  
   public IntPtr unionmember2;  
   public IntPtr unionmember3;  
   public IntPtr unionmember4;  
};  
```  
  
## <a name="members"></a>멤버  
 `bpLocationType`  
 값은 [BP_LOCATION_TYPE](../../../extensibility/debugger/reference/bp-location-type.md) 해석 하는 데 사용 하는 열거형은 `bpLocation` union 또는 `unionmemberX` 멤버입니다.  
  
 `bpLocation`.`bplocCodeFileLine`  
 [C + + 전용] 포함 된 [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) 경우 구조체 `bpLocationType`  =  `BPLT_CODE_FILE_LINE`합니다.  
  
 `bpLocation.bplocCodeFuncOffset`  
 [C + + 전용] 포함 된 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) 경우 구조체 `bpLocationType`  =  `BPLT_CODE_FUNC_OFFSET`합니다.  
  
 `bpLocation.bplocCodeContext`  
 [C + + 전용] 포함 된 [BP_LOCATION_CODE_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md) 경우 구조체 `bpLocationType`  =  `BPLT_CODE_CONTEXT`합니다.  
  
 `bpLocation.bplocCodeString`  
 [C + + 전용] 포함 된 [BP_LOCATION_CODE_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md) 경우 구조체 `bpLocationType`  =  `BPLT_CODE_STRING`합니다.  
  
 `bpLocation.bplocCodeAddress`  
 [C + + 전용] 포함 된 [BP_LOCATION_CODE_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md) 경우 구조체 `bpLocationType`  =  `BPLT_CODE_ADDRESS`합니다.  
  
 `bpLocation.bplocDataString`  
 [C + + 전용] 포함 된 [BP_LOCATION_DATA_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md) 경우 구조체 `bpLocationType`  =  `BPLT_DATA_STRING`합니다.  
  
 `bpLocation.bplocResolution`  
 [C + + 전용] 포함 된 [BP_LOCATION_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md) 경우 구조체 `bpLocationType`  =  `BPLT_RESOLUTION`합니다.  
  
 `unionmember1`  
 [C#] 해석 하는 방법에 대 한 설명을 참조 하세요.  
  
 `unionmember2`  
 [C#] 해석 하는 방법에 대 한 설명을 참조 하세요.  
  
 `unionmember3`  
 [C#] 해석 하는 방법에 대 한 설명을 참조 하세요.  
  
 `unionmember4`  
 [C#] 해석 하는 방법에 대 한 설명을 참조 하세요.  
  
## <a name="remarks"></a>설명  
 이 구조는의 구성원은 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 및 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조입니다.  
  
 [C#] `unionmemberX` 멤버는 다음 표에 따라 해석 됩니다. 왼쪽된 열에 대 한 살펴보면는 `bpLocationType` 값 다음 무엇 인지 확인 하려면 다른 열에 걸쳐 보기 `unionmemberX` 마샬링 및 멤버 나타냅니다는 `unionmemberX` 적절 하 게 합니다. C#에서이 구조의 일부를 해석 하는 방법에 대 한 예제를 참조 하십시오.  
  
|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|  
|----------------------|--------------------|--------------------|--------------------|--------------------|  
|`BPLT_CODE_FILE_LINE`|`string`(컨텍스트)|[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)|-|-|  
|`BPLT_CODE_FUNC_OFFSET`|`string`(컨텍스트)|[IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)|-|-|  
|`BPLT_CODE_CONTEXT`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|-|-|-|  
|`BPLT_CODE_STRING`|`string`(컨텍스트)|`string`(조건부 식)|-|-|  
|`BPLT_CODE_ADDRESS`|`string`(컨텍스트)|`string`(모듈 URL)|`string`함수 이름|`string`(주소)|  
|`BPLT_DATA_STRING`|[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)|`string`(컨텍스트)|`string`(데이터 식)|`uint`(요소 수)|  
|`BPLT_RESOLUTION`|[IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)|-|-|-|  
  
## <a name="example"></a>예  
 해석 하는 방법을 보여 주는이 예제는 `BP_LOCATION` 구조에 대 한 C#에서 `BPLT_DATA_STRING` 유형입니다. 이 특정 형식에 모든 4를 해석 하는 방법을 보여 줍니다 `unionmemberX` 모든 가능한 형식이 (개체, 문자열 및 숫자)의 멤버입니다.  
  
```csharp  
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
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)   
 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP_LOCATION_CODE_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md)   
 [BP_LOCATION_CODE_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md)   
 [BP_LOCATION_CODE_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md)   
 [BP_LOCATION_DATA_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md)   
 [BP_LOCATION_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md)