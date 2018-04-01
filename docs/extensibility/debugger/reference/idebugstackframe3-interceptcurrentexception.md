---
title: IDebugStackFrame3::InterceptCurrentException | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugStackFrame3::InterceptCurrentException
helpviewer_keywords:
- IDebugStackFrame3::InterceptCurrentException
ms.assetid: 116c7324-7645-4c15-b484-7a5cdd065ef5
caps.latest.revision: 9
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9842527f90d9b2df7308f1e80e337de2848d9179
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugstackframe3interceptcurrentexception"></a>IDebugStackFrame3::InterceptCurrentException
현재 예외를 가로채기 위해가 현재 스택 프레임에 디버거를 통해 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT InterceptCurrentException(  
   INTERCEPT_EXCEPTION_ACTION dwFlags,  
   UINT64*                    pqwCookie  
);  
```  
  
```csharp  
int InterceptCurrentException(  
   uint dwFlags,   
   out  ulong pqwCookie  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 [in] 다른 동작을 지정합니다. 현재만 [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md) 값 `IEA_INTERCEPT` 은 지원 되며 지정 해야 합니다.  
  
 `pqwCookie`  
 [out] 특정 예외를 식별 하는 고유 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
 가장 일반적인 오류 반환은 다음과 같습니다.  
  
|Error|설명|  
|-----------|-----------------|  
|`E_EXCEPTION_CANNOT_BE_INTERCEPTED`|현재 예외를 가로챌 수 없습니다.|  
|`E_EXCEPTION_CANNOT_UNWIND_ABOVE_CALLBACK`|현재 실행 프레임 아직 처리기에 대 한 검색이 하지 않았습니다.|  
|`E_INTERCEPT_CURRENT_EXCEPTION_NOT_SUPPORTED`|이 메서드는이 프레임에 대해 지원 되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 예외가 throw 될 때 디버거 예외 처리를 처리 하는 동안 주요 지점에서 런타임에 컨트롤을 얻게 됩니다. 이러한 키 분 동안 디버거 요청할 수 현재 스택 프레임 프레임에서 예외를 가로챌 하려는 경우. 이러한 방식으로 가로챈된 예외 스택 프레임 예외 처리기 (예: 프로그램 코드에서 try/catch 블록)에 없는 경우에 기본적으로 스택 프레임에 대 한 즉시에 예외 처리기는 합니다.  
  
 디버거를 예외를 가로챌 수 하는 경우를 확인 하려는 경우 현재 스택 프레임 개체의이 메서드를 호출 합니다. 이 메서드는 모든 예외 정보 처리를 담당 합니다. 경우는 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md) 인터페이스 구현 되지 않음 또는 `InterceptStackException` 디버거를 계속 정상적으로 예외를 처리 한 다음 메서드는 모든 오류를 반환 합니다.  
  
> [!NOTE]
>  예외 가로챌 수 있습니다 관리 되는 코드에만, 즉 런타임에.NET 모드로 디버깅 중인 프로그램을 실행 하는 경우. 타사 언어 구현자 구현할 수는 물론, `InterceptStackException` 자신의 디버그 엔진 선택 하는 경우에 합니다.  
  
 가로채기가 완료 되 면는 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md) 신호입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)   
 [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md)   
 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)