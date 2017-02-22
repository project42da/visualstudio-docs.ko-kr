---
title: "IDebugBreakpointRequest2 | Microsoft Docs"
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
  - "IDebugBreakpointRequest2"
helpviewer_keywords: 
  - "IDebugBreakpointRequest2 인터페이스"
ms.assetid: 01ac4013-96f9-4235-b289-f55f9e99558f
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugBreakpointRequest2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스를 만들어 모든 형식의 중단점을 바인딩할에 필요한 정보를 나타냅니다.  
  
## 구문  
  
```  
IDebugBreakpointRequest2 : IUnknown  
```  
  
## 구현자 참고 사항  
 세션 디버그 매니저 \(SDM\) 일반적으로이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 디버그 엔진 \(DE\)이이 인터페이스에 대 한 호출을 통해 받은 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) 보류 중단점을 만들 수 있습니다.  호출을 [GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md) DE에서이 인터페이스를 검색할 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugBreakpointRequest2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)|이 중단점 요청은 중단점 위치 형식을 가져옵니다.|  
|[GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)|이 중단점 요청은 중단점 요청 정보를 가져옵니다.|  
  
## 설명  
 후 프로그램이 디버깅 되 고 로드, 호출을 [바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) 보류 중단점 프로그램에서 요청 된 위치에 바인딩합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)   
 [GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)   
 [바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)