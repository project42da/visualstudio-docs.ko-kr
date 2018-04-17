---
title: IDebugProcessEx2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcessEx2
helpviewer_keywords:
- IDebugProcessEx2 interface
ms.assetid: 44e309ba-1d6f-499b-aa7e-9b34858a6d57
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 479206b75325c1b7e6bba0e4cc4e9b53944d73d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocessex2"></a>IDebugProcessEx2
이 인터페이스에는 세션을 디버그 관리자 (SDM)에 연결 되었거나 프로세스에서 분리 하는 프로세스를 알릴 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProcessEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 사용자 지정 포트 공급자와 같은 개체에이 인터페이스를 구현 하는 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 하기 위해 인터페이스:  
  
-   프로세스에 연결 된 세션의 추적 지원  
  
-   지원 자동 연결이 여러 디버그 엔진에서  
  
 사용자 지정 포트 공급자 중에서 선택한 경우이 인터페이스를 구현할 수 있습니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
  
-   SDM 호출 [QueryInterface](/cpp/atl/queryinterface) 에 `IDebugProcess2` 인터페이스가이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugProcessEx2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[Attach](../../../extensibility/debugger/reference/idebugprocessex2-attach.md)|세션에서 프로세스를 디버깅 이제는 프로세스에 알립니다.|  
|[Detach](../../../extensibility/debugger/reference/idebugprocessex2-detach.md)|세션에서 프로세스를 디버깅 더 이상이 프로세스에 알립니다.|  
|[AddImplicitProgramNodes](../../../extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes.md)|디버그 엔진의 목록에 대 한 프로그램 노드를 추가합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 SDM와 프로세스 간의 비공개입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)