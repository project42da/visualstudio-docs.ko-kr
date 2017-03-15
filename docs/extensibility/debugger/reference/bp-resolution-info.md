---
title: "BP_RESOLUTION_INFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_RESOLUTION_INFO"
helpviewer_keywords: 
  - "BP_RESOLUTION_INFO 구조"
ms.assetid: ba0c162a-61e8-4a0b-811f-4c1d8a5d82f0
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# BP_RESOLUTION_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

코드 중단점 또는 데이터 중단점에 대해 바인딩된 중단점 정보에 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct _BP_RESOLUTION_INFO {   
   BPRESI_FIELDS          dwFields;  
   BP_RESOLUTION_LOCATION bpResLocation;  
   IDebugProgram2*        pProgram;  
   IDebugThread2*         pThread;  
} BP_RESOLUTION_INFO;  
```  
  
```c#  
public struct BP_RESOLUTION_INFO {   
   public uint                   dwFields;  
   public BP_RESOLUTION_LOCATION bpResLocation;  
   public IDebugProgram2         pProgram;  
   public IDebugThread2          pThread;  
};  
```  
  
## Members  
 `dwFields`  
 플래그의 컬렉션의 [BPRESI\_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md) 필드를 지정 하는 열거형 채울.  
  
 `bpResLocation`  
 [BP\_RESOLUTION\_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md) 코드 또는 데이터에 중단점의 위치를 지정 하는 구조입니다.  
  
 `pProgram`  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 는 중단점 오류 발생 응용 프로그램을 나타내는 개체입니다.  
  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 중단점 오류 있는 응용 프로그램 실행 되는 스레드를 나타내는 개체입니다.  
  
## 설명  
 이 구조가 반환 하는 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)   
 [BPRESI\_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)   
 [BP\_RESOLUTION\_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)