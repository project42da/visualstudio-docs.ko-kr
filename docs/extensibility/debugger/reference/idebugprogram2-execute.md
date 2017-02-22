---
title: "IDebugProgram2::Execute | Microsoft Docs"
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
  - "IDebugProgram2::Execute"
helpviewer_keywords: 
  - "IDebugProgram2::Execute"
ms.assetid: f7205ce8-0ac6-4fcd-b6ec-b720b4fcaccf
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgram2::Execute
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로그램이 중지 된 상태에서 실행이 계속 됩니다.  모든 이전 실행 상태 \(단계\)와 같은 선택을 취소, 다시 실행 프로그램을 시작 하 고.  
  
> [!NOTE]
>  이 메서드는 사용되지 않습니다.  대신 [실행](../../../extensibility/debugger/reference/idebugprocess3-execute.md) 메서드를 사용하십시오.  
  
## 구문  
  
```cpp#  
HRESULT Execute(  
   void  
);  
```  
  
```c#  
int Execute();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 사용자 실행이 중지 된 상태에서 다른 프로그램의 스레드를 시작 하는 경우이 메서드는이 프로그램에 호출 됩니다.  사용자가 선택 하는 경우에이 메서드가 호출 되는  **시작** 명령에서  **디버그** ide에서 메뉴입니다.  이 메서드의 구현을 호출으로 같은 간단한 것일 수도 있는 [다시 시작](../../../extensibility/debugger/reference/idebugthread2-resume.md) 프로그램에서 현재 스레드의 메서드.  
  
> [!WARNING]
>  중지 이벤트 또는 즉시 \(동기\) 이벤트를 보내지 않습니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출; 처리 하는 중 그렇지 않으면 디버거가 중단 될 수 있음  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [다시 시작](../../../extensibility/debugger/reference/idebugthread2-resume.md)