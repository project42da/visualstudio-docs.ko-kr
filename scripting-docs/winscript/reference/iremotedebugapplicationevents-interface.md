---
title: "IRemoteDebugApplicationEvents 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplicationEvents interface
ms.assetid: 9626519e-910c-48e0-ae99-c711ce6628fd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04d40d3e03cfb9582075ec1be7abace963d1377f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationevents-interface"></a>IRemoteDebugApplicationEvents 인터페이스
`IRemoteDebugApplicationEvents` 인터페이스는 디버그 응용 프로그램에서 제공 하는 이벤트 인터페이스입니다. 이 인터페이스는 항상 디버거 스레드 내에서 호출 됩니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IRemoteDebugApplicationEvents` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IRemoteDebugApplicationEvents::OnConnectDebugger](../../winscript/reference/iremotedebugapplicationevents-onconnectdebugger.md)|디버거 처리 이벤트에 연결합니다.|  
|[IRemoteDebugApplicationEvents::OnDisconnectDebugger](../../winscript/reference/iremotedebugapplicationevents-ondisconnectdebugger.md)|디버거 처리 이벤트를 분리합니다.|  
|[IRemoteDebugApplicationEvents::OnSetName](../../winscript/reference/iremotedebugapplicationevents-onsetname.md)|설정 이름 이벤트를 처리합니다.|  
|[IRemoteDebugApplicationEvents::OnDebugOutput](../../winscript/reference/iremotedebugapplicationevents-ondebugoutput.md)|디버거 출력 이벤트를 처리합니다.|  
|[IRemoteDebugApplicationEvents::OnClose](../../winscript/reference/iremotedebugapplicationevents-onclose.md)|응용 프로그램 닫기 이벤트를 처리합니다.|  
|[IRemoteDebugApplicationEvents::OnEnterBreakPoint](../../winscript/reference/iremotedebugapplicationevents-onenterbreakpoint.md)|중단점 입력에 대 한 이벤트를 처리 합니다.|  
|[IRemoteDebugApplicationEvents::OnLeaveBreakPoint](../../winscript/reference/iremotedebugapplicationevents-onleavebreakpoint.md)|중단점 종료에 대 한 이벤트를 처리 합니다.|  
|[IRemoteDebugApplicationEvents::OnCreateThread](../../winscript/reference/iremotedebugapplicationevents-oncreatethread.md)|Create 스레드 이벤트를 처리합니다.|  
|[IRemoteDebugApplicationEvents::OnDestroyThread](../../winscript/reference/iremotedebugapplicationevents-ondestroythread.md)|스레드 제거 이벤트를 처리합니다.|  
|[IRemoteDebugApplicationEvents::OnBreakFlagChange](../../winscript/reference/iremotedebugapplicationevents-onbreakflagchange.md)|Break 플래그 변경 될 때 이벤트를 처리 합니다.|