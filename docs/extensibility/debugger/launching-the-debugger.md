---
title: "디버거 시작 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], launching the debugger
- debugger [Debugging SDK], launching
ms.assetid: f24da1a1-f923-48b4-989f-18a22b581d1b
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 23fd772b74c4caafbde37541933c38e306f9dc75
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="launching-the-debugger"></a>디버거 시작
디버거 시작 메서드 및 이벤트와 해당 하는 적절 한 특성의 순서를 전송 해야 합니다.  
  
## <a name="sequences-of-methods-and-events"></a>메서드 및 이벤트의 시퀀스  
  
1.  세션 디버그 관리자 (SDM)를 선택 하 여 호출 됩니다는 **디버그** 메뉴를 선택한 다음 **시작**합니다. 참조 [프로그램을 시작](../../extensibility/debugger/launching-a-program.md) 자세한 정보에 대 한 합니다.  
  
2.  SDM 호출 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드.  
  
3.  디버그 엔진 (DE) 프로세스 모델을 기반으로 `IDebugProgramNodeAttach2::OnAttach` 메서드 다음 결정 하는 다음 방법 중 하나를 반환 합니다.  
  
     경우 `S_FALSE` 가상 컴퓨터 중 로드 되도록 디버그 엔진 (DE)가 반환 됩니다.  
  
     또는  
  
     경우 `S_OK` 반환 되 면는 DE 로드 하는 것은 SDM의 프로세스입니다. 다음은 SDM 다음 작업을 수행합니다.  
  
    1.  호출 [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) 는 DE의 엔진 정보를 가져옵니다.  
  
    2.  배치는 DE를 만듭니다.  
  
    3.  호출 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md)합니다.  
  
4.  DE 보냅니다는 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 와 SDM에는 `EVENT_SYNC` 특성입니다.  
  
5.  DE 보냅니다는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 와 SDM에는 `EVENT_SYNC` 특성입니다.  
  
6.  DE 보냅니다는 [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) 와 SDM에는 `EVENT_SYNC` 특성입니다.  
  
7.  DE 보냅니다는 [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 와 SDM에는 `EVENT_SYNC` 특성입니다.  
  
8.  DE 보냅니다는 [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) 와 SDM에는 `EVENT_SYNC` 특성입니다.  
  
## <a name="see-also"></a>참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)   
 [프로그램 시작](../../extensibility/debugger/launching-a-program.md)