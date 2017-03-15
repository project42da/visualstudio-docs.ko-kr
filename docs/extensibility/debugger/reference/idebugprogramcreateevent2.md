---
title: "IDebugProgramCreateEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramCreateEvent2"
helpviewer_keywords: 
  - "IDebugProgramCreateEvent2 인터페이스"
ms.assetid: b19a7934-6179-4a68-9075-bd7dcd640b05
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IDebugProgramCreateEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진 \(DE\) 프로그램에 연결 되 면 세션 디버그 매니저 \(SDM\) 보내집니다.  
  
## 구문  
  
```  
IDebugProgramCreateEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE 또는 사용자 지정 포트 공급자 프로그램, 일반적으로 프로그램이 연결 되어 동시에 생성 되었음을 보고 하려면이 인터페이스를 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하는 `QueryInterface` 메서드에 액세스 하는 `IDebugEvent2` 인터페이스.  
  
## 호출자에 대 한 참고 사항  
 DE 또는 사용자 지정 포트 공급자 만들고이 이벤트 개체를 생성 하는 프로그램을 보고 하도록 보냅니다.  DE의 사용 하 여이 이벤트를 보냅니다에서 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 되는 콜백 함수입니다.  이 이벤트를 사용 하는 사용자 지정 포트 공급자 보냅니다 있는 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) 인터페이스입니다.  
  
## 설명  
 DE 또는 사용자 지정 포트 공급자 새 게시 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스를 호출 하 여 [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)