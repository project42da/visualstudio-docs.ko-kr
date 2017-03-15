---
title: "IDebugBoundBreakpoint2::SetCondition | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBoundBreakpoint2::SetCondition"
helpviewer_keywords: 
  - "SetCondition 메서드"
  - "IDebugBoundBreakpoint2::SetCondition 메서드"
ms.assetid: 5d366876-efed-43d0-8ea1-dfdb009cbfac
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugBoundBreakpoint2::SetCondition
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

설정 하거나이 바인딩된 중단점에 연관 된 상태를 변경 합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetCondition(   
   BP_CONDITION bpCondition  
);  
```  
  
```c#  
int SetCondition(   
   enum_BP_CONDITION bpCondition  
);  
```  
  
#### 매개 변수  
 `bpCondition`  
 \[in\] 값은 [BP\_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) 조건에 설명 하는 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_BP_DELETED` 바인딩된 중단점 개체의 상태를 설정는 경우 `BPS_DELETED` \(일부는 [BP\_STATE](../../../extensibility/debugger/reference/bp-state.md) 열거형\).  
  
## 설명  
 이 중단점에 이전에 연결 된 모든 조건이 손실 됩니다.  
  
## 참고 항목  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP\_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)   
 [BP\_STATE](../../../extensibility/debugger/reference/bp-state.md)