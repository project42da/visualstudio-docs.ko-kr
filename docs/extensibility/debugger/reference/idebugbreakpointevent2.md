---
title: "IDebugBreakpointEvent2 | Microsoft Docs"
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
  - "IDebugBreakpointEvent2"
helpviewer_keywords: 
  - "IDebugBreakpointEvent2 인터페이스"
ms.assetid: 50b3a7a7-331b-42c8-922c-ff3522ebe1da
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugBreakpointEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램이 중단점에서 멈추면 debug 엔진 \(DE\)이이 인터페이스 세션 디버그 매니저 \(SDM\) 보냅니다.  
  
## 구문  
  
```  
IDebugBreakpointEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE는 해당 중단점에 대 한 지원의 일부로 서이 인터페이스를 구현합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다 \(SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스\)입니다.  
  
## 호출자에 대 한 참고 사항  
 DE 만들고 프로그램에서 중단점을 하나 이상 발견 한 경우이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 콜백 함수 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugBreakpointEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[EnumBreakpoints](../../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md)|코드 위치에 발생 하는 모든 중단점의 열거자를 만듭니다.|  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)