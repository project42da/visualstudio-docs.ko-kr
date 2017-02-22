---
title: "IDebugMemoryBytes2::ReadAt | Microsoft Docs"
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
  - "IDebugMemoryBytes2::ReadAt"
helpviewer_keywords: 
  - "IDebugMemoryBytes2::ReadAt 메서드"
  - "ReadAt 메서드"
ms.assetid: b413684d-4155-4bd4-ae30-ffa512243b5f
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugMemoryBytes2::ReadAt
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

시퀀스에 지정 된 위치에서 시작 하 여 바이트를 읽습니다.  
  
## 구문  
  
```cpp#  
HRESULT ReadAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory,  
   DWORD*                pdwRead,  
   DWORD*                pdwUnreadable  
);  
```  
  
```c#  
int ReadAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory,  
   out uint             pdwRead,  
   ref uint             pdwUnreadable  
);  
```  
  
#### 매개 변수  
 `pStartContext`  
 \[in\] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 바이트를 읽기 시작 하는 위치를 지정 하는 개체입니다.  
  
 `dwCount`  
 \[in\] 읽을 바이트의 수입니다.  또한 지정은 `rgbMemory` 배열입니다.  
  
 `rgbMemory`  
 \[in, out\] 배열에 있는 바이트로 채워진 실제로 읽기.  
  
 `pdwRead`  
 \[out\] 실제로 인접 한 바이트 수를 반환 합니다.  
  
 `pdwUnreadable`  
 \[in, out\] 읽을 바이트 수를 반환합니다.  클라이언트가 읽을 바이트 수에 관심이 있는 경우 null 값을 수 있습니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 100 바이트 요청 된 및 첫 번째 50 읽을 수 있는, 다음 20을 읽을 수 없는 고 나머지 30 읽을 수 있는 경우이 메서드를 반환 합니다.  
  
 \*`pdwRead` \= 50  
  
 \*`pdwUnreadable` \= 20  
  
 이 경우에 때문에 `*pdwRead + *pdwUnreadable < dwCount`, 호출자가 요청한 원래 100 중 나머지 30 바이트 읽기에서 추가로 호출 해야 하는 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 에 전달 되는 개체는 `pStartContext` 매개 변수는 70 여 고급 해야 합니다.  
  
## 참고 항목  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)