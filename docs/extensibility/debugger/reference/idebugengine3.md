---
title: IDebugEngine3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine3
helpviewer_keywords: IDebugEngine3 interface
ms.assetid: 8bdf4bb7-3b5d-4991-8981-772d4f6bb656
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: df8ea8f5e95cf32f5b1425a4f110c424155b2ef2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugengine3"></a>IDebugEngine3
하나 이상의 모듈을 디버깅 하는 제어 하는 단일 디버그 엔진을 (DE)을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugEngine3 : IDebugEngine2  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스는 구현한 사용자 지정 DE (기호 지원) 하는 경우 JustMyCode 상태를 사용 하도록 합니다. 기호 및 JustMyCode를 지 원하는 경우이 인터페이스는 DE 하 여 구현 되어야 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스는 세션 디버그 관리자 (SDM) 기호를 로드 하려는 위치에 대 한 사용자 옵션에 전달 하 여 호출 됩니다. 엔진의 GUID를 인스턴스화할 때 설정 하 라고 (메트릭을 엔진 등록 중에이 GUID 기반). 또한은 SDM JustMyCode 상태를 설정 하 고 디버거를 지정된 된 상태에서 알려진 모든 예외를 설정 하려면이 인터페이스를 호출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 상속 된 메서드 외에도 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md), `IDebugEngine3` 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)|DE 하는 데 사용할 검색 디버깅 기호에 대 한 경로 또는 경로 설정 합니다.|  
|[LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)|기호를 로드 아직가 되지 않은 모든 모듈에 대 한 기호를 로드 합니다.|  
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)|DE JustMyCode 정보에 대 한 지시합니다.|  
|[SetEngineGuid](../../../extensibility/debugger/reference/idebugengine3-setengineguid.md)|메트릭을에서 DE GUID를 설정합니다.|  
|[SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md)|지정 된 상태로 현재 처리 중인 모든 예외를 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)