---
title: "IDebugReference2::GetMemoryContext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugReference2::GetMemoryContext"
helpviewer_keywords: 
  - "IDebugReference2::GetMemoryContext"
ms.assetid: 47fc3827-07a0-4eee-b7f4-fc1c62e6b25c
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugReference2::GetMemoryContext
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

메모리 컨텍스트에 대 한 참조를 가져옵니다.  다음에 사용하도록 예약됩니다.  
  
## 구문  
  
```cpp#  
HRESULT GetMemoryContext (   
   IDebugMemoryContext2** ppMemory  
);  
```  
  
```c#  
int GetMemoryContext (   
   out IDebugMemoryContext2 ppMemory  
);  
```  
  
#### 매개 변수  
 `ppMemory`  
 \[out\] 반환은 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 참조 값과 연관 된 메모리를 나타내는 개체입니다.  
  
## 반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## 참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)