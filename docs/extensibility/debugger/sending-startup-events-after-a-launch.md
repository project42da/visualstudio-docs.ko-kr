---
title: "시작 된 후 시작 이벤트를 전송합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK] 시작 이벤트"
ms.assetid: 306ea0b4-6d9e-4871-8d8d-a4032d422940
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# 시작 된 후 시작 이벤트를 전송합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\)에 프로그램을 연결 하면 디버그 세션을 다시 시작 이벤트를 보냅니다.  
  
 디버그 세션 전송 시작 이벤트는 다음과 같습니다.  
  
-   엔진을 만드는 이벤트입니다.  
  
-   프로그램 생성 이벤트입니다.  
  
-   스레드 만들기 및 모듈 로드 이벤트.  
  
-   코드 로드 하 고 실행할 수 있을 때만 코드를 실행 하기 전에 로드 완료 이벤트  
  
    > [!NOTE]
    >  이 이벤트가 계속 될 때 전역 변수를 초기화 및 시작 루틴을 실행 합니다.  
  
-   다른 가능한 스레드 생성 및 모듈 로드 이벤트.  
  
-   엔트리 포인트 프로그램의 주 진입점에 같은 도달 한다는 신호를 보내는 이벤트를  **주** 또는 `WinMain`.  DE은 이미 실행 중인 프로그램에 연결 하는 경우이 이벤트는 일반적으로 전송 되지 않습니다.  
  
 프로그래밍 방식으로 DE 세션 디버그 매니저 \(SDM\)을 먼저 보냅니다는  [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 엔진을 만드는 이벤트를 나타내는 인터페이스 뒤에  [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md), 프로그램 작성 이벤트를 나타냅니다.  
  
 이것은 일반적으로 하나 이상의 뒤  [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) 스레드 만들 이벤트와  [IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md) 모듈 로드 이벤트.  
  
 로드 된 및 실행할 준비가 되었습니다. 코드 이지만 임의의 코드를 실행 하기 전에 DE SDM을 보내는 경우는  [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 로드 완료 이벤트입니다.  마지막으로 프로그램이 이미 실행 되 고 있지 않으면 해당 DE 보냅니다는  [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) 엔트리 포인트 이벤트를 신호 프로그램의 주 진입점에 도달 하 고 디버깅을 위한 준비가 되었습니다.  
  
## 참고 항목  
 [실행 제어](../../extensibility/debugger/control-of-execution.md)   
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)