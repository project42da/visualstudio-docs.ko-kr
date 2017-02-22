---
title: "IDebugBreakpointRequest3 | Microsoft Docs"
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
  - "IDebugBreakpointRequest3"
helpviewer_keywords: 
  - "IDebugBreakpointRequest3"
ms.assetid: 8a042beb-b319-48e3-b3c8-9c8336ab371b
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugBreakpointRequest3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스를 만들어 모든 형식의 중단점을 바인딩할에 필요한 정보를 나타냅니다.  확장 된 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md).  
  
## 구문  
  
```  
IDebugBreakpointRequest3 : IDebugBreakpointRequest2  
```  
  
## 구현자 참고 사항  
 세션 디버그 매니저 \(SDM\) 일반적으로이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 디버그 엔진 \(DE\)이이 인터페이스를 호출 하 여 액세스 하는 [QueryInterface](/visual-cpp/atl/queryinterface) IDebugBreakpointRequest2 인터페이스에 대 한 호출을 받은 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md).  
  
## 메서드에서 Vtable 순서  
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)에서 상속되는 메서드 외에도 `IDebugBreakpointRequest3` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md)|이 중단점 요청은 중단점 요청 정보를 가져옵니다.|  
  
## 설명  
 이 인터페이스에 DE를 통해 추가 정보를 제공 하는 데 사용 됩니다 있는 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조체입니다.  이 추가 정보는 DE 공급 업체 ID \(GUID 형태로\)는 추적점의 이름을 중단점 제약 조건 이름이 포함 됩니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)   
 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)