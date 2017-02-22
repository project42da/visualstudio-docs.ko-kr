---
title: "IDebugMemoryBytes2::WriteAt | Microsoft Docs"
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
  - "IDebugMemoryBytes2::WriteAt"
helpviewer_keywords: 
  - "IDebugMemoryBytes2::WriteAt 메서드"
  - "WriteAt 메서드"
ms.assetid: 61cc3704-47fa-4d9b-aa62-bb4585ac8fb1
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugMemoryBytes2::WriteAt
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

지정 된 번호는 지정 된 주소에서 시작 하는 메모리의 바이트를 씁니다.  
  
## 구문  
  
```cpp#  
HRESULT WriteAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory  
);  
```  
  
```c#  
int WriteAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory  
);  
```  
  
#### 매개 변수  
 `pStartContext`  
 \[in\] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 바이트 쓰기 시작할 위치를 지정 하는 개체입니다.  
  
 `dwCount`  
 \[in\] 쓸 바이트 수입니다.  
  
 `rgbMemory`  
 \[in\] 쓸 바이트 수입니다.  이 배열에는 최소한으로 간주 됩니다 `dwCount` 의 크기 \(바이트\)입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 모든 바이트를 쓸 수 또는 오류 코드를 반환 하는 경우 \(일반적으로 `E_FAIL`\).  
  
## 설명  
 시작 주소 이것에 나타내는 메모리 창 내에서 없는 경우 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) 개체, 없음 쓰기 발생 하 고 오류 코드를 `E_FAIL` 반환 됩니다\-작성할 양을 메모리 공간에 겹치는 경우에.  
  
## 참고 항목  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)