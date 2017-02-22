---
title: "IDebugThread2::Suspend | Microsoft Docs"
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
  - "IDebugThread2::Suspend"
helpviewer_keywords: 
  - "IDebugThread2::Suspend"
ms.assetid: 1e20be85-aa12-48de-bb83-0bf0976e99ae
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugThread2::Suspend
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

스레드를 일시 중단합니다.  
  
## 구문  
  
```cpp#  
HRESULT Suspend (   
   DWORD *pdwSuspendCount  
);  
```  
  
```c#  
HRESULT Suspend (   
   out uint pdwSuspendCount  
);  
```  
  
#### 매개 변수  
 `pdwSuspendCount`  
 \[out\] 일시 중단 작업 후 일시 중단 계수를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드를 호출할 때마다 일시 중단 계수가 0 위에 증가합니다.  이 일시 중단 횟수가 표시 되는  **스레드에서** 디버그 창.  
  
 각 호출에 대해이 메서드를 수 있어야 나중에 호출 하는 [다시 시작](../../../extensibility/debugger/reference/idebugthread2-resume.md) 메서드가 있습니다.  
  
## 참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [다시 시작](../../../extensibility/debugger/reference/idebugthread2-resume.md)