---
title: "BP_REQUEST_INFO | Microsoft Docs"
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
  - "BP_REQUEST_INFO"
helpviewer_keywords: 
  - "BP_REQUEST_INFO 구조"
ms.assetid: 42a31412-5b6b-47fe-a762-0c2bc769e1cc
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# BP_REQUEST_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

중단점을 구현 하는 데 필요한 정보가 들어 있습니다.  
  
## 구문  
  
```cpp#  
typedef struct _BP_REQUEST_INFO {  
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
} BP_REQUEST_INFO;  
```  
  
```c#  
public struct BP_REQUEST_INFO {  
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
};  
```  
  
## Members  
 `dwFields`  
 플래그의 조합에서 [BPREQI\_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) 채워진 필드를 지정 하는 열거형입니다.  
  
 `guidLanguage`  
 언어의 GUID입니다.  
  
 `bpLocation`  
 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 중단점 위치 형식을 지정 하는 구조입니다.  
  
 `pProgram`  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 는 중단점이 발생 응용 프로그램을 나타내는 개체입니다.  
  
 `bstrProgramName`  
 중단점이 발생 하는 응용 프로그램의 이름입니다.  
  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 에 중단점이 발생 하는 스레드를 나타내는 개체입니다.  
  
 `bstrThreadName`  
 이름에 중단점이 발생 하는 스레드입니다.  
  
 `bpCondition`  
 [BP\_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) 에서 중단점이 발생 하는 조건을 설명 하는 구조입니다.  
  
 `bpPassCount`  
 [BP\_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) 중단점의 패스 개수 정보를 포함 하는 구조입니다.  
  
 `dwFlags`  
 플래그의 조합에서 [BP\_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) 요청 된 중단점에 대 한 플래그를 지정 하는 열거형입니다.  
  
## 설명  
 이 구조에서 반환 되는 [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md) 메서드.  
  
 디버그 엔진 공급 업체 GUID를 얻이 필요가 있으면 제약 조건 중단점 또는 추적점을 참조는 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조체입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)   
 [BPREQI\_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)   
 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [BP\_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)   
 [BP\_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP\_FLAGS](../../../extensibility/debugger/reference/bp-flags.md)   
 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)