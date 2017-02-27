---
title: "IDebugPendingBreakpoint2::SetCondition | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPendingBreakpoint2::SetCondition"
helpviewer_keywords: 
  - "SetCondition 메서드"
  - "IDebugPendingBreakpoint2::SetCondition 메서드"
ms.assetid: 0534224f-654f-4862-bc4d-a9a81a5f8899
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPendingBreakpoint2::SetCondition
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

설정 하거나 보류 중단점에 연관 된 상태를 변경 합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetCondition(   
   BP_CONDITION bpCondition  
);  
```  
  
```c#  
int SetCondition(   
   BP_CONDITION bpCondition  
);  
```  
  
#### 매개 변수  
 `bpCondition`  
 \[in\] A [BP\_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) 구조를 설정 하는 조건을 지정 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 보류 중단점에 이전에 연결 된 모든 조건이 손실 됩니다.  이 보류 중단점이 바인딩된 중단점을 모두 자신의 조건에 지정 된 값으로 설정 하기 위해 호출 되는 `bpCondition` 매개 변수.  
  
## 참고 항목  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [BP\_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)