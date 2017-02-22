---
title: "CONTEXT_COMPARE | Microsoft Docs"
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
  - "CONTEXT_COMPARE"
helpviewer_keywords: 
  - "CONTEXT_COMPARE 열거형"
ms.assetid: 701ed61c-a320-4c20-a335-0b840024abc0
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# CONTEXT_COMPARE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

두 개의 메모리 컨텍스트에서 비교 하는 조건을 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_CONTEXT_COMPARE {   
   CONTEXT_EQUAL                 = 0x0001,  
   CONTEXT_LESS_THAN             = 0x0002,  
   CONTEXT_GREATER_THAN          = 0x0003,  
   CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,  
   CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,  
   CONTEXT_SAME_SCOPE            = 0x0006,  
   CONTEXT_SAME_FUNCTION         = 0x0007,  
   CONTEXT_SAME_MODULE           = 0x0008,  
   CONTEXT_SAME_PROCESS          = 0x0009  
};  
typedef DWORD CONTEXT_COMPARE;  
```  
  
```c#  
public enum enum_CONTEXT_COMPARE {   
   CONTEXT_EQUAL                 = 0x0001,  
   CONTEXT_LESS_THAN             = 0x0002,  
   CONTEXT_GREATER_THAN          = 0x0003,  
   CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,  
   CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,  
   CONTEXT_SAME_SCOPE            = 0x0006,  
   CONTEXT_SAME_FUNCTION         = 0x0007,  
   CONTEXT_SAME_MODULE           = 0x0008,  
   CONTEXT_SAME_PROCESS          = 0x0009  
};  
```  
  
## Members  
 CONTEXT\_EQUAL  
 해당 컨텍스트로 메모리에는 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT\_LESS\_THAN  
 보다 대상 메모리 컨텍스트 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT\_GREATER\_THAN  
 첫 번째 메모리 컨텍스트에서를 컨텍스트로 메모리 보다 큰 목록에서 찾습니다.  
  
 CONTEXT\_LESS\_THAN\_OR\_EQUAL  
 대상 메모리 상황에 맞는 보다 작거나 목록에 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT\_GREATER\_THAN\_OR\_EQUAL  
 대상 메모리 컨텍스트 이상이 되는 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT\_SAME\_SCOPE  
 대상 메모리 컨텍스트에서와 같은 범위에 있는 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT\_SAME\_FUNCTION  
 대상 메모리 범위와 같은 기능에 있는 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT\_SAME\_MODULE  
 대상 메모리 컨텍스트에서와 동일한 모듈에 있는 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT\_SAME\_PROCESS  
 대상 메모리 컨텍스트에서와 같은 프로세스에 있는 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
## 설명  
 인수로 전달 되는 [비교](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md) 방법입니다.  
  
 이러한 값은 목록에 지정 된 조건에 맞는 첫 번째 메모리 컨텍스트를 찾으려면 사용 됩니다.  메모리 컨텍스트 메모리 컨텍스트의 목록을 통해에서 자신을 비교 부여 됩니다는 `IDebugMemoryContext2::Compare` 메서드가 있습니다.  첫 번째 메모리 컨텍스트를 비교 연산자 목록에서 `true` 다음이 반환 됩니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [비교](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)