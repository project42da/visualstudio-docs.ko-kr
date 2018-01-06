---
title: BP_CONDITION | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_CONDITION
helpviewer_keywords: BP_CONDITION structure
ms.assetid: 407f87a3-2878-429b-8c65-b68feb36622a
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9ccc0b142e87acd3a09840f8c72f5fe1a35bc0a4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bpcondition"></a>BP_CONDITION
중단점을 발생 조건을 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _BP_CONDITION {   
   IDebugThread2* pThread;  
   BP_COND_STYLE  styleCondition;  
   BSTR           bstrContext;  
   BSTR           bstrCondition;  
   UINT           nRadix;  
} BP_CONDITION;  
```  
  
```csharp  
public struct BP_CONDITION {   
   public IDebugThread2 pThread;  
   public uint          styleCondition;  
   public string        bstrContext;  
   public string        bstrCondition;  
   public uint          nRadix;  
};  
```  
  
## <a name="members"></a>멤버  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 중단점을 포함 하는 응용 프로그램에 대 한 활성 스레드를 나타내는 개체입니다.  
  
 `styleCondition`  
 값은 [BP_COND_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md) 이 중단점 조건의 스타일을 설명 하는 열거형입니다.  
  
 `bstrContext`  
 중단점의 위치입니다.  
  
 `bstrCondition`  
 중단점의 발생 조건입니다.  
  
 `nRadix`  
 모든 숫자 정보를 평가 하는 데 사용할 기 수입니다.  
  
## <a name="remarks"></a>설명  
 이 구조는의 구성원은 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 및 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조입니다.  
  
 이 구조에 대 한 매개 변수로 전달 되는 [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md) 및 [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [BP_COND_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md)