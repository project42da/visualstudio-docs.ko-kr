---
title: "IDebugEvent2 | Microsoft Docs"
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
  - "IDebugEvent2"
helpviewer_keywords: 
  - "IDebugEvent2 인터페이스"
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 모두 중단점에서 중지와 같은 중요 한 디버그 정보를 및 디버깅 메시지와 같은 중요 하지 않은 정보를 전달 하기 위해 사용 됩니다.  
  
## 구문  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 및 사용자 지정 포트 공급자와 같은 다른 모든 이벤트 인터페이스 개체에이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 인터페이스에 부여 하는 ID \(IID\) 인수를 사용 하 여 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 또는 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md), 세션 디버그 매니저 \(SDM\)를 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugEvent2` 적절 한 이벤트 인터페이스를 가져올 수 있는 인터페이스.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|이 디버그 이벤트에 대 한 특성을 가져옵니다.|  
  
## 설명  
 특정 이벤트 인터페이스를 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md), IDebugEvent2 인터페이스에서 파생 되지 않습니다 있지만 대신 별도 인터페이스와 같은 개체에 구현 된 `IDebugEvent2`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)