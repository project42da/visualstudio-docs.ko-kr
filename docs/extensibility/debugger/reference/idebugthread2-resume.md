---
title: "IDebugThread2::Resume | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugThread2::Resume"
helpviewer_keywords: 
  - "IDebugThread2::Resume"
ms.assetid: 36aad682-b0b9-40a2-b3fc-f0e61d41cdbc
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugThread2::Resume
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

스레드의 실행을 다시 시작합니다.  
  
## 구문  
  
```cpp#  
HRESULT Resume (   
   DWORD *pdwSuspendCount  
);  
```  
  
```c#  
int Resume (   
   out uint pdwSuspendCount  
);  
```  
  
#### 매개 변수  
 `pdwSuspendCount`  
 \[out\] 이력서 작업 후 일시 중단 계수를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 일시 중단 횟수가이 메서드가 감소를 호출 되며 이때 0에 도달할 때까지 실제로 실행 다시 시작 됩니다.  이 일시 중단 횟수가 표시 되는  **스레드에서** 디버그 창.  
  
 각 호출에 대해이 메서드를 반드시 있어야 하는 이전 호출에서 [일시 중단](../../../extensibility/debugger/reference/idebugthread2-suspend.md) 메서드.  일시 중단 횟수가 몇 번 결정의 `IDebugThread2::Suspend` 메서드가 현재까지 호출 합니다.  
  
## 참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [일시 중단](../../../extensibility/debugger/reference/idebugthread2-suspend.md)