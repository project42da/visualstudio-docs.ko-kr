---
title: "IDebugStackFrame3::InterceptCurrentException | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugStackFrame3::InterceptCurrentException"
helpviewer_keywords: 
  - "IDebugStackFrame3::InterceptCurrentException"
ms.assetid: 116c7324-7645-4c15-b484-7a5cdd065ef5
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugStackFrame3::InterceptCurrentException
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

현재 예외를 차단 하려고 할 때 현재 스택 프레임에 대 한 디버거를 호출 합니다.  
  
## 구문  
  
```cpp  
HRESULT InterceptCurrentException(  
   INTERCEPT_EXCEPTION_ACTION dwFlags,  
   UINT64*                    pqwCookie  
);  
```  
  
```c#  
int InterceptCurrentException(  
   uint dwFlags,   
   out  ulong pqwCookie  
);  
```  
  
#### 매개 변수  
 `dwFlags`  
 \[in\] 다른 동작을 지정합니다.  현재,만 [INTERCEPT\_EXCEPTION\_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md) 값 `IEA_INTERCEPT` 지원 되지 않으므로 지정 해야 합니다.  
  
 `pqwCookie`  
 \[out\] 특정 예외를 식별 하는 고유 값입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
 다음은 가장 일반적인 오류가 반환 됩니다.  
  
|오류|설명|  
|--------|--------|  
|`E_EXCEPTION_CANNOT_BE_INTERCEPTED`|현재 예외를 가로챌 수 없습니다.|  
|`E_EXCEPTION_CANNOT_UNWIND_ABOVE_CALLBACK`|현재 실행 프레임에 대 한 처리기를 아직 검색 되지 않은.|  
|`E_INTERCEPT_CURRENT_EXCEPTION_NOT_SUPPORTED`|이 메서드는이 프레임에 대해 지원 되지 않습니다.|  
  
## 설명  
 예외가 throw 되 면 디버거가 프로세스를 처리 하는 동안 예외가 컨트롤에서 런타임에 키 포인트를 얻게 됩니다.  이러한 주요 순간 디버거는 현재 스택 프레임 프레임 예외를 차단 하려는 경우 요청할 수 있습니다.  해당 스택 프레임 예외 처리기 \(예: 프로그램 코드에서는 try\/catch 블록\)이 없는 경우에 이러한 방법으로 차단된 예외 기본적으로 스택 프레임에 대 한 즉석에서 예외 처리기입니다.  
  
 디버거에서 예외를 가로챌 경우를 알고 싶을 때 현재 스택 프레임 개체에이 메서드를 호출 합니다.  이 메서드를 예외에 대 한 모든 세부 사항을 처리 하기 위해 담당 합니다.  경우는 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md) 인터페이스가 구현 되지 않았습니다 또는 `InterceptStackException` 메서드는 오류를 반환 하 고 예외를 정상적으로 처리 디버거가 계속 합니다.  
  
> [!NOTE]
>  예외 수 있습니다 수 차단 관리 되는 코드에만 즉, 디버깅 중인 프로그램에서 실행 되는 경우에.NET 실행할 시간입니다.  물론, 다른 언어 구현 자가 구현할 수 있습니다 `InterceptStackException` 가 선택 하는 경우에 자신의 디버깅 엔진에 있습니다.  
  
 가로채기를 완료 한 후에 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md) 신호를 합니다.  
  
## 참고 항목  
 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)   
 [INTERCEPT\_EXCEPTION\_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md)   
 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)