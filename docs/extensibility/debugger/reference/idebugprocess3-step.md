---
title: "IDebugProcess3::Step | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProcess3::Step"
helpviewer_keywords: 
  - "IDebugProcess3::Step"
ms.assetid: 6ad9094c-27cc-4927-8a7c-1b4d97b2e436
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProcess3::Step
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

하나의 명령 또는 명령문을 실행 하는 프로세스를 발생 합니다.  
  
> [!NOTE]
>  대신이 메서드를 사용 해야 [단계](../../../extensibility/debugger/reference/idebugprogram2-step.md).  
  
## 구문  
  
```cpp  
HRESULT Step(  
   IDebugThread2* pThread,  
   STEPKIND       sk,  
   STEPUNIT       step,  
);  
```  
  
```c#  
int Step(  
   IDebugThread2 pThread,   
   enum_STEPKIND sk,   
   enum_STEPUNIT step  
);  
```  
  
#### 매개 변수  
 `pThread`  
 \[in\] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 실행 하는 스레드를 나타내는 개체입니다.  
  
 `sk`  
 \[in\] 중 하나를 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) 값입니다.  
  
 `step`  
 \[in\] 중 하나를 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) 값입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 설명  
 있는 경우 모든 스레드가 동기화 또는 스레드 간의 통신, 특정 스레드를 한 단계씩 실행 하는 경우 프로세스에서 다른 스레드를 실행 해야 합니다.  
  
 **경고**  중지 이벤트 또는 즉시 \(동기\) 이벤트를 보내지 않습니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출; 처리 하는 중 그렇지 않으면 디버거가 중단 될 수 있음  
  
## 참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md)   
 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)