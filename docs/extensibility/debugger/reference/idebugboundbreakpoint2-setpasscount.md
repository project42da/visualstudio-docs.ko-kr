---
title: "IDebugBoundBreakpoint2::SetPassCount | Microsoft Docs"
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
  - "IDebugBoundBreakpoint2::SetPassCount"
helpviewer_keywords: 
  - "SetPassCount 메서드"
  - "IDebugBoundBreakpoint2::SetPassCount 메서드"
ms.assetid: b32c12f9-b34d-43bd-a1b9-61af6cf8e51b
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugBoundBreakpoint2::SetPassCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

설정 하거나이 바인딩된 중단점에 관련 된 단계 수를 변경 합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetPassCount(   
   BP_PASSCOUNT bpPassCount  
);  
```  
  
```c#  
int SetPassCount(   
   BP_PASSCOUNT bpPassCount  
);  
```  
  
#### 매개 변수  
 `bpPassCount`  
 \[in\] [BP\_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) 의 단계 수를 지정 하는 구조입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_BP_DELETED` 바인딩된 중단점 개체의 상태를 설정는 경우 `BPS_DELETED` \(일부는 [BP\_STATE](../../../extensibility/debugger/reference/bp-state.md) 열거형\).  
  
## 설명  
 통과 횟수 중단점을 발생 하는 시기를 결정 합니다.  현재 패스 또는 적중된 횟수를 호출 하 여 얻을 수 있는 [GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md) 메서드.  
  
 이 중단점에 이전에 연결 된 모든 성공 횟수는 손실 됩니다.  
  
## 참고 항목  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md)   
 [BP\_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP\_STATE](../../../extensibility/debugger/reference/bp-state.md)