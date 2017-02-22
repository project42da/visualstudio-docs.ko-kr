---
title: "IDebugBoundBreakpoint2::GetHitCount | Microsoft Docs"
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
  - "IDebugBoundBreakpoint2::GetHitCount"
helpviewer_keywords: 
  - "GetHitCount 메서드"
  - "IDebugBoundBreakpoint2::GetHitCount 메서드"
ms.assetid: 23481f37-047c-41d2-8286-4da1f4084961
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugBoundBreakpoint2::GetHitCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

에 바인딩된 중단점이 현재 적중된 횟수를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetHitCount(   
   DWORD* pdwHitCount  
);  
```  
  
```c#  
int GetHitCount(   
   out uint pdwHitCount  
);  
```  
  
#### 매개 변수  
 `pdwHitCount`  
 \[out\] 적중된 횟수를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_BP_DELETED` 바인딩된 중단점 개체의 상태를 설정는 경우 `BPS_DELETED` \(일부는 [BP\_STATE](../../../extensibility/debugger/reference/bp-state.md) 열거형\).  
  
## 설명  
 적중된 횟수를 현재 실행 하는 세션 동안이 중단점이 발생 시 횟수입니다.  
  
## 참고 항목  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP\_STATE](../../../extensibility/debugger/reference/bp-state.md)