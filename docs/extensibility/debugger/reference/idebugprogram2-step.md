---
title: "IDebugProgram2::Step | Microsoft Docs"
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
  - "IDebugProgram2::Step"
helpviewer_keywords: 
  - "IDebugProgram2::Step"
ms.assetid: e4c2ffce-9810-4088-8162-eac9ef04f2a9
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgram2::Step
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

한 단계를 수행합니다.  
  
> [!NOTE]
>  이 메서드는 사용되지 않습니다.  대신 [단계](../../../extensibility/debugger/reference/idebugprocess3-step.md) 메서드를 사용하십시오.  
  
## 구문  
  
```cpp#  
HRESULT Step(   
   IDebugThread2*  pThread,  
   STEPKIND        sk,  
   STEPUNIT        step  
);  
```  
  
```c#  
int Step(   
   IDebugThread2  pThread,  
   enum_STEPKIND  sk,  
   enum_STEPUNIT  step  
);  
```  
  
#### 매개 변수  
 `pThread`  
 \[in\] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 실행 하는 스레드를 나타내는 개체입니다.  
  
 `sk`  
 \[in\] 값은 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) 단계의 종류를 지정 하는 열거형입니다.  
  
 `step`  
 \[in\] 값은 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) 단계 단위 \(예를 들어, 명령문 또는 명령\)를 지정 하는 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 있는 경우 모든 스레드가 동기화 또는 스레드 간의 통신을 특정 스레드를 한 단계씩 실행 하는 경우 프로그램에 다른 스레드를 실행 해야 합니다.  
  
> [!WARNING]
>  중지 이벤트 또는 즉시 \(동기\) 이벤트를 보내지 않습니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출; 처리 하는 중 그렇지 않으면 디버거가 중단 될 수 있음  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)