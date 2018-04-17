---
title: EVALFLAGS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EVALFLAGS
helpviewer_keywords:
- EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7c718414749bb6c748f25fb90837644fe984a274
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="evalflags"></a>EVALFLAGS
식 계산을 제어 하는 플래그를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
};  
typedef DWORD EVALFLAGS;  
```  
  
```csharp  
public enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
}  
```  
  
## <a name="members"></a>멤버  
 EVAL_RETURNVALUE  
 있는 경우 반환 값을 평가할 지정 합니다.  
  
 EVAL_NOSIDEEFFECTS  
 파생 작업이 허용 되지 않음을 지정 합니다.  
  
 EVAL_ALLOWBPS  
 중단점에서 중지를 지정합니다.  
  
 EVAL_ALLOWERRORREPORT  
 오류를 사용 하려면 호스트에 보고를 지정 합니다. Internet Explorer에서 스크립트에서 식 평가에 주로 사용 됩니다.  
  
 EVAL_FUNCTION_AS_ADDRESS  
 함수를 호출 하는 대신 주소로 평가 될 강제로 함수입니다.  
  
 EVAL_NOFUNCEVAL  
 확인할 함수를 방지 합니다. 예를 들어는 `int` 식에 토큰 `myExpression(int) + 10`합니다. 이 함수는 주소로 시 키 지 않고 값을 올바르게 평가할 수 있습니다.  
  
 EVAL_NOEVENTS  
 식 평가 중 발생 하는 이벤트 보내지 않아야 세션 디버그 관리자 (SDM) 또는 IDE에 표시 하는 플래그입니다.  
  
## <a name="remarks"></a>설명  
 이러한 플래그에 대 한 인수로 전달 되는 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 및 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 메서드.  
  
 이러한 플래그 비트 OR 연산자와 함께 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)