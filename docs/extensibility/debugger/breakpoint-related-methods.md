---
title: "중단점 관련 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], breakpoint methods
- breakpoints, methods
ms.assetid: a6f77bf0-bf81-443f-8683-5f12075bbe10
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f5bf80b78545242a625b9c3e212c101712ecbd9e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="breakpoint-related-methods"></a>중단점 관련 메서드
디버그 엔진 (DE)에 중단점 설정을 지원 해야 합니다. Visual Studio 디버깅 중단점의 형식을 지원 합니다.  
  
-   바인딩된  
  
     UI를 통해 요청 하 고 지정한 코드 위치에 성공적으로 바인딩  
  
-   보류 중  
  
     UI 하지만 실제에 아직 바인딩되지 않았습니다 지침을 통해 요청  
  
## <a name="discussion"></a>토론  
 예를 들어 보류 중인 중단점 지침 아직 로드 되지 않은 경우에 발생 합니다. 코드 로드 될 때 지정 된 위치에 코드를 즉 바인딩할, 코드에서 중단 명령을 삽입 하는 중단점 시도 보류 중입니다. 이벤트를 나타내는 바인딩 성공 또는 바인딩 오류가 발생 했다는 알리기 위해 세션 디버그 관리자 (SDM)에 전송 됩니다.  
  
 보류 중인 중단점에는 또한 해당 바인딩된 중단점의 내부 목록을 관리합니다. 중단점 대기 중인 한 많은 중단점을 삽입할 코드에서 하면 수 있습니다. 해당 바인딩된 중단점 및 Visual Studio UI 디버깅 보류 중단점의 트리 뷰를 보여 줍니다.  
  
 생성 및 사용 보류 중단점 구현 해야는 [IDebugEngine2::CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) 으로 메서드는 다음과 같은 방법을 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 인터페이스입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)|지정 된 있는지 여부를 결정 중단점 보류 중인 코드 위치에 바인딩할 수 있습니다.|  
|[바인딩](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)|바인딩할 지정 된 중단점 보류 중인 하나 이상의 코드 위치입니다.|  
|[우편 번호](../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)|보류 중인 중단점의 상태를 가져옵니다.|  
|[GetBreakpointRequest](../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)|보류 중인 중단점을 만드는 데 중단점 요청을 가져옵니다.|  
|[사용 하도록 설정](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)|보류 중인 중단점의 활성화 상태를 토글합니다.|  
|[EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)|보류 중인 중단점에서 바인딩된 모든 중단점을 열거 합니다.|  
|[EnumErrorBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)|보류 중인 중단점에서 발생 하는 모든 오류 중단점을 열거 합니다.|  
|[삭제](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)|보류 중인 중단점 및 여기에서 바인딩된 모든 중단점을 삭제 합니다.|  
  
 바인딩된 중단점 및 오류 중단점 열거의 모든 메서드를 구현 해야 [IEnumDebugBoundBreakpoints2](../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md) 및의 [IEnumDebugErrorBreakpoints2](../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)합니다.  
  
 보류 된 코드에 바인딩하는 중단점 위치는 다음 구현 해야 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) 메서드.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPendingBreakpoint](../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)|중단점을 포함 하는 보류 중인 중단점을 가져옵니다.|  
|[우편 번호](../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)|바인딩된 중단점의 상태를 가져옵니다.|  
|[GetBreakpointResolution](../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)|중단점을 설명 하는 중단점 해상도를 가져옵니다.|  
|[사용 하도록 설정](../../extensibility/debugger/reference/idebugboundbreakpoint2-enable.md)|중단점을 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[삭제](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)|바인딩된 중단점을 삭제합니다.|  
  
 해상도 및 정보는 다음의 구현에 필요한 요청 [IDebugBreakpointResolution2](../../extensibility/debugger/reference/idebugbreakpointresolution2.md) 메서드.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetBreakpointType](../../extensibility/debugger/reference/idebugbreakpointresolution2-getbreakpointtype.md)|해상도가 나타내는 중단점의 형식을 가져옵니다.|  
|[GetResolutionInfo](../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)|중단점을 설명 하는 중단점 확인 정보를 가져옵니다.|  
  
 바인딩하는 동안 발생할 수 있는 오류 확인을 다음의 구현이 필요 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) 메서드.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md)|오류 중단점을 포함 하는 보류 중인 중단점을 가져옵니다.|  
|[GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md)|오류 중단점을 설명 하는 중단점 오류 해상도를 가져옵니다.|  
  
 바인딩하는 동안 발생할 수 있는 오류를 해결 해야는 다음과 같은 방법을 [IDebugErrorBreakpointResolution2](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md)합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetBreakpointType](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getbreakpointtype.md)|중단점의 형식을 가져옵니다.|  
|[GetResolutionInfo](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)|중단점의 해결 방법 정보를 가져옵니다.|  
  
 메서드를 구현 해야 중단점에서의 소스 코드를 보면 [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) 의 메서드 및/또는 [IDebugStackFrame2::GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)