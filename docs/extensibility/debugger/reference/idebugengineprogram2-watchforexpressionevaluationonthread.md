---
title: "IDebugEngineProgram2::WatchForExpressionEvaluationOnThread | Microsoft Docs"
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
  - "IDebugEngineProgram2::WatchForExpressionEvaluationOnThread"
helpviewer_keywords: 
  - "IDebugEngineProgram2::WatchForExpressionEvaluationOnThread"
ms.assetid: 01d05e77-8cac-4d1b-b19f-25756767ed27
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

허용 하거나 허용 하지 않습니다 식 계산 프로그램을 중지 한 경우에 해당된 스레드에서 발생 합니다.  
  
## 구문  
  
```cpp#  
HRESULT WatchForExpressionEvaluationOnThread(   
   IDebugProgram2*       pOriginatingProgram,  
   DWORD                 dwTid,  
   DWORD                 dwEvalFlags,  
   IDebugEventCallback2* pExprCallback,  
   BOOL                  fWatch  
);  
```  
  
```c#  
int WatchForExpressionEvaluationOnThread(   
   IDebugProgram2       pOriginatingProgram,  
   uint                  dwTid,  
   uint                  dwEvalFlags,  
   IDebugEventCallback2 pExprCallback,  
   int                   fWatch  
);  
```  
  
#### 매개 변수  
 `pOriginatingProgram`  
 \[in\] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 식을 평가할 수 있는 프로그램을 나타내는 개체입니다.  
  
 `dwTid`  
 \[in\] 스레드 식별자를 지정 합니다.  
  
 `dwEvalFlags`  
 \[in\] 플래그의 조합에서 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 평가 수행 하는 방법을 지정 하는 열거형입니다.  
  
 `pExprCallback`  
 \[in\] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 는 식을 계산 하는 동안 발생 하는 디버그 이벤트를 보내는 데 사용할 수 있는 개체입니다.  
  
 `fWatch`  
 \[in\] 0이 아닌 경우 \(`TRUE`\), 식 계산에서 식별 되는 스레드 수 `dwTid`. 그렇지 않으면 0 \(`FALSE`\) 식 계산에 해당 스레드를 허용 하지 않습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 세션 디버그 매니저 \(SDM\)로 식별 되는 프로그램을 묻는 경우에 `pOriginatingProgram` 에서 식을 계산 하려면 매개 변수를이 메서드를 호출 하 여 연결 된 다른 모든 프로그램에 알립니다.  
  
 식 계산을 한 프로그램에서 코드가 다른 함수를 실행 하거나 평가 하는 때문에 실행 하면 발생할 수 있습니다 `IDispatch` 속성입니다.  이 때문에이 메서드 식을 평가 실행 하 고이 프로그램에서 스레드가 중지 될 수 있습니다 경우에 완료 수 있습니다.  
  
## 참고 항목  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)