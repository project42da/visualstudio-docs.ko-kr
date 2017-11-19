---
title: "제어 프로그램 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], control of execution
ms.assetid: 6be80904-e66c-4cae-8891-1113b799fb01
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cb69afe513010a7da4b4a85669bbc5f145f8dbc5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="program-control"></a>프로그램 제어
Visual Studio의 다음 단계별 실행의 모든 디버깅 및 루틴을 계속 프로그램 수준에서 발생 합니다.  
  
-   특정 프레임 환경에서 실행 될 다음 명령으로 컴퓨터를 설정 즉, 다음 문 설정  
  
-   즉, 단계별 실행 모드에서 나가려면 계속 실행  
  
-   다음 명령으로 단계별 실행  
  
-   현재 단계별 실행 모드를 계속  
  
-   프로그램에 포함 된 스레드 일시 중단  
  
-   프로그램에 포함 된 스레드 재개  
  
> [!NOTE]
>  호출 스택을 보려면 스레드 수준에서 구현 됩니다. 모든 메서드를 구현 해야 합니다는 스레드의 호출 스택을 볼 때 프레임 정보를 열거 하는 [IEnumDebugFrameInfo2](../../extensibility/debugger/reference/ienumdebugframeinfo2.md) 인터페이스입니다.  
  
## <a name="methods-of-program-control"></a>프로그램 제어의 메서드  
 다음 표에서의 메서드를 보여 줍니다. [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 최소 기능 디버그 엔진 (DE) 및 실행 제어에 대 한 구현 되어야 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md)|계속 중지 된 상태에서 프로그램에 포함 된 모든 스레드를 실행 합니다. 실행 제어에 필요합니다.|  
|[IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)|계속 중지 된 상태에서 프로그램에 포함 된 모든 스레드를 실행 합니다. 실행 제어에 필요합니다.|  
|[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)|지정 된 스레드에 대 한 단계를 수행합니다. 프로그램에 포함 된 모든 다른 스레드가 실행을 계속 합니다. 실행 제어에 필요합니다.|  
  
 다중 스레드 프로그램에 대 한 구현 해야는 [IDebugProgram2::EnumThreads](../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) 메서드와의 모든 메서드는 [IEnumDebugThreads2](../../extensibility/debugger/reference/ienumdebugthreads2.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)