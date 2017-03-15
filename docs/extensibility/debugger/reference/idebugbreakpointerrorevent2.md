---
title: "IDebugBreakpointErrorEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBreakpointErrorEvent2"
helpviewer_keywords: 
  - "IDebugBreakpointErrorEvent2"
ms.assetid: adee79df-8db5-4510-a7df-c50f4dbf5e35
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# IDebugBreakpointErrorEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 세션 디버그 매니저 \(SDM\) 보류 중단점에 로드 된 프로그램의 경고 또는 오류 때문에 바인딩할 수 없습니다 있음을 알려 줍니다.  
  
## 구문  
  
```  
IDebugBreakpointErrorEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE는 해당 중단점에 대 한 지원의 일부로 서이 인터페이스를 구현합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다 \(SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스\)입니다.  
  
## 호출자에 대 한 참고 사항  
 DE 만들고 보류 중단점이 디버깅 중인 프로그램에 바인딩할 수 없는 경우이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 콜백 함수 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugBreakpointErrorEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md)|가져옵니다는 [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) 경고 또는 오류를 설명 하는 인터페이스입니다.|  
  
## 설명  
 중단점이 바인딩되는 SDM에 이벤트가 전달 됩니다.  중단점을 바인딩할 수 없는 경우는 `IDebugBreakpointErrorEvent2` 전송 됩니다. 그렇지 않은 경우는 [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) 전송 됩니다.  
  
 예를 들어, 구문 분석 또는 평가를 보류 중단점으로 연관 된 조건이 실패 하면 경고를 보류 중단점을이 바인딩할 수 없습니다 전송 됩니다.  중단점에 대 한 코드를 아직 로드 되지 않은 경우에 발생할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)