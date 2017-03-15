---
title: "IDebugProcessDestroyEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProcessDestroyEvent2"
helpviewer_keywords: 
  - "IDebugProcessDestroyEvent2"
ms.assetid: 1b8e0528-95bc-48fa-9653-2cea66c8dc3a
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IDebugProcessDestroyEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 프로세스 종료 됩니다 예외적인, 종료 또는에서 분리 됩니다 전송 됩니다.  
  
## 구문  
  
```  
IDebugProcessDestroyEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 또는 사용자 지정 포트 공급자 프로세스 종료 되었음을 보고 하기 위해이 인터페이스를 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 DE 또는 사용자 지정 포트 공급자 만들고이 이벤트 개체가 프로세스의 종료를 보고 하 보냅니다.  DE의 사용 하 여이 이벤트를 보냅니다에서 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 되 면 SDM가 제공 되는 콜백 함수입니다.  이 이벤트를 사용 하는 사용자 지정 포트 공급자 보냅니다 있는 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) 인터페이스입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)