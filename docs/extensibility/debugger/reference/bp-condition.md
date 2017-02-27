---
title: "BP_CONDITION | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_CONDITION"
helpviewer_keywords: 
  - "BP_CONDITION 구조"
ms.assetid: 407f87a3-2878-429b-8c65-b68feb36622a
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# BP_CONDITION
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

중단점을 발생 시키는 조건을 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct _BP_CONDITION {   
   IDebugThread2* pThread;  
   BP_COND_STYLE  styleCondition;  
   BSTR           bstrContext;  
   BSTR           bstrCondition;  
   UINT           nRadix;  
} BP_CONDITION;  
```  
  
```c#  
public struct BP_CONDITION {   
   public IDebugThread2 pThread;  
   public uint          styleCondition;  
   public string        bstrContext;  
   public string        bstrCondition;  
   public uint          nRadix;  
};  
```  
  
## Members  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 있는 중단점을 포함 하는 응용 프로그램에 대 한 활성 스레드를 나타내는 개체입니다.  
  
 `styleCondition`  
 값은 [BP\_COND\_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md) 이 중단점 조건의 스타일을 설명 하는 열거형입니다.  
  
 `bstrContext`  
 위치 중단점입니다.  
  
 `bstrCondition`  
 중단점의 실행 조건입니다.  
  
 `nRadix`  
 기 수 숫자 정보 계산에 사용 되.  
  
## 설명  
 이 구조체의 멤버인는 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 및 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조체입니다.  
  
 이 구조는 매개 변수로 전달 되는 [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md) 및 [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md) 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [BP\_COND\_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md)