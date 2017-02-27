---
title: "IDebugPendingBreakpoint2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPendingBreakpoint2"
helpviewer_keywords: 
  - "IDebugPendingBreakpoint2 인터페이스"
ms.assetid: d416b095-917e-475e-b796-ec0a03ffb8da
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IDebugPendingBreakpoint2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 코드 위치를 바인딩할 준비가 되어 중단점을 나타냅니다.  
  
## 구문  
  
```  
IDebugPendingBreakpoint2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 중단점에 대 한 지원의 일부로 서이 인터페이스를 구현합니다.  
  
## 호출자에 대 한 참고 사항  
 호출을 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) 에서 보류 중인 중단점을 만듭니다는 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) 인터페이스입니다.  호출을 [바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) 만듭니다는 `IDebugBreakpoint2` 프로그램에서 바인딩된 중단점을 나타내는 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugPendingBreakpoint2`.  
  
|메서드|설명|  
|---------|--------|  
|[CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)|이 보류 중단점이 코드 위치에 바인딩할 수 있는지 여부를 결정 합니다.|  
|[바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)|이 보류 중단점에 하나 이상의 코드 위치에 바인딩합니다.|  
|[GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)|보류 중단점의 상태를 가져옵니다.|  
|[GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)|이 보류 중단점을 만드는 데 사용 된 중단점 요청을 가져옵니다.|  
|[가상화](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md)|이 가상화 된 상태 보류 중단점 설정\/해제.|  
|[사용](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)|이 활성화 된 상태 보류 중단점 설정\/해제 합니다.|  
|[SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)|설정 하거나이를 보류 중단점 연결 된 조건을 변경 합니다.|  
|[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)|설정 하거나 이와 보류 중단점 관련의 단계 수를 변경 합니다.|  
|[EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)|이 보류 중단점에서 바인딩된 중단점을 모두 열거 합니다.|  
|[EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)|이 보류 중단점에서 발생 시킨 오류 중단점을 모두 열거 합니다.|  
|[삭제](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)|이 보류 중단점 및 바인딩된에서 모든 중단점을 삭제 합니다.|  
  
## 설명  
 `IDebugPendingBreakpoint2`중 하나 또는 여러 프로그램에 적용할 수 있는 코드에 중단점을 바인딩할 때 필요한 모든 필요한 정보를 공급자로 생각할 수 있습니다.  
  
 잠재적으로 보류 중단점이 바인딩된 중단점을 하나 이상 생성 합니다.  예를 들어, c \+ \+ 스타일 서식 파일에서 중단점을 해당 서식 파일의 각 고유 인스턴스에 대해 바인딩된 중단점을 발생할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md)