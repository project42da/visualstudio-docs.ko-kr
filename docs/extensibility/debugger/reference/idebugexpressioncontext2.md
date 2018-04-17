---
title: IDebugExpressionContext2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugExpressionContext2
helpviewer_keywords:
- IDebugExpressionContext2 interface
ms.assetid: 577fdaae-4b2d-4112-9839-ab899535fa6f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4da916f67611f594b14a41cbb2838f4565eb7fe3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugexpressioncontext2"></a>IDebugExpressionContext2
이 인터페이스는 식 계산에 대 한 컨텍스트를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugExpressionContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 식이 계산 될 수 있는 컨텍스트를 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 호출 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) this 반환 인터페이스입니다. 이 인터페이스는 디버깅 중인 프로그램 일시 중지 된 스택 프레임은 사용할 수 있는 경우에 액세스할 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugExpressionContext2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugexpressioncontext2-getname.md)|평가 컨텍스트에 이름을 검색합니다.|  
|[ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)|평가 대 한 텍스트 기반 식을 구문 분석합니다.|  
  
## <a name="remarks"></a>설명  
 평가 컨텍스트에 식 평가 수행 하기 위한 범위로 생각할 수 있습니다.  
  
 프로그램이 중지 세션 디버그 관리자 (SDM) 스택 프레임에서에서 얻습니다을 호출 하 여 DE [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)합니다. 다음은 SDM를 호출 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) 가져오려는 `IDebugExpressionContext2` 인터페이스입니다. 호출 하 여 다음 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 만들려는 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) 구문 분석된 된 식 평가 준비가 나타내는 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)   
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)