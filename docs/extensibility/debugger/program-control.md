---
title: "프로그램 제어 | Microsoft Docs"
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
ms.assetid: 6be80904-e66c-4cae-8891-1113b799fb01
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 프로그램 제어
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Studio 디버깅을 모두 다음과 같은 단계별 실행 및 계속 루틴 프로그램 수준에서 발생 합니다.  
  
-   다음 문 설정, 컴퓨터에 특정 프레임 환경에서 실행 될 다음 명령을 설정  
  
-   계속 실행, 단계별 실행 모드를 종료 하면  
  
-   다음 명령으로 한 단계씩 실행  
  
-   현재 단계별 실행 모드에서 계속합니다.  
  
-   프로그램에서 포함 된 스레드를 일시 중단 합니다.  
  
-   프로그램에 포함 된 스레드를 다시 시작  
  
> [!NOTE]
>  호출 스택을 표시 스레드 수준에서 구현 됩니다.  호출 스택이 스레드 볼 때 프레임 정보를 열거 하는 모든 메서드를 구현 해야는  [IEnumDebugFrameInfo2](../../extensibility/debugger/reference/ienumdebugframeinfo2.md) 인터페이스입니다.  
  
## 프로그램 컨트롤의 메서드  
 다음 테이블의 메서드를 보여 줍니다.  [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 는 해야 합니다 구현할 수는 최소한으로 작동 되는 디버그 엔진 \(DE\) 및 실행 제어를 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md)|계속 중지 된 상태에서 프로그램에 포함 된 모든 스레드가 실행 됩니다.  실행 제어를 지정합니다.|  
|[IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)|계속 중지 된 상태에서 프로그램에 포함 된 모든 스레드가 실행 됩니다.  실행 제어를 지정합니다.|  
|[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)|지정 된 스레드를 한 단계를 수행합니다.  프로그램에 포함 된 모든 스레드가 실행을 계속 합니다.  실행 제어를 지정합니다.|  
  
 다중 스레드 프로그램의 경우에 구현 해야는  [IDebugProgram2::EnumThreads](../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) 의 모든 메서드 및 메서드는  [IEnumDebugThreads2](../../extensibility/debugger/reference/ienumdebugthreads2.md) 인터페이스.  
  
## 참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)