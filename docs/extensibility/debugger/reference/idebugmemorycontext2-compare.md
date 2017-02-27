---
title: "IDebugMemoryContext2::Compare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugMemoryContext2::Compare"
helpviewer_keywords: 
  - "IDebugMemoryContext2::Compare 메서드"
  - "Compare 메서드"
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# IDebugMemoryContext2::Compare
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

각 컨텍스트에 일치 하는 첫 번째 컨텍스트의 인덱스를 반환 하는 비교 flags로 표시 된 방법으로 주어진 배열의 메모리 컨텍스트를 비교 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Compare(   
   CONTEXT_COMPARE        compare,  
   IDebugMemoryContext2** rgpMemoryContextSet,  
   DWORD                  dwMemoryContextSetLen,  
   DWORD*                 pdwMemoryContext  
);  
```  
  
```c#  
int Compare(  
   enum_CONTEXT_COMPARE   compare,   
   IDebugMemoryContext2[] rgpMemoryContextSet,   
   uint                   dwMemoryContextSetLen,   
   out uint               pdwMemoryContext  
);  
```  
  
#### 매개 변수  
 `compare`  
 \[in\] 값은 [CONTEXT\_COMPARE](../../../extensibility/debugger/reference/context-compare.md) 비교 형식을 결정 하는 열거형입니다.  
  
 `rgpMemoryContextSet`  
 \[in\] 배열에 대 한 참조를 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 와 비교할 개체입니다.  
  
 `dwMemoryContextSetLen`  
 \[in\] 한 상황에서의 수는 `rgpMemoryContextSet` 배열입니다.  
  
 `pdwMemoryContext`  
 \[out\] 비교를 만족 하는 첫 번째 메모리 컨텍스트의 인덱스를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_COMPARE_CANNOT_COMPARE` 두 컨텍스트 비교 될 수 없는 경우.  
  
## 설명  
 디버그 엔진 \(DE\)는 모든 종류의 비교 작업을 지원 하지는 않지만 적어도 지원 해야 `CONTEXT_EQUAL`, `CONTEXT_LESS_THAN`, `CONTEXT_GREATER_THAN` 및 `CONTEXT_SAME_SCOPE`.  
  
## 참고 항목  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT\_COMPARE](../../../extensibility/debugger/reference/context-compare.md)