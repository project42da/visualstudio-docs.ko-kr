---
title: "IDebugEventCallback2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEventCallback2"
helpviewer_keywords: 
  - "IDebugEventCallback2"
ms.assetid: 2c935ee0-2e22-4be0-a852-73736f33c8c9
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# IDebugEventCallback2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진 \(DE\) 세션 디버그 매니저 \(SDM\) 디버그 이벤트를 보낼 수 있습니다.  
  
## 구문  
  
```  
IDebugEventCallback2 : IUnknown  
```  
  
## 구현자 참고 사항  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]디버그 엔진에서 이벤트를 수신 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 SDM을 호출 하는 경우이 인터페이스는 디버그 엔진 일반적으로 수신 [연결](../../../extensibility/debugger/reference/idebugprogram2-attach.md), [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md), 또는 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  호출 하 여 디버그 엔진 이벤트 SDM을 보냅니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugEventCallback2`.  
  
|메서드|설명|  
|---------|--------|  
|[이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)|디버깅 이벤트는 SDM에 알림을 보냅니다.|  
  
## 설명  
 있지만 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 및 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 취하는 지정 된 `IDebugEventCallback2` 인터페이스는이 경우, 하지 및 인터페이스 포인터가 항상 null 값이 됩니다.  디버그 엔진 대신 사용 해야는 `IDebugEventCallback2` 인터페이스에 대 한 호출을 받은 [연결](../../../extensibility/debugger/reference/idebugprogram2-attach.md), [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md), 또는 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
 패키지를 구현 하는 경우 [IDebugEventCallback](../../../extensibility/debugger/reference/idebugeventcallback2.md) 관리 되는 코드에 좋습니다는 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 수 호출에 전달 되는 다양 한 인터페이스 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [연결](../../../extensibility/debugger/reference/idebugprogram2-attach.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)