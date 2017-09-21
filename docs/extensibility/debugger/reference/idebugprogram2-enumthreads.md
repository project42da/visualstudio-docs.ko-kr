---
title: "IDebugProgram2::EnumThreads | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgram2::EnumThreads"
helpviewer_keywords: 
  - "IDebugProgram2::EnumThreads"
ms.assetid: 0f2a8c51-1315-4c96-8aa1-6a937dc2a769
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProgram2::EnumThreads
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램을 실행 하는 스레드의 목록을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumThreads(   
   IEnumDebugThreads2** ppEnum  
);  
```  
  
```c#  
int EnumThreads(   
   out IEnumDebugThreads2 ppEnum  
);  
```  
  
#### 매개 변수  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md) 스레드 목록을 포함 하는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)