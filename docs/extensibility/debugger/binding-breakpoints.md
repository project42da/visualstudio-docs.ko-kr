---
title: 중단점을 바인딩하 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- breakpoints, binding
ms.assetid: 70737387-c52f-4dae-8865-77d4b203bf25
caps.latest.revision: 12
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 55416d6b156055d967424476f5add3b4ed75d18d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="binding-breakpoints"></a>바인딩 중단점
사용자는 중단점을 설정한 경우 아마도 F9 키를 눌러 IDE는 요청을 생성 및 메시지 중단점을 만들려고 하면 디버그 세션 합니다.  
  
## <a name="setting-a-breakpoint"></a>중단점 설정  
 중단점 설정 이므로 두 단계로, 코드 또는 중단점 영향을 받는 데이터가 아직 사용할 수 없습니다. 먼저, 중단점을 설명 해야 합니다 하 고 그런 다음 코드나 데이터에 사용할 수 있게 되 면, 그에 연결 해야 해당 코드 또는 데이터를 다음과 같습니다.  
  
1.  관련 디버그 엔진 (DEs)에서 중단점을 요청 하 고 중단점에 바인딩된 코드 또는 데이터를 사용할 수 있도록 합니다.  
  
2.  중단점 요청이 모든 관련 DEs를 전송 하는 디버그 세션에 전송 됩니다. 중단점을 처리 하도록 선택 하는 모든 DE 중단점 보류 중인 해당 만듭니다.  
  
3.  디버그 세션은 보류 중인 중단점을 수집 하 고 디버그 패키지 (Visual Studio의 디버깅 구성)으로 다시 보냅니다.  
  
4.  디버그 패키지가 메시지 코드 또는 데이터에 보류 중인 중단점을 바인딩할 디버그 세션을 표시 합니다. 디버그 세션을 모든 관련 DEs로이 요청을 보냅니다.  
  
5.  DE 중단점을 바인딩할 수 있으면 중단점 디버그 세션에 다시 이벤트를 바인딩된 보냅니다. 그렇지 않은 경우 중단점 오류 이벤트를 대신 보냅니다.  
  
## <a name="pending-breakpoints"></a>보류 중인 중단점  
 보류 중인 중단점 여러 코드 위치에 바인딩할 수 있습니다. 예를 들어 c + + 템플릿에 대 한 소스 코드의 줄 템플릿에서 생성 된 모든 코드 시퀀스를 바인딩할 수 있습니다. 디버그 세션 중단점 바인딩된 이벤트를 사용 하 여 이벤트를 보낸 시간에 중단점을 바인딩할 코드 컨텍스트를 열거할 수 있습니다. 코드 컨텍스트는 DE 여러 중단점 바인딩된 각 바인딩 요청에 대 한 이벤트를 보낼 수 있으므로 나중 바인딩할 수 있습니다. 그러나 한 DE 바인딩 요청이 당 하나만 중단점 오류 이벤트를 보내야 합니다.  
  
## <a name="implementation"></a>구현  
 디버그 패키지가 세션 디버그 (SDM) 관리자를 호출 하 고 일단 프로그래밍 방식으로 [IDebugBreakpointRequest2](../../extensibility/debugger/reference/idebugbreakpointrequest2.md) 인터페이스를 래핑하는 [BP_REQUEST_INFO](../../extensibility/debugger/reference/bp-request-info.md) 구조를 설명 하는 중단점을 설정할 수 있습니다. 중단점의 여러 형태를 사용할 수 있지만 궁극적으로 코드 또는 데이터 컨텍스트를 확인 합니다.  
  
 SDM 호출 하 여이 호출으로 각 관련 DE 전달 해당 [CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) 메서드. DE가 중단점 처리를 위해서는 만들고 반환는 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 인터페이스입니다. SDM 이러한 인터페이스를 수집 하 고 단일 디버그 패키지가 다시 전달 `IDebugPendingBreakpoint2` 인터페이스입니다.  
  
 지금까지 이벤트가 생성 되었습니다.  
  
 디버그 패키지가 다음 호출 하 여 코드 또는 데이터에 보류 중인 중단점을 바인딩할 하려고 [바인딩할](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)는 DE에서 구현 되는 합니다.  
  
 중단점이 바인딩되지 않은 경우는 DE 보냅니다는 [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) 디버그 패키지에 대 한 이벤트 인터페이스입니다. 모든 코드 컨텍스트 (또는 단일 데이터 컨텍스트)를 열거 하려면이 인터페이스를 호출 하 여 중단점 바인딩할 디버그 패키지 사용 하 여 [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md)를 하나 이상 반환 하는 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) 인터페이스입니다. [GetBreakpointResolution](../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md) 반환 인터페이스는 [IDebugBreakpointResolution2](../../extensibility/debugger/reference/idebugbreakpointresolution2.md) 인터페이스 및 [GetResolutionInfo](../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) 반환는 [BP_ RESOLUTION_INFO](../../extensibility/debugger/reference/bp-resolution-info.md) 코드 또는 데이터 컨텍스트를 포함 하는 공용 구조체입니다.  
  
 단일 보냅니다는 DE는 중단점을 바인딩할 수 없는 경우 [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) 디버그 패키지에 대 한 이벤트 인터페이스입니다. 호출 하 여 오류 유형 (오류 또는 경고) 및 정보 메시지를 검색 하는 디버그 패키지가 [GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md)옵니다 [GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) 및 [ GetResolutionInfo](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)합니다. 반환 합니다.는 [BP_ERROR_RESOLUTION_INFO](../../extensibility/debugger/reference/bp-error-resolution-info.md) 오류 유형 및 메시지를 포함 하는 구조입니다.  
  
 DE 중단점을 처리 하지만 바인딩할 수 없습니다, 유형의 오류가 반환 `BPET_TYPE_ERROR`합니다. IDE 내에서 중단점 문자 모양 소스 코드 줄의 왼쪽에는 느낌표 문자 모양을 배치 하 고 디버그 패키지가 오류 대화 상자를 표시 하 여 응답 합니다.  
  
 DE에서 바인딩할 수 있습니다는 DE 중단점을 처리 하지만 일부 다른 바인딩할 수 없는 경우에 경고를 반환 합니다. IDE 내에서 중단점 문자 모양 소스 코드 줄의 왼쪽에 문자 모양을 질문을 배치 하 여 응답 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)