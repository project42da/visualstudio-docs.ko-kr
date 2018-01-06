---
title: IDebugModule2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugModule2
helpviewer_keywords: IDebugModule2 interface
ms.assetid: 24c2a126-f4ab-4891-8509-8ef99b994c08
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4ffa4044e6490f8de8228541787b7bf8ab80285a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmodule2"></a>IDebugModule2
이 인터페이스는 모듈을 나타내는-, 즉 프로그램의 실행 파일 단위 — DLL 등입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugModule2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 모듈을 나타내는 하 고 해당 모듈에 대 한 정보에 대 한 액세스를 제공 합니다.이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 호출 [GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md) 이 인터페이스를 반환 합니다. DE 보냅니다는 [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md) 인터페이스를 사용 하 여 세션 디버그 관리자 (SDM)는 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 메서드.  
  
 이 인터페이스에서 반환 될 수 있습니다는 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조 (에 대 한 호출에서 반환 된 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)).  
  
 [다음](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md) 도이 인터페이스를 반환 ([EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) 반환 된 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md) 인터페이스).  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugModule2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)|가져옵니다는 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) 이 모듈을 설명 하는 합니다.|  
|[ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md)|사용되지 않습니다. 사용 하지 마십시오. 이 모듈에 대 한 기호를 다시 로드합니다.|  
  
## <a name="remarks"></a>설명  
 모듈 정보에 표시할 수는 **모듈** IDE의 창.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)   
 [GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)   
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)