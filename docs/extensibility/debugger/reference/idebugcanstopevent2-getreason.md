---
title: "IDebugCanStopEvent2::GetReason | Microsoft Docs"
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
  - "IDebugCanStopEvent2::GetReason"
helpviewer_keywords: 
  - "IDebugCanStopEvent2::GetReason"
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCanStopEvent2::GetReason
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\)를 중지 하려고 할 이유는 이유를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetReason(   
   CANSTOP_REASON* pcr  
);  
```  
  
```c#  
int GetReason(   
   out enum_CANSTOP_REASON pcr  
);  
```  
  
#### 매개 변수  
 `pcr`  
 \[out\] 반환 값에서는 [CANSTOP\_REASON](../../../extensibility/debugger/reference/canstop-reason.md) 이 이벤트에 대 한 이유를 설명 하는 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 일반적으로이 메서드가 호출 됩니다는 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) 호출자가 0이 아닌 값을 전달할 것인지 여부를 결정할 수 있도록 하는 메서드 \(`TRUE`\)에 `IDebugCanStopEvent2::CanStop` 메서드.  
  
 수 있습니다 중지 사유 `CANSTOP_ENTRYPOINT`는 DE은 진입점에 도달 하거나 `CANSTOP_STEPIN`, 함수에는 DE은 거두었습니다.  
  
## 참고 항목  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [CANSTOP\_REASON](../../../extensibility/debugger/reference/canstop-reason.md)   
 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)