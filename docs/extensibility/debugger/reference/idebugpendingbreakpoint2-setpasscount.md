---
title: "IDebugPendingBreakpoint2::SetPassCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPendingBreakpoint2::SetPassCount"
helpviewer_keywords: 
  - "SetPassCount 메서드"
  - "IDebugPendingBreakpoint2::SetPassCount 메서드"
ms.assetid: 08ddd328-57eb-42e0-baa9-8424dcd1bf04
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPendingBreakpoint2::SetPassCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

설정 하거나 보류 중단점에 관련 된 단계 수를 변경 합니다.  
  
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
 \[in\] A [BP\_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) 패스 개수를 포함 하는 구조입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_BP_DELETED` 중단점 삭제 된 경우입니다.  
  
## 설명  
 보류 중단점에 이전에 연결 되었던 모든 성공 횟수는 손실 됩니다.  모든 중단점을 보류 중단점이 바인딩되는 패스 개수를 설정할 라고는 `bpPassCount` 매개 변수.  
  
## 참고 항목  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [BP\_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)