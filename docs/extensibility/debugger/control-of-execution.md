---
title: "실행 제어 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 실행 제어"
ms.assetid: 97071846-007e-450f-95a6-f072d0f5e61e
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 실행 제어
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

일반적으로 디버그 엔진 \(DE\) 다음 이벤트 중 하나가 마지막으로 startup 이벤트로 보냅니다.  
  
-   새로 시작된 된 프로그램을 연결 하는 경우 엔트리 포인트 이벤트  
  
-   이미 실행 중인 프로그램에 연결 하는 경우 로드 완료 이벤트를  
  
 두이 이벤트가 이벤트를 통해 IDE는 DE 사용자 로부터의 응답 기다림을 의미를 중지 합니다.  자세한 내용은  [작동 모드](../../extensibility/debugger/operational-modes.md).  
  
## 이벤트 중지  
 언제 중지 이벤트를 디버그 세션에 전송 됩니다.  
  
1.  프로그램 및 현재 명령 포인터를 포함 하는 스레드는 이벤트 인터페이스를 가져올 수 있습니다.  
  
2.  IDE의 현재 소스 코드 파일 및 편집기에서 강조 표시 위치를 결정 합니다.  
  
3.  프로그램의 호출 하 여 일반적으로이 첫 번째 중지 이벤트에 디버그 세션을 응답  **계속** 메서드가 있습니다.  
  
4.  케이스는 DE 디버그 세션에 중단점 이벤트 전송 중단점에 도달 하는 것과 같은 중지 조건이 발생할 때까지 프로그램이 다음 실행 됩니다.  중단점 이벤트는 중지 이벤트 이며 다시 DE는 사용자 응답을 기다립니다.  
  
5.  사용자 선택,가 위, 단계 또는 함수를 호출 하는 프로그램의 디버그 세션 IDE를 묻는 경우 `Step` 단위 \(명령, 문 또는 선\) 단계와 단계의 종류를 전달 하는 메서드를\-,로, 위 또는 함수 외부로 단계를.  단계가 완료 되 면, DE는 단계 완료 이벤트 중지 이벤트를 디버그 세션에 전송 합니다.  
  
     또는  
  
     현재 명령 포인터에서 실행을 계속 하려면 사용자가 선택 하는 경우 호출 하는 프로그램의 디버그 세션 IDE를 묻는  **Execute** 메서드가 있습니다.  다음 중지 조건이 발생할 때까지 프로그램 실행을 다시 시작 합니다.  
  
     또는  
  
     디버그 세션 특정 중지 이벤트를 무시 하는 경우 프로그램의 디버그 세션 호출  **계속** 메서드가 있습니다.  중지 조건이 발생 하는 경우에, 위 또는 함수 외부로 프로그램 스테핑 했습니다 경우 단계를 계속 합니다.  
  
 프로그래밍 방식으로 DE 중지 조건이 발생 한 경우와 같은 중지 이벤트가 보냅니다  [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 또는  [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) 통해 세션 디버그 매니저 \(SDM\)에  [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) 인터페이스입니다.  DE 가공 패스는  [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 및  [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) 프로그램 및 현재 명령 포인터를 포함 하는 스레드를 나타내는 인터페이스입니다.  SDM 호출  [IDebugThread2::EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 위쪽 스택 프레임 및 호출 하는 데  [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) 는 현재 명령 포인터와 연관 된 문서 컨텍스트를 가져올 수 있습니다.  이 문서의 컨텍스트는 일반적으로 소스 코드 파일 이름, 줄 및 열 번호입니다.  IDE는 이러한 현재 명령 포인터를 포함 하는 소스 코드를 사용 합니다.  
  
 호출 하 여 일반적으로이 첫 번째 중지 이벤트에는 SDM을 응답  [IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md).  케이스는 DE 보내는 중단점에 도달 하는 것과 같은 중지 조건이 발생할 때까지 다음 프로그램이 실행 되는  [IDebugBreakpointEvent2 인터페이스](../../extensibility/debugger/reference/idebugbreakpointevent2.md) 는 SDM을.  중단점 이벤트는 중지 이벤트 이며 다시 DE는 사용자 응답을 기다립니다.  
  
 가 위, 단계적으로 사용자가 선택 하거나 함수를 호출 하는 SDM IDE를 묻는 경우  [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md),이 전달의  [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) \(명령, 문 또는 선\) 하는  [STEPKIND](../../extensibility/debugger/reference/stepkind.md),로, 위 또는 함수 외부로 단계를.  단계가 완료 되 면, DE를 보냅니다에서  [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 인터페이스는 중지 이벤트는 SDM.  
  
 현재 명령 포인터에서 실행을 계속 하려면 사용자가 선택 하는 경우 호출 하는 SDM IDE를 묻는  [IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md).  다음 중지 조건이 발생할 때까지 프로그램 실행을 다시 시작 합니다.  
  
 디버그 패키지 특정 중지 이벤트를 무시 하는 경우 디버그 패키지를 호출 하는 SDM 호출  [IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md).  중지 조건이 발생 하는 경우에, 위 또는 함수 외부로 프로그램 스테핑 했습니다 경우 단계를 계속 합니다.  계속 하는 방법을 알 수 있도록 프로그램 단계별 실행 상태를 유지 함을 의미 합니다.  
  
 SDM을 수행 하는 호출 `Step`,  **Execute**, 및  **계속** 는 SDM 호출이 반환을 신속 하 게 필요 함을 의미 합니다. 비동기입니다.  DE은 SDM 중지 이벤트 하기 전에 동일한 스레드에서 보냅니다 경우 `Step`,  **Execute**, 또는  **계속** 반환 하는 SDM을 중단 합니다.  
  
## 참고 항목  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)