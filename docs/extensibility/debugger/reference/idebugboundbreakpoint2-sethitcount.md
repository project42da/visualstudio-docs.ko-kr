---
title: "IDebugBoundBreakpoint2::SetHitCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBoundBreakpoint2::SetHitCount"
helpviewer_keywords: 
  - "SetHitCount 메서드"
  - "IDebugBoundBreakpoint2::SetHitCount 메서드"
ms.assetid: 8145d875-26b1-4049-a2a2-e7d3d7f4735f
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugBoundBreakpoint2::SetHitCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

바인딩된 중단점에 적중된 횟수를 설정합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetHitCount(   
   DWORD dwHitCount  
);  
```  
  
```c#  
int SetHitCount(   
   uint dwHitCount  
);  
```  
  
#### 매개 변수  
 `dwHitCount`  
 \[in\] 설정 하려면 적중된 횟수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_BP_DELETED` 바인딩된 중단점 개체의 상태를 설정는 경우 `BPS_DELETED` \(일부는 [BP\_STATE](../../../extensibility/debugger/reference/bp-state.md) 열거형\).  
  
## 설명  
 적중된 횟수를 현재 실행 하는 세션 동안이 중단점이 발생 시 횟수입니다.  
  
 일반적으로이 메서드는 디버그 엔진에서이 중단점이 현재 적중된 횟수를 업데이트 하 여 호출 됩니다.  
  
## 참고 항목  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP\_STATE](../../../extensibility/debugger/reference/bp-state.md)