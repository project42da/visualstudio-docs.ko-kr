---
title: "IDebugThread2::GetLogicalThread | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugThread2::GetLogicalThread"
helpviewer_keywords: 
  - "IDebugThread2::GetLogicalThread"
ms.assetid: bce6230e-41d4-49b7-a050-2dde5efb6805
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugThread2::GetLogicalThread
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진이이 메서드를 구현 하십시오.  
  
## 구문  
  
```cpp#  
HRESULT GetLogicalThread(   
   IDebugStackFrame2*     pStackFrame,  
   IDebugLogicalThread2** ppLogicalThread  
);  
```  
  
```c#  
int GetLogicalThread(   
   IDebugStackFrame2        pStackFrame,  
   out IDebugLogicalThread2 ppLogicalThread  
);  
```  
  
#### 매개 변수  
 `pStackFrame`  
 \[in\] [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 는 스택 프레임을 나타내는 개체입니다.  
  
 `ppLogicalThread`  
 \[out\] 반환 된 `IDebugLogicalThread2` 관련된 논리 스레드가 나타내는 인터페이스입니다.  디버그 엔진 구현은이 null 값으로 설정 해야 합니다.  
  
## 반환 값  
 디버그 엔진 구현은 항상 반환 `E_NOTIMPL`.  
  
## 참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)