---
title: "IDebugBreakEvent2 | Microsoft Docs"
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
  - "IDebugBreakEvent2"
helpviewer_keywords: 
  - "IDebugBreakEvent2 인터페이스"
ms.assetid: 57dfdbc2-4e68-4dbf-9579-006cd6fb1c62
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugBreakEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 세션 디버그 매니저 \(SDM\) 비동기 나누기가 성공적으로 완료 되었음을 알려 줍니다.  
  
## 구문  
  
```  
IDebugBreakEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE 나누기 사용자 프로그램에 지원 하기 위해이 인터페이스를 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다 \(SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스\)입니다.  
  
## 호출자에 대 한 참고 사항  
 SDM 호출 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) 사용자를 일시 중지할 수 디버깅 중인 프로그램 요청 했습니다 경우.  프로그램이 성공적으로 일시 중지 된 경우는 DE 보냅니다 있는 `IDebugBreakEvent2` 이벤트입니다.  이 이벤트를 사용 하 여 보냅니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 콜백 함수 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 합니다.  
  
## 설명  
 예를 들어, 사용자가 선택할 수 있습니다는  **중단 모든** 에  **디버그** 메뉴에서 무한 루프를 실행 중인 프로그램을 중단 합니다.  호출 하 여 중지 하는 프로그램은 SDM 알려 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md).  DE 보냅니다 `IDebugBreakEvent2` 때 마지막으로 프로그램을 중지 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)