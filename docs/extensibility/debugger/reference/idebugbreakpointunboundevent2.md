---
title: "IDebugBreakpointUnboundEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBreakpointUnboundEvent2"
helpviewer_keywords: 
  - "IDebugBreakpointUnboundEvent2"
ms.assetid: 6b1e1863-0c64-4d85-8ab9-aface522fdea
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugBreakpointUnboundEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 세션 디버그 매니저 \(SDM\) 바인딩된 중단점 로드 된 프로그램에서 바인딩 되었음을 알 수 있습니다.  
  
## 구문  
  
```  
IDebugBreakpointUnboundEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 중단점에 대 한 지원의 일부로 서이 인터페이스를 구현합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다 \(SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스\)입니다.  
  
## 호출자에 대 한 참고 사항  
 DE 만들고 바인딩된 중단점이 바인딩 해제 된 경우이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 콜백 함수 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugBreakpointUnboundEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)|언바운드 되었습니다 중단점을 가져옵니다.|  
|[GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)|중단점이 바인딩 된 이유를 가져옵니다.|  
  
## 설명  
 코드에서 해당 모듈에 연결 된 모든 중단점은 디버그 엔진 DLL 이나 클래스를 언로드할 때 디버깅 중인 프로그램에서 바운드 해야 합니다.  `IDebugBreakpointUnboundEvent2` 각 바인딩 해제 된 중단점에 대 한 전송 됩니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)