---
title: "IDebugCanStopEvent2::CanStop | Microsoft Docs"
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
  - "IDebugCanStopEvent2::CanStop"
helpviewer_keywords: 
  - "IDebugCanStopEvent2::CanStop"
ms.assetid: 7d61adbe-6b3d-41f3-86a1-45d9cc01a7f8
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCanStopEvent2::CanStop
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\) 코드의 현재 위치에서 중지 하거나 방금 실행을 계속할 것인지 여부를 알립니다.  
  
## 구문  
  
```cpp#  
HRESULT CanStop (   
   BOOL fCanStop  
);  
```  
  
```c#  
int CanStop (   
   int fCanStop  
);  
```  
  
#### 매개 변수  
 `fCanStop`  
 \[in\] 0이 아닌 \(`TRUE`\)는 DE을 현재 코드 위치에 중지 그렇지 않으면 0 \(`FALSE`\).  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 일반적으로이 이벤트의 수신기를 호출을 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) 는 DE 할 중지 하는 이유를 확인 하려면 메서드에 대 한 호출의 `IDebugCanStopEvent2::CanStop` 메서드는 적절 한 응답을.  
  
 DE 중지 되 면 중지 사유를 설명 하는 이벤트를 보냅니다.  일반적으로 전송 된 나타내는 사용자 또는 신호 중단 이벤트가 두 가지는 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) 인터페이스와 표시 되는 중단점 이벤트를 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) 인터페이스입니다.  
  
## 참고 항목  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)   
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)