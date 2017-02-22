---
title: "IDebugMemoryContext2::Add | Microsoft Docs"
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
  - "IDebugMemoryContext2::Add"
helpviewer_keywords: 
  - "IDebugMemoryContext2::Add 메서드"
  - "Add 메서드"
ms.assetid: 3c47e646-ce9e-4dd3-8f1a-6dbd3827d407
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugMemoryContext2::Add
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

지정 된 값을 현재 컨텍스트에 추가 하 고 새 컨텍스트를 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Add(   
   UINT64                 dwCount,  
   IDebugMemoryContext2** ppMemCxt  
);  
```  
  
```c#  
int Add(  
   ulong                    dwCount,   
   out IDebugMemoryContext2 ppMemCxt  
);  
```  
  
#### 매개 변수  
 `dwCount`  
 \[in\] 현재 컨텍스트에 추가할 값입니다.  
  
 `ppMemCxt`  
 \[out\] 새 반환 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 새 컨텍스트 인터페이스에 필요한 새 주소 값은 주소에 추가 생성 되므로 메모리 컨텍스트 주소입니다.  
  
 이 컨텍스트와 관련 된 메모리 공간 밖으로 만들어진 주소입니다 경우에이 메서드는 항상 새 컨텍스트를 생성 해야 합니다.  새 컨텍스트에 대 한 메모리를 할당 하지 수 있습니다 또는 경우에 예외입니다 `ppMemCxt` 오류는 null 값입니다.  
  
## 참고 항목  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)