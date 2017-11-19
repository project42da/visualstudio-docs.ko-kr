---
title: CONTEXT_COMPARE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CONTEXT_COMPARE
helpviewer_keywords: CONTEXT_COMPARE enumeration
ms.assetid: 701ed61c-a320-4c20-a335-0b840024abc0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 48043375ebdf904a7fafbae5e4193b42d8ba8269
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="contextcompare"></a>CONTEXT_COMPARE
두 메모리 컨텍스트를 비교 하기 위한 조건을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_CONTEXT_COMPARE {   
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
  
```csharp  
public enum enum_CONTEXT_COMPARE {   
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
  
## <a name="members"></a>멤버  
 CONTEXT_EQUAL  
 대상 메모리 내 컨텍스트에 같은 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT_LESS_THAN  
 대상 메모리 내 컨텍스트에 보다 작은 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT_GREATER_THAN  
 대상 메모리 내 컨텍스트에 보다 큰 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT_LESS_THAN_OR_EQUAL  
 대상 메모리 내 컨텍스트에 보다 작거나 목록에서 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT_GREATER_THAN_OR_EQUAL  
 대상 메모리 내 컨텍스트에 보다 크거나 같은 경우에 목록의 첫 번째 메모리 내 컨텍스트에 찾습니다.  
  
 CONTEXT_SAME_SCOPE  
 대상 메모리 내 컨텍스트에와 동일한 범위에 있는 목록의 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT_SAME_FUNCTION  
 대상 메모리 범위와 동일한 기능에 있는 목록의 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT_SAME_MODULE  
 대상 메모리 내 컨텍스트에와 같은 모듈에 있는 목록의 첫 번째 메모리 컨텍스트를 찾습니다.  
  
 CONTEXT_SAME_PROCESS  
 대상 메모리 내 컨텍스트에와 동일한 프로세스에 있는 목록의 첫 번째 메모리 컨텍스트를 찾습니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 인수로 전달 되는 [비교](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md) 메서드.  
  
 이러한 값은 첫 번째 메모리 내 컨텍스트에 지정 된 비교 기준을 충족 하는 목록에서 찾으려는 사용 됩니다. 메모리 내 컨텍스트에 메모리 컨텍스트의 목록을 통해 자체 작업에 대해 비교할 제공할지는 `IDebugMemoryContext2::Compare` 메서드. 비교 연산자는 목록의 첫 번째 메모리 내 컨텍스트에 `true` 반환 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)