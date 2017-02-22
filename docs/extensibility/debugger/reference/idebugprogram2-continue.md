---
title: "IDebugProgram2::Continue | Microsoft Docs"
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
  - "IDebugProgram2::Continue"
helpviewer_keywords: 
  - "IDebugProgram2::Continue"
ms.assetid: e5a6e02a-d21b-4a03-a034-e8de1f71ce2e
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgram2::Continue
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로그램이 중지 된 상태에서 실행이 계속 됩니다.  모든 이전 실행 상태 \(단계\) 유지 됩니다, 다시 실행 프로그램을 시작 하 고 있습니다.  
  
> [!NOTE]
>  이 메서드는 사용되지 않습니다.  대신 [계속](../../../extensibility/debugger/reference/idebugprocess3-continue.md) 메서드를 사용하십시오.  
  
## 구문  
  
```cpp#  
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
 \[in\] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 스레드를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 응용 프로그램 중지 이벤트를 생성 하는 프로그램을 디버깅 하 고 있는, 하 든 관계 없이이 프로그램에서이 메서드가 호출 됩니다.  구현 \(예: 단계\) 이전 실행 상태를 유지 하 고 절대로 이전 실행을 완료 하기 전에 중지 된 있었습니다 것 처럼 계속 실행 해야 합니다.  즉,이 프로그램에는 스레드 스텝 작업을 수행 하 고 다른 프로그램을 중지 하 고이 메서드를 호출한 다음 중지 된 경우 프로그램 원래의 스텝 작업을 완료 해야 합니다.  
  
> [!WARNING]
>  중지 이벤트 또는 즉시 \(동기\) 이벤트를 보내지 않습니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출; 처리 하는 중 그렇지 않으면 디버거가 중단 될 수 있음  
  
## 참고 항목  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)