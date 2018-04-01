---
title: IDebugStackFrame3 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugStackFrame3
helpviewer_keywords:
- IDebugStackFrame3 interface
ms.assetid: 39af2f57-0a01-42b8-b093-b7fbc61e2909
caps.latest.revision: 15
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a45859fe78df3907df680b7716f743ff411ca3f3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugstackframe3"></a>IDebugStackFrame3
이 인터페이스를 확장 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 가로챈된 예외를 처리 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugStackFrame3 : IDebugStackFrame2  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE)를 구현 하는 동일한 개체에서이 인터페이스를 구현 하는 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 인터페이스를 가로챈된 예외를 지원 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [QueryInterface](/cpp/atl/queryinterface) 에 `IDebugStackFrame2` 인터페이스가이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 상속 된 메서드 외에도 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md), `IDebugStackFrame3` 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)|일반 예외 처리 하기 전에 현재 스택 프레임에 대 한 예외를 처리합니다.|  
|[GetUnwindCodeContext](../../../extensibility/debugger/reference/idebugstackframe3-getunwindcodecontext.md)|스택 해제 된 발생 하는 경우 코드 컨텍스트를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 가로챈된 예외가 실행된 시간이 하 여 모든 일반 예외 처리 루틴을 호출 하기 전에 디버거가 예외를 처리할 수를 의미 합니다. 기본적으로 예외가 가로채 런타임에 존재 하지 않은 경우에 예외 처리기 있다는 것으로 가정 하 의미 합니다.  
  
 [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md) 모든 일반적인 예외 콜백 이벤트 동안 호출 되어 (이 유일한 예외는 경우 코드 디버깅 하는 혼합 모드 (관리 및 비관리 코드) 하는 동안 예외를 가로챌 수 없습니다는 쿼리에서 마지막 기회 콜백)입니다. DE 구현 하지 않는 경우 `IDebugStackFrame3`는 DE IDebugStackFrame3에서 오류를 반환 하거나::`InterceptCurrentException` (같은 `E_NOTIMPL`), 다음 디버거가 예외를 정상적으로 처리 됩니다.  
  
 디버거 예외를 가로채 사용자 디버깅 중인 프로그램의 상태를 변경 하 고, 예외가 throw 된 지점에서 실행을 다시 허용할 수 있습니다.  
  
> [!NOTE]
>  가로챈된 예외는 공용 언어 런타임 (CLR)에서 실행 중인 프로그램에서 즉, 관리 코드에만 허용 됩니다.  
  
 디버그 엔진 "metricExceptions"를 설정 하 여 가로채 예외를 지원 하는지 값 1 실행 시 사용 하 여 나타냅니다는 `SetMetric` 함수입니다. 자세한 내용은 참조 [디버깅할 수 있도록 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)