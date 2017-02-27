---
title: "IDebugMemoryContext2::Subtract | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugMemoryContext2::Subtract"
helpviewer_keywords: 
  - "Subtract 메서드"
  - "IDebugMemoryContext2::Subtract 메서드"
ms.assetid: 63df14c7-8d7e-47c1-afa7-5a1ab5d8eaba
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugMemoryContext2::Subtract
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

현재 컨텍스트에서 지정 된 값을 빼고 새 컨텍스트를 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Subtract(   
   UINT64                 dwCount,  
   IDebugMemoryContext2** ppMemCxt  
);  
```  
  
```c#  
int Subtract(  
   ulong                    dwCount,   
   out IDebugMemoryContext2 ppMemCxt  
);  
```  
  
#### 매개 변수  
 `dwCount`  
 \[in\] 메모리 바이트 수를 감소 시킬 수 있습니다.  
  
 `ppMemCxt`  
 \[out\] 새 반환 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 주소에서 값을 빼서 새 컨텍스트 인터페이스에 필요한 새 주소를 생성 하도록 메모리 컨텍스트 주소입니다.  
  
 이 컨텍스트와 관련 된 메모리 공간 밖으로 만들어진 주소입니다 경우에이 메서드는 항상 새 컨텍스트를 생성 해야 합니다.  새 컨텍스트에 대 한 메모리를 할당 하지 수 있습니다 또는 경우에 예외입니다 `ppMemCxt` 오류는 null 값입니다.  
  
## 참고 항목  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)