---
title: "중단점 관련 메서드 | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK] 중단점 메서드"
  - "중단점, 메서드"
ms.assetid: a6f77bf0-bf81-443f-8683-5f12075bbe10
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# 중단점 관련 메서드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\)의 중단점 설정을 지원 해야 합니다.  중단점에 다음과 같은 유형의 Visual Studio 디버깅을 지원합니다.  
  
-   바인딩된 모드  
  
     UI를 통해 요청 하 고 지정 된 코드 위치에 성공적으로 바인딩  
  
-   보류 중  
  
     UI 있지만 실제 수 없습니다 아직 바운드 지침을 요청 했습니다.  
  
## 토론  
 예를 들어 보류 중단점 지시 아직 로드 되지 않은 경우에 발생 합니다.  코드를 보류 중단점 시도 즉 코드의 지정 된 위치에 연결, break 명령에 코드를 삽입 합니다 로드 될 때.  이벤트 세션 디버그 매니저 \(SDM\)에 성공적으로 바인딩 나타내려면 또는 바인딩 오류를 알리기 위해 전송 됩니다.  
  
 보류 중단점도 자체 내부 해당 바인딩된 중단점 목록을 관리합니다.  보류 중인 중단점 삽입 여러 중단점을 코드에서 발생할 수 있습니다.  Visual Studio UI 디버깅 보류 중단점의 트리 뷰를 표시 하 고 해당 중단점을 바인딩할.  
  
 만들기와 보류 중단점 사용을 구현 하는 요구는  [IDebugEngine2::CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) 메서드 뿐 아니라 다음과 같은 방법 중  [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 인터페이스입니다.  
  
|메서드|설명|  
|---------|--------|  
|[CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)|지정 된 여부를 확인 합니다 보류 중단점이 있는 코드 위치를 바인딩할 수 있습니다.|  
|[바인딩](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)|지정 된 보류 중단점이 하나 이상의 코드 위치에 바인딩합니다.|  
|[GetState](../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)|보류 중단점의 상태를 가져옵니다.|  
|[GetBreakpointRequest](../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)|보류 중단점을 만드는 데 사용 되는 중단점 요청을 가져옵니다.|  
|[사용](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)|보류 중단점의 활성화 상태를 설정\/해제 합니다.|  
|[EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)|보류 중단점에서 바인딩된 중단점을 모두 열거 합니다.|  
|[EnumErrorBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)|보류 중단점에서 발생 하는 모든 오류 중단점을 열거 합니다.|  
|[Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)|보류 중단점 및 바인딩된에서 모든 중단점을 삭제 합니다.|  
  
 바인딩된 중단점 및 중단점 오류를 열거 하는 모든 메서드를 구현 해야  [IEnumDebugBoundBreakpoints2](../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md) 및  [IEnumDebugErrorBreakpoints2](../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md).  
  
 보류 바인딩하는 코드에 중단점 위치 해야 다음 구현  [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) 메서드가 있습니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetPendingBreakpoint](../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)|중단점이 있는 보류 중인 중단점을 가져옵니다.|  
|[GetState](../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)|바인딩된 중단점의 상태를 가져옵니다.|  
|[GetBreakpointResolution](../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)|설명 중단점 중단점 해상도를 가져옵니다.|  
|[사용](../../extensibility/debugger/reference/idebugboundbreakpoint2-enable.md)|중단점을 사용할 수 있거나.|  
|[Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)|바인딩된 중단점을 삭제합니다.|  
  
 확인 및 요청 정보가 필요한 다음 구현  [IDebugBreakpointResolution2](../../extensibility/debugger/reference/idebugbreakpointresolution2.md) 메서드가 있습니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetBreakpointType](../../extensibility/debugger/reference/idebugbreakpointresolution2-getbreakpointtype.md)|해결으로 표현 되는 중단점의 종류를 가져옵니다.|  
|[GetResolutionInfo](../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)|중단점은 중단점 해상도 정보를 가져옵니다.|  
  
 바인딩 중 발생할 수 있는 오류를 확인 해야 다음 구현  [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) 메서드가 있습니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md)|오류 중단점을 포함 하는 보류 중단점을 가져옵니다.|  
|[GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md)|설명 오류 중단점 중단점 오류 해상도를 가져옵니다.|  
  
 해상도를 바인딩하는 동안 발생할 수 있는 오류 또한 필요의 다음 메서드를  [IDebugErrorBreakpointResolution2](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md).  
  
|메서드|설명|  
|---------|--------|  
|[GetBreakpointType](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getbreakpointtype.md)|중단점 형식을 가져옵니다.|  
|[GetResolutionInfo](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)|확인 정보를 중단점을 가져옵니다.|  
  
 메서드를 구현 하 여 필요한 소스 코드에서 중단점을 보고  [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) 및\/또는 메서드를  [IDebugStackFrame2::GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md).  
  
## 참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)