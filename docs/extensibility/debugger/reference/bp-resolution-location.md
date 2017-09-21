---
title: "BP_RESOLUTION_LOCATION | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_RESOLUTION_LOCATION"
helpviewer_keywords: 
  - "BP_RESOLUTION_LOCATION 구조"
ms.assetid: 21dc5246-69c1-43e3-855c-9cd4e596c0e6
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# BP_RESOLUTION_LOCATION
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

중단점 위치 확인의 구조를 지정합니다.  
  
## 구문  
  
```cpp#  
struct _BP_RESOLUTION_LOCATION {  
   BP_TYPE bpType;  
   union {  
      BP_RESOLUTION_CODE bpresCode;  
      BP_RESOLUTION_DATA bpresData;  
      int                unused;  
   } bpResLocation;  
} BP_RESOLUTION_LOCATION;  
```  
  
```c#  
public struct BP_RESOLUTION_LOCATION {  
   public uint bpType;  
   public IntPtr unionmember1;  
   public IntPtr unionmember2;  
   public IntPtr unionmember3;  
   public uint   unionmember4;  
};  
```  
  
## Members  
 `bpType`  
 값을는 [BP\_TYPE](../../../extensibility/debugger/reference/bp-type.md) 해석 하는 방법을 지정 하는 열거형의 `bpResLocation` union 또는 `unionmemberX` 멤버입니다.  
  
 `bpResLocation.bpresCode`  
 \[C \+ \+에만\] Contains the [BP\_RESOLUTION\_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md) structure if `bpType` \= `BPT_CODE`.  
  
 `bpResLocation.bpresData`  
 \[C \+ \+에만\] Contains the [BP\_RESOLUTION\_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md) structure if `bpType` \= `BPT_DATA`.  
  
 `bpResLocation.unused`  
 \[C \+ \+에만\] 자리 표시자입니다.  
  
 `unionmember1`  
 \[C\#만\] 해석 하는 방법에 대 한 설명 부분을 참조 하십시오.  
  
 `unionmember2`  
 \[C\#만\] 해석 하는 방법에 대 한 설명 부분을 참조 하십시오.  
  
 `unionmember3`  
 \[C\#만\] 해석 하는 방법에 대 한 설명 부분을 참조 하십시오.  
  
 `unionmember4`  
 \[C\#만\] 해석 하는 방법에 대 한 설명 부분을 참조 하십시오.  
  
## 설명  
 이 구조체의 멤버인는 [BP\_ERROR\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) 및 [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) 구조체입니다.  
  
 \[C\#만\] `unionmemberX` 멤버는 다음 테이블에 따라 해석 됩니다.  아래로 왼쪽된 된 열에 대 한 조회는 `bpType` 다음 전체 값 무엇 인지 확인할 수 `unionmemberX` 및 marshal 멤버가 나타냅니다는 `unionmemberX` 적절 하 게.  예를 들어 C\#에서이 구조를 해석 하는 방법 참조 하십시오.  
  
|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|  
|----------------------|--------------------|--------------------|--------------------|--------------------|  
|`BPT_CODE`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|\-|\-|\-|  
|`BPT_DATA`|`string`\(데이터 식\)|`string`함수 이름|`string`\(이미지 이름\)|`enum_BP_RES_DATA_FLAGS`|  
  
## 예제  
 해석 하는 방법을 보여 주는이 예제는 `BP_RESOLUTION_LOCATION` C\#의 구조.  
  
```c#  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(BP_RESOLUTION_LOCATION bprl)  
        {  
            if (bprl.bpType == (uint)enum_BP_TYPE.BPT_CODE)  
            {  
                 IDebugCodeContext2 pContext = (IDebugCodeContext2)Marshal.GetObjectForIUnknown(bp.unionmember1);  
            }  
            else if (bprl.bpType == (uint)enum_BP_TYPE.BPT_DATA)  
            {  
                 string dataExpression = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 string functionName = Marshal.PtrToStringBSTR(bp.unionmember2);  
                 string imageName = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 enum_BP_RES_DATA_FLAGS numElements = (enum_BP_RES_DATA_FLAGS)bp.unionmember4;  
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
 [BP\_TYPE](../../../extensibility/debugger/reference/bp-type.md)   
 [BP\_ERROR\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [BP\_RESOLUTION\_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md)   
 [BP\_RESOLUTION\_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)   
 [BP\_RES\_DATA\_FLAGS](../../../extensibility/debugger/reference/bp-res-data-flags.md)