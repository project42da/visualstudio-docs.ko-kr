---
title: "IDebugProcess3::Continue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProcess3::Continue"
helpviewer_keywords: 
  - "IDebugProcess3::Continue"
ms.assetid: 57506242-5763-4c08-adb9-8a78ce02cebb
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugProcess3::Continue
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로세스가 중지 된 상태에서 실행이 계속 됩니다.  모든 이전 실행 상태 \(단계\) 그대로 유지 됩니다, 프로세스가 시작 될 다시 실행 하 고 있습니다.  
  
> [!NOTE]
>  대신이 메서드를 사용 해야 [계속](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
## 구문  
  
```cpp  
HRESULT Continue(  
   IDebugThread2* pThread  
);  
```  
  
```c#  
int Continue(  
   IDebugThread2 pThread  
);  
```  
  
#### 매개 변수  
 `pThread`  
 \[in\] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 계속 스레드를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 설명  
 이 프로세스는 프로세스를 디버깅 하 고 있는, 또는 어떤 프로세스 중지 이벤트 생성에 관계 없이이 메서드가 호출 됩니다.  구현 \(예: 단계\) 이전 실행 상태를 유지 하 고 절대로 이전 실행을 완료 하기 전에 중지 된 있었습니다 것 처럼 계속 실행 해야 합니다.  즉, 스레드를 하는 경우이 프로세스 스텝 작업을 수행 하 고 다른 프로세스를 중지 하기 때문에 중지 되었습니다 다음 `Continue` 되었습니다 라고 하는 지정 된 스레드가 원래 스텝 작업을 완료 해야 합니다.  
  
 **경고**  중지 이벤트 또는 즉시 \(동기\) 이벤트를 보내지 않습니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출; 처리 하는 중 그렇지 않으면 디버거가 중단 될 수 있음  
  
## 참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)