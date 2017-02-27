---
title: "IDebugBoundBreakpoint2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBoundBreakpoint2"
helpviewer_keywords: 
  - "IDebugBoundBreakpoint2 인터페이스"
ms.assetid: df33c52e-ded2-48a0-951d-1f36c8fc922e
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugBoundBreakpoint2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 코드 위치를 연결 된 중단점을 나타냅니다.  
  
## 구문  
  
```  
IDebugBoundBreakpoint2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 중단점에 대 한 지원의 일부로 서이 인터페이스를 구현합니다.  
  
## 호출자에 대 한 참고 사항  
 호출을 [바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) 이 인터페이스를 만듭니다.  호출 하려면 [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md) 및 [다음](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md) 이 인터페이스를 가져올 수도 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugBoundBreakpoint2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)|지정한 바인딩된 중단점에서 만든 보류 중인 중단점을 가져옵니다.|  
|[GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)|이 바인딩된 중단점의 상태를 가져옵니다.|  
|[GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md)|에 바인딩된 중단점이 현재 적중된 횟수를 가져옵니다.|  
|[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)|설명이 중단점이 중단점 해상도를 가져옵니다.|  
|[사용](../../../extensibility/debugger/reference/idebugboundbreakpoint2-enable.md)|중단점을 사용할 수 있거나.|  
|[SetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-sethitcount.md)|이 바인딩된 중단점에 적중된 횟수를 설정합니다.|  
|[SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)|설정 하거나이 바인딩된 중단점에 연관 된 상태를 변경 합니다.|  
|[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)|통과 횟수가 바인딩된 중단점에 관련 된 변경 또는 설정 합니다.|  
|[삭제](../../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)|중단점을 삭제합니다.|  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)   
 [다음](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md)   
 [바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)