---
title: "연결 및 분리 하는 프로그램 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, attaching to programs
- debug engines, detaching from programs
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 71f678852b4d16d0b7c6f150abae03c6c4cdcad4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="attaching-and-detaching-to-a-program"></a>연결 및 분리 하는 프로그램
디버거를 연결 메서드 및 특정 속성을 가진 이벤트의 순서를 전송 해야 합니다.  
  
## <a name="sequence-of-methods-and-events"></a>메서드 및 이벤트의 시퀀스  
  
1.  세션 디버그 관리자 (SDM) 호출 하면 중지는 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드.  
  
     디버그 엔진 (DE) 프로세스 모델을 기반으로 `IDebugProgramNodeAttach2::OnAttach` 메서드 다음 결정 하는 다음 방법 중 하나를 반환 합니다.  
  
     경우 `S_FALSE` 디버그 엔진 프로그램에 연결 되었고 성공적으로 반환 됩니다. 그렇지 않은 경우는 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드를 호출 하 여 연결 프로세스를 완료 합니다.  
  
     경우 `S_OK` 은 SDM와 동일한 프로세스에 로드 되는 DE가 반환 됩니다. SDM 다음 작업을 수행합니다.  
  
    1.  호출 [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) 는 DE의 엔진 정보를 가져옵니다.  
  
    2.  배치는 DE를 만듭니다.  
  
    3.  호출 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md)합니다.  
  
2.  DE 보냅니다는 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 와 SDM에는 `EVENT_SYNC` 특성입니다.  
  
3.  DE 보냅니다는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 와 SDM에는 `EVENT_SYNC` 특성입니다.  
  
4.  DE 보냅니다는 [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 와 SDM에는 `EVENT_SYNC_STOP` 특성입니다.  
  
 프로그램에서 분리는 단순, 2 단계 프로세스는 다음과 같습니다.  
  
1.  SDM 호출 [분리](../../extensibility/debugger/reference/idebugprogram2-detach.md)합니다.  
  
2.  DE 보냅니다는 [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)