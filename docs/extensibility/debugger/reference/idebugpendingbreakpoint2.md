---
title: IDebugPendingBreakpoint2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPendingBreakpoint2
helpviewer_keywords:
- IDebugPendingBreakpoint2 interface
ms.assetid: d416b095-917e-475e-b796-ec0a03ffb8da
caps.latest.revision: 13
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ef986bd657a080c08fd0ebb85908ba59757bf207
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpendingbreakpoint2"></a>IDebugPendingBreakpoint2
이 인터페이스 코드 위치에 바인딩할 준비가 되어 있는 중단점을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPendingBreakpoint2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 중단점에 대 한 지원의 일부로이 인터페이스를 구현합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 호출 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) 에서 보류 중인 중단점을 만듭니다는 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) 인터페이스입니다. 에 대 한 호출 [바인딩할](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) 만듭니다는 `IDebugBreakpoint2` 프로그램에서 바인딩된 중단점을 나타내는 인터페이스입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugPendingBreakpoint2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)|이 보류 중인 중단점 코드 위치에 바인딩할 수 있는지 여부를 결정 합니다.|  
|[바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)|이 보류 중인 중단점 하나 이상의 코드 위치로 바인딩합니다.|  
|[우편 번호](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)|이 중단점이 보류 중 상태를 가져옵니다.|  
|[GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)|이 보류 중인 중단점을 만드는 데 사용 된 중단점 요청을 가져옵니다.|  
|[가상화](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md)|이 중단점이 보류 중인 가상화 된 상태를 토글합니다.|  
|[사용 하도록 설정](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)|중단점 보류 중인이 활성화 된 상태를 토글합니다.|  
|[SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)|설정 하거나 중단점 보류 중인 연결 된이 조건을 변경 합니다.|  
|[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)|설정 하거나 중단점 보류 중인 연결 된이 패스 개수를 변경 합니다.|  
|[EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)|이 보류 중인 중단점에서 바인딩된 모든 중단점을 열거 합니다.|  
|[EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)|이 보류 중인 중단점에서 발생 하는 모든 오류 중단점을 열거 합니다.|  
|[삭제](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)|이 보류 중인 중단점 및 여기에서 바인딩된 모든 중단점을 삭제 합니다.|  
  
## <a name="remarks"></a>설명  
 `IDebugPendingBreakpoint2`하나 또는 여러 프로그램에 적용할 수 있는 코드에 중단점을 바인딩할 때 필요한 모든 필요한 정보를 공급자로 생각할 수 있습니다.  
  
 보류 중인 중단점 바인딩된 중단점이 여러 개 생성 합니다. 예를 들어 c + + 스타일 템플릿의 중단점 해당 서식 파일의 각 고유 인스턴스에 대 한 바인딩된 중단점이 발생할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md)