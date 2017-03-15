---
title: "PENDING_BP_STATE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PENDING_BP_STATE"
helpviewer_keywords: 
  - "PENDING_BP_STATE 열거형"
ms.assetid: ac04ad72-fa92-4a15-ade2-0d0bbbadfc7f
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# PENDING_BP_STATE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

보류 중단점 \(아직 연결 된 중단점\)의 상태를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_PENDING_BP_STATE {   
   PBPS_NONE     = 0x0000,  
   PBPS_DELETED  = 0x0001,  
   PBPS_DISABLED = 0x0002,  
   PBPS_ENABLED  = 0x0003  
};  
typedef DWORD PENDING_BP_STATE;  
```  
  
```c#  
public enum enum_PENDING_BP_STATE {   
   PBPS_NONE     = 0x0000,  
   PBPS_DELETED  = 0x0001,  
   PBPS_DISABLED = 0x0002,  
   PBPS_ENABLED  = 0x0003  
};  
```  
  
## Members  
 PBPS\_NONE  
 0 자리 표시자입니다.  이 값은 반환 됩니다.  
  
 PBPS\_DELETED  
 보류 중단점 삭제 되었음을 나타냅니다.  
  
 PBPS\_DISABLED  
 보류 중단점이 해제 되었음을 나타냅니다.  
  
 PBPS\_ENABLED  
 보류 중단점이 설정 되었음을 나타냅니다.  
  
## 설명  
 사용은 `state` 의 멤버는 [PENDING\_BP\_STATE\_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md) 구조.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PENDING\_BP\_STATE\_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md)