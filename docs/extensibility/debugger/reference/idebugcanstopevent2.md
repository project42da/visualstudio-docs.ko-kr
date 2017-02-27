---
title: "IDebugCanStopEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCanStopEvent2"
helpviewer_keywords: 
  - "IDebugBreakpointRequest2 인터페이스"
ms.assetid: 784bd5b1-4a3f-4455-b313-c4c9a82555a5
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugCanStopEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 세션 디버그 매니저 \(SDM\) 코드의 현재 위치에서 중지를 요청 하는 데 사용 됩니다.  
  
## 구문  
  
```  
IDebugCanStopEvent2 : IUknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 소스 코드를 단계별로 실행을 지원 하기 위해이 인터페이스를 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다 \(SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스\)입니다.  
  
 이 인터페이스의 구현을 호출 하는 SDM의 통신 해야 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) 는 디버그 엔진입니다.  예를 들어,이 디버그 엔진 메시지 처리 스레드를 게시 한 메시지와 함께 할 수 있습니다 또는이 인터페이스를 구현 하는 개체 디버그 엔진에 대 한 참조를 보유 하 고 디버그 엔진에 전달 되는 플래그를 콜백할 수 `IDebugCanStopEvent2::CanStop`.  
  
## 호출자에 대 한 참고 사항  
 이 메서드는 DE 실행 하 고 있는 DE 계속 하도록 요청 될 때마다 코드를 단계별로 실행 되는 DE 보낼 수 있습니다.  이 이벤트를 사용 하 여 보냅니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 콜백 함수 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugCanStopEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)|이 이벤트에 대 한 이유를 가져옵니다.|  
|[CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)|디버깅 중인 프로그램 해야 합니다이 이벤트 \(및 보내기 중지 사유를 설명 하는 이벤트\)의 위치를 중지 계속 실행 하기만 하면 지정 합니다.|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)|이 이벤트의 위치를 설명 하는 문서 컨텍스트를 가져옵니다.|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)|이 이벤트의 위치를 설명 하는 코드 컨텍스트를 가져옵니다.|  
  
## 설명  
 사용자 단계 함수 및 해당 DE 찾아 디버그 정보가 있습니다 또는 디버그 정보가 있지만 DE은 그 위치에 대 한 소스 코드가 표시 될 수 있습니다 경우 알 수 없습니다 경우이 인터페이스는 DE를 보냅니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugStepCompleteEvent2](../../../extensibility/debugger/reference/idebugstepcompleteevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)