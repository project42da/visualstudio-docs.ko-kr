---
title: "시작 후 시작 이벤트 보내기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], startup events
ms.assetid: 306ea0b4-6d9e-4871-8d8d-a4032d422940
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0620821ec908deed2c57ddfefb40763a48fd2074
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sending-startup-events-after-a-launch"></a>시작 후 시작 이벤트를 전송합니다.
디버그 엔진 (DE) 프로그램에 연결 되 면 일련의 시작 이벤트는 디버그 세션에 다시 보냅니다.  
  
 디버그 세션에 다시 전송 되는 시작 이벤트는 다음과 같습니다.  
  
-   엔진 생성 이벤트입니다.  
  
-   프로그램 생성 이벤트입니다.  
  
-   스레드 생성 및 모듈 로드 이벤트입니다.  
  
-   코드는 로드 하 고 바로 실행할 수 있지만 모든 코드를 실행 하기 전에 전송 로드 완료 이벤트  
  
    > [!NOTE]
    >  이 이벤트가 계속 되 면 전역 변수가 초기화 되 고 시작 루틴을 실행 합니다.  
  
-   가능한 다른 스레드 생성 및 모듈 로드 이벤트입니다.  
  
-   프로그램의 주 진입점와 같은 도달에 신호를 보냅니다 항목 시점 이벤트, **Main** 또는 `WinMain`합니다. 이 이벤트는 DE 이미 실행 중인 프로그램에 연결 되 면 일반적으로 전송 되지 않습니다.  
  
 프로그래밍 방식으로 DE 세션 디버그 관리자 (SDM)를 먼저 보냅니다는 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 엔진 생성 이벤트를 나타내는 인터페이스 뒤는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 을 프로그램 생성 이벤트를 나타냅니다.  
  
 일반적으로 다음 하나 이상의 [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) 스레드 만들기 이벤트 및 [IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md) 모듈 로드 이벤트입니다.  
  
 코드는 로드 하 고 바로 실행할 수 있지만 DE은 SDM 보내는 모든 코드가 실행 되기 전에 [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 완료 이벤트를 로드 합니다. 마지막으로, 프로그램이 이미 실행 되지 않는 경우는 DE 보냅니다는 [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) 항목 시점 이벤트, 신호 프로그램에서의 주 진입점에 도달 하 고 디버깅을 위해 준비 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [실행 제어](../../extensibility/debugger/control-of-execution.md)   
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)