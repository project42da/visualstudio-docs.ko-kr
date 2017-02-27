---
title: "IDebugProcess3::Execute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProcess3::Execute"
helpviewer_keywords: 
  - "IDebugProcess3::Execute"
ms.assetid: d831cd81-d7bf-4172-8517-aa699867791f
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProcess3::Execute
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로세스가 중지 된 상태에서 실행이 계속 됩니다.  모든 이전 실행 상태 \(단계\) 해제 되 고 다시 실행 하는 프로세스를 시작 합니다.  
  
> [!NOTE]
>  대신이 메서드를 사용 해야 [실행](../../../extensibility/debugger/reference/idebugprogram2-execute.md).  
  
## 구문  
  
```cpp  
HRESULT Execute(  
   IDebugThread2* pThread  
);  
```  
  
```c#  
int Execute(  
   IDebugThread2 pThread  
);  
```  
  
#### 매개 변수  
 `pThread`  
 \[in\] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 를 실행 하는 스레드를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 설명  
 사용자가 일부 다른 프로세스의 스레드는 중지 된 상태에서 실행을 시작 하는 경우이 메서드는이 과정을 호출 됩니다.  사용자가 선택 하는 경우에이 메서드가 호출 되는  **시작** 명령에서  **디버그** ide에서 메뉴입니다.  이 메서드의 구현을 호출으로 같은 간단한 것일 수도 있는 [다시 시작](../../../extensibility/debugger/reference/idebugthread2-resume.md) 프로세스에서 현재 스레드의 메서드.  
  
> [!WARNING]
>  중지 이벤트 또는 즉시 \(동기\) 이벤트를 보내지 않습니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출; 처리 하는 중 그렇지 않으면 디버거가 중단 될 수 있음  
  
## 참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [다시 시작](../../../extensibility/debugger/reference/idebugthread2-resume.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)