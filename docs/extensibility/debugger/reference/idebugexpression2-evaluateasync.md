---
title: "IDebugExpression2::EvaluateAsync | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpression2::EvaluateAsync"
helpviewer_keywords: 
  - "IDebugExpression2::EvaluateAsync"
ms.assetid: 848fe6cb-0759-42f2-890b-d2b551c527d6
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# IDebugExpression2::EvaluateAsync
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 비동기적으로 계산 수 있습니다.  
  
## 구문  
  
```cpp#  
HRESULT EvaluateAsync (   
   EVALFLAGS             dwFlags,  
   IDebugEventCallback2* pExprCallback  
);  
```  
  
```c#  
int EvaluateAsync(  
   enum_EVALFLAGS       dwFlags,   
   IDebugEventCallback2 pExprCallback  
);  
```  
  
#### 매개 변수  
 `dwFlags`  
 \[in\] 플래그의 조합에서 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 식 계산을 제어 하는 열거형입니다.  
  
 `pExprCallback`  
 \[in\] 이 매개 변수는 항상 null 값입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  일반적인 오류 코드가입니다.  
  
|오류|설명|  
|--------|--------|  
|E\_EVALUATE\_BUSY\_WITH\_EVALUATION|현재 다른 식 계산을 하 고 동시 식 계산이 지원 되지 않습니다.|  
  
## 설명  
 이 메서드는 식 계산 즉시 시작 된 후에 반환 해야 합니다.  식이 성공적으로 계산 되는 경우는 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) 전송 되어야 합니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 를 통해 제공 되는 이벤트 콜백 [연결](../../../extensibility/debugger/reference/idebugprogram2-attach.md) 또는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
## 예제  
 다음 예제에서는 단순에이 메서드를 구현 하는 방법을 보여 줍니다. `CExpression` 를 구현 하는 개체는 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) 인터페이스입니다.  
  
```cpp#  
HRESULT CExpression::EvaluateAsync(EVALFLAGS dwFlags,  
                                   IDebugEventCallback2* pExprCallback)  
{  
    // Set the aborted state to FALSE  
    // in case the user tries to redo the evaluation after aborting.  
    m_bAborted = FALSE;  
    // Post the WM_EVAL_EXPR message in the message queue of the current thread.  
    // This starts the expression evaluation on a background thread.  
    PostThreadMessage(GetCurrentThreadId(), WM_EVAL_EXPR, 0, (LPARAM) this);  
    return S_OK;  
}  
```  
  
## 참고 항목  
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)   
 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)   
 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)