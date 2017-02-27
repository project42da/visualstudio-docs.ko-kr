---
title: "PENDING_BP_STATE_INFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PENDING_BP_STATE_INFO"
helpviewer_keywords: 
  - "PENDING_BP_STATE_INFO 구조"
ms.assetid: 4d73ceff-43f9-4e95-8dba-88e1fab2def3
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# PENDING_BP_STATE_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

코드 위치를 바인딩할 준비가 되어 중단점의 상태에 대 한 정보가 포함 되어 있습니다.  
  
## 구문  
  
```cpp#  
typedef struct _tagPENDING_BP_STATE_INFO {   
   PENDING_BP_STATE       state;  
   PENDING_BP_STATE_FLAGS flags;  
} PENDING_BP_STATE_INFO;  
```  
  
```c#  
public struct PENDING_BP_STATE_INFO {   
   public uint state;  
   public uint flags;  
};  
```  
  
## Members  
 state  
 값은 [PENDING\_BP\_STATE](../../../extensibility/debugger/reference/pending-bp-state.md) 보류 중단점의 상태를 지정 하는 열거형입니다.  
  
 플래그  
 플래그의 조합에 [PENDING\_BP\_STATE\_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md) 중단점 가상화 여부를 지정 하는 열거형입니다.  
  
## 설명  
 이 구조체에 전달 되는 [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md) 메서드는 입력 위치에 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)   
 [PENDING\_BP\_STATE](../../../extensibility/debugger/reference/pending-bp-state.md)   
 [PENDING\_BP\_STATE\_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md)