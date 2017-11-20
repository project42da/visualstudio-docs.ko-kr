---
title: "실행 제어 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], control of execution
ms.assetid: 97071846-007e-450f-95a6-f072d0f5e61e
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 79d888e9b50d18b4a9d46a8914381db27f09698d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="control-of-execution"></a>실행 제어
디버그 엔진 (DE) 일반적으로 보내는 다음 이벤트 중 하나가 마지막 시작 이벤트로:  
  
-   새로 시작된 된 프로그램에 연결 하는 경우 항목 시점 이벤트  
  
-   로드 완료 이벤트를 이미 실행 중인 프로그램에 연결 하는 경우  
  
 두이 이벤트를 모두 의미는 DE IDE를 사용 하 여 사용자 로부터 응답을 받기 위해 대기 하는 이벤트를 중지 합니다. 자세한 내용은 참조 [작동 모드](../../extensibility/debugger/operational-modes.md)합니다.  
  
## <a name="stopping-event"></a>이벤트를 중지합니다.  
 디버그 세션에는 stopping 이벤트를 전송 된 때:  
  
1.  이벤트 인터페이스의 프로그램 및 현재 명령 포인터를 포함 하는 스레드를 얻을 수 있습니다.  
  
2.  IDE는 현재 소스 코드 파일 및 위치에 표시 되는 편집기에서 강조 표시를 결정 합니다.  
  
3.  디버그 세션 일반적으로이 이벤트에 응답 첫 번째 중지 프로그램의 호출 하 여 **계속** 메서드.  
  
4.  프로그램에서 대/소문자는 DE 디버그 세션에 중단점 이벤트를 보내는 중단점 같은 stopping 조건에 도달할 때까지 실행 합니다. 중단점 이벤트는 stopping 이벤트를 하 고는 DE 다시 사용자 응답을 대기 합니다.  
  
5.  과다, 단계씩 실행 하 여 사용자가 또는 IDE 함수에서 메시지를 호출 프로그램의 디버그 세션을 표시 하는 경우 `Step` (명령, 문 또는 선) 단계 및 단계의 종류의 단위를 전달 하는 메서드,-즉, 한 단계씩 코드 실행, 넘는 것인지 또는 함수를 벗어났습니다. 단계가 완료 되 면는 DE stopping 이벤트는 디버그 세션을 단계 완료 이벤트를 보냅니다.  
  
     또는  
  
     현재 명령 포인터에서 실행을 계속 하 여 사용자가을 IDE 라는 메시지를 표시 하는 프로그램을 호출 하면 디버그 세션 **Execute** 메서드. 다음 중지 상태에 도달할 때까지 프로그램 실행을 다시 시작 합니다.  
  
     또는  
  
     디버그 세션 특정 stopping 이벤트를 무시할 경우 디버그 세션 프로그램의를 호출 하는 **계속** 메서드. 프로그램 중단 조건이 발생 했을 때, 또는 함수에서 실행 된, 단계를 계속 합니다.  
  
 프로그래밍 방식으로 DE stopping 상태를 발견 하면 보내는 등의 중지 이벤트 [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 또는 [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) 방법으로 세션 디버그 관리자 (SDM)를 [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) 인터페이스입니다. DE 패스는 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 및 [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) 현재 명령 포인터를 포함 하는 스레드 및 프로그램을 나타내는 인터페이스입니다. SDM 호출 [IDebugThread2::EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 최상위 스택 프레임 및 호출 가져오려면 [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) 현재 명령와 관련 된 문서 컨텍스트를 가져오려면 포인터입니다. 이 문서의 컨텍스트에서 일반적으로 소스 코드 파일 이름, 줄 및 열 번호입니다. IDE 이러한를 사용 하 여 현재 명령 포인터를 포함 하는 소스 코드를 강조 표시 합니다.  
  
 SDM 일반적으로이 이벤트에 응답 첫 번째 중지를 호출 하 여 [IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)합니다. 프로그램에는 다음 경우는 DE 보냅니다는 중단점 같은 stopping 조건에 도달할 때까지 실행 한 [IDebugBreakpointEvent2 인터페이스](../../extensibility/debugger/reference/idebugbreakpointevent2.md) 은 SDM에 있습니다. 중단점 이벤트는 stopping 이벤트를 하 고는 DE 다시 사용자 응답을 대기 합니다.  
  
 사용자가 한 단계씩 코드 실행, over, 또는 함수에서 IDE 프롬프트 SDM를 호출 하는 경우 [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md), 전달 된 [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) (명령, 문 또는 줄) 및 [ STEPKIND](../../extensibility/debugger/reference/stepkind.md)즉,, 내부 또는 외부로 함수 한 단계씩 실행을 여부. 단계가 완료 되 면는 DE 보냅니다는 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 는 stopping 이벤트 SDM에 대 한 인터페이스입니다.  
  
 현재 명령 포인터에서 실행을 계속 하 여 사용자가을 IDE를 호출할 SDM 묻습니다 [IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md)합니다. 다음 중지 상태에 도달할 때까지 프로그램 실행을 다시 시작 합니다.  
  
 디버그 패키지가 특정 stopping 이벤트를 무시 하도록 경우 디버그 패키지를 호출 하는 SDM를 호출 하는 [IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)합니다. 프로그램 중단 조건이 발생 했을 때, 또는 함수에서 실행 된, 단계를 계속 합니다. 계속 하는 방법을 알 수 있도록 프로그램 단계별 실행 상태를 유지 함을 의미 합니다.  
  
 SDM에 수행 하는 호출 `Step`, **Execute**, 및 **계속** 는 비동기적 이며은 SDM 신속 하 게 반환할에 대 한 호출에 필요 함을 의미 합니다. DE 보냅니다는 SDM stopping 이벤트 하기 전에 동일한 스레드에서 `Step`, **Execute**, 또는 **계속** 은 SDM 중단을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)